# Mon Devis Déménagement — landing page

Landing page de génération de leads pour le déménagement, pensée pour le trafic
Google Ads. Site statique sans build, déployé sur GitHub Pages.

**En ligne :** https://remivinel-netizen.github.io/lp-mon-devis-demenagement/

## L'idée

Le marché est saturé de comparateurs qui demandent vos coordonnées *avant* de
vous apprendre quoi que ce soit. Ici c'est l'inverse : le visiteur obtient son
volume et sa fourchette de prix **pendant** qu'il répond, et ne laisse ses
coordonnées qu'à la dernière étape, une fois le chiffre sous les yeux.

C'est le seul vrai levier de conversion de la page — tout le reste en découle.

## Fichiers

| Fichier                 | Rôle                                                      |
| ----------------------- | --------------------------------------------------------- |
| `index.html`            | La LP complète. CSS et JS en ligne, aucune dépendance.      |
| `merci.html`            | Confirmation + récapitulatif. **Page de conversion.**       |
| `mentions-legales.html` | Gabarit à compléter.                                        |
| `confidentialite.html`  | Gabarit à compléter.                                        |
| `404.html`              | Page d'erreur.                                              |
| `page.css`              | Styles communs aux pages secondaires uniquement.            |
| `fonts/`                | Plus Jakarta Sans + Instrument Serif, auto-hébergées (OFL). |
| `img/`                  | Logo (2 variantes) et favicon, en SVG.                      |

`index.html` et `merci.html` embarquent leur CSS : ce sont les deux pages qui
doivent s'afficher sans requête bloquante.

## Charte graphique

Les trois concurrents étudiés (officiel-demenagement, nextories,
demenagement24) utilisent **tous** le même bleu corporate. D'où le contre-pied :
un **vert forêt** profond et un **kraft de carton**, qui disent le métier plutôt
que la catégorie. La brique terracotta sert exclusivement à l'action.

| Jeton             | Valeur    | Emploi                              | Contraste            |
| ----------------- | --------- | ----------------------------------- | -------------------- |
| `--foret`         | `#0C3B2E` | Titres, grands aplats               | 12,50 / blanc        |
| `--brique`        | `#C4461E` | Boutons, accents                    | 4,95 / blanc (AA)    |
| `--brique-fonce`  | `#9E3415` | La brique en petit texte            | 7,10 / blanc         |
| `--brique-vif`    | `#E05A2B` | **Décor et survol uniquement**      | 3,71 — jamais texte  |
| `--kraft`         | `#EADBC4` | Fonds clairs, accents sur fond vert | encre à 12,13 dessus |
| `--sable`         | `#FBF7F0` | Fond de page                        | —                    |
| `--ink-3`         | `#6B746F` | Texte atténué                       | 4,52 / sable (AA)    |

Tous ces ratios sont **mesurés**, pas estimés. Toute nouvelle couleur doit être
vérifiée avant d'être posée.

Typographie : **Plus Jakarta Sans** (variable 400–800) pour le texte,
**Instrument Serif italique** pour les accents de titre. Les deux sont sous
licence SIL OFL et servies depuis `fonts/` — ni CDN, ni Google Fonts, donc
aucune requête tierce au chargement.

## Le formulaire

Six étapes, dans cet ordre :

1. **Logement** — studio à 5 pièces, avec le volume indicatif affiché
2. **Départ** — code postal, étage, ascenseur
3. **Arrivée** — idem
4. **Date** — de « dès que possible » à « je me renseigne » (sert au scoring)
5. **Formule** — qui emballe les cartons
6. **Contact** — prénom, nom, email, téléphone, consentement

Les étapes à boutons radio avancent toutes seules. Les codes postaux sont
résolus via [geo.api.gouv.fr](https://geo.api.gouv.fr) : on récupère le **centre
de la commune**, donc une vraie distance haversine (majorée de 25 % pour
approcher le trajet routier) et non une approximation par département.

Mesuré : Lyon → Bordeaux donne 544 km (réel ≈ 550), Paris → Lyon 491 km
(réel ≈ 465).

### Moteur de prix

Tout se règle dans la constante `TARIF` d'`index.html` — tarif au m³, borne
basse et borne haute, par bande de distance (local < 50 km, régional < 300 km,
national au-delà) et par formule. Un plancher à 390 € évite les estimations
absurdes sur les très petits volumes, et un étage sans ascenseur majore de
3,5 % par niveau, plafonné à cinq.

Les fourchettes sont calées sur le marché français 2026 (33 à 90 €/m³ selon
distance et formule). **À réviser une fois par an.**

### Envoi du lead

L'endpoint vit dans l'attribut `data-endpoint` du `<form id="q-form">`.
Tant qu'il contient `REMPLACER`, **l'envoi est simulé** et le payload s'affiche
dans la console : la page est testable telle quelle, sans fuiter de lead.

Pour l'activer, remplacer par l'URL du webhook (Make, n8n, CRM…) :

```html
<form id="q-form" data-endpoint="https://hook.eu1.make.com/VOTRE_WEBHOOK">
```

Le payload JSON contient le projet (logement, volume, communes, distance, étages,
date, formule), l'estimation calculée, la priorité (`chaud` / `tiede` / `froid`
selon l'échéance), le contact, la preuve de consentement horodatée, et tous les
identifiants publicitaires captés.

> ⚠️ Un `data-endpoint` est **public** : n'y mettez qu'une URL de webhook sans
> secret. Si l'endpoint doit être authentifié, passez par un petit proxy
> serveur — GitHub Pages ne sait pas en héberger un.

### Mesure

Événements `dataLayer` : `quiz_start`, `quiz_step`, `estimation_vue`,
`quiz_contact_vu`, `generate_lead` (avec `user_data` pour les conversions
améliorées), `cta_click`.

Le snippet GTM est présent **en commentaire** dans `index.html` et `merci.html` :
décommenter et remplacer `GTM-XXXXXXX`. La conversion Google Ads se règle sur
`/merci.html`.

Les identifiants de clic (`gclid`, `gbraid`, `wbraid`, `fbclid`, `msclkid`) et
les `utm_*` sont captés à l'arrivée et conservés en `sessionStorage` : ils
survivent à la navigation interne et sont joints au lead.

## À compléter avant la mise en ligne

Rien de tout ceci n'est bloquant pour une démo, tout l'est pour une mise en ligne.

- [ ] **Les avis clients.** Les trois témoignages du tableau `AVIS`
      (`index.html`) sont des **exemples de mise en forme**, explicitement
      marqués comme tels. Les remplacer par de vrais avis, avec l'accord écrit
      des personnes citées et la date réelle de la prestation.
- [ ] **Le téléphone et les horaires** — `01 80 00 00 00` et
      « lundi–samedi 9h–19h » apparaissent dans l'en-tête, le pied de page et la
      barre mobile. Trois occurrences, plus le `tel:` de chacune.
- [ ] **Les mentions légales** — tous les champs entre crochets, plus le
      médiateur de la consommation (obligatoire, art. L.616-1).
- [ ] **La politique de confidentialité** — responsable de traitement, durées de
      conservation réellement appliquées, liste des sous-traitants.
- [ ] **Un bandeau de consentement** conforme, avant d'activer le moindre
      traceur publicitaire.
- [ ] **Le webhook** du formulaire (voir ci-dessus).
- [ ] **GTM** — décommenter et renseigner l'identifiant.
- [ ] **Les fourchettes de prix** du tableau et de `TARIF` — à faire valider par
      les déménageurs du réseau.
- [ ] **Le domaine** — `mon-devis-demenagement.fr` est posé dans le `canonical`
      et les Open Graph. À confirmer ou à changer (3 occurrences).
- [ ] **Une image Open Graph** (`og:image`, 1200 × 630) : absente aujourd'hui,
      les partages sociaux sortent donc sans visuel.

## Développement

Aucun build, aucune dépendance. Pour servir en local :

```bash
python3 -m http.server 4319
```

Puis http://localhost:4319.

## Déploiement

GitHub Pages sert la branche `main` à la racine. Un `push` suffit ; le `.nojekyll`
évite que Jekyll ne filtre les fichiers.

Pour brancher un domaine : ajouter un fichier `CNAME` contenant le domaine, et
faire pointer le DNS vers GitHub Pages.
