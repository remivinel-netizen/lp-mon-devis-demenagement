# Mon Devis Déménagement — landing page

Landing page de génération de leads pour le déménagement, pensée pour le trafic
Google Ads. Site statique sans build, déployé sur GitHub Pages.

**En ligne :** https://remivinel-netizen.github.io/lp-mon-devis-demenagement/

## L'idée

Deux partis pris, l'un sur la mécanique, l'autre sur le discours.

**La mécanique.** Le marché demande vos coordonnées *avant* de vous apprendre
quoi que ce soit. Ici c'est l'inverse : le visiteur obtient son volume et sa
fourchette de prix **pendant** qu'il répond, et ne laisse ses coordonnées qu'à
la dernière étape, le chiffre sous les yeux.

**Le discours.** Il reprend le registre de
[l'Officiel du Déménagement](https://www.officiel-demenagement.com/) : une
promesse de sérénité plutôt qu'une mise en concurrence, des services compris
plutôt qu'une comparaison de devis, et un conseiller identifié plutôt qu'une
plateforme. Concrètement, quatre arguments structurent la page :

1. **« Vous ne payez que les kilomètres aller »** — l'argument de prix le plus
   fort du secteur, et le plus mal expliqué. Il a sa propre section, avec un
   schéma, parce qu'il ne se comprend pas en une ligne.
2. **« Tout compris »** — cartons livrés, assurance du mobilier, changement
   d'adresse, compris dans les trois formules.
3. **Un conseiller, pas un robot** — la même personne du devis au jour J,
   avec ses horaires affichés.
4. **Les formalités prises en charge** — la partie fastidieuse (impôts, CAF,
   énergie, compteurs) est traitée ou guidée.

Les formules reprennent la nomenclature du marché — **Économique / Standard /
Luxe** — avec le partage des tâches détaillé formule par formule, puisque c'est
là que les devis deviennent incomparables.

### Appels à l'action

Motif repris de `lp-mon-bilan-solaire` : **un CTA ferme chaque section de
contenu, toujours avec le même libellé** (« Obtenir mon devis »), suivi d'une
courte mention de réassurance. Le visiteur n'a jamais à remonter chercher le
formulaire.

| Section                | CTA |
| ---------------------- | --- |
| Hero                   | — (il contient le formulaire) |
| Bandeau des 4 piliers   | — (bloc de preuve) |
| Kilomètres aller        | ✓ |
| Comment ça se passe     | ✓ |
| Les trois formules      | ✓ |
| Les services offerts    | ✓ |
| Les cas particuliers    | ✓ |
| Le conseiller           | ✓ |
| Les avis                | ✓ |
| FAQ                     | — |
| CTA final               | ✓ |

Plus l'en-tête et la barre collante mobile, soit **dix entrées** vers le même
formulaire. Changer le libellé se fait donc en dix endroits — ou nulle part.

### Règle de rédaction : rien d'inventé

Chaque affirmation de la page doit être **étayée par la page de référence** ou
par un fait public vérifiable. Ce qui n'a pas de source a été retiré, même
quand c'était vendeur :

| Retiré                                   | Pourquoi                                               |
| ---------------------------------------- | ------------------------------------------------------ |
| « Rappel sous 24 h », « devis sous 24 h » | Aucun délai de ce type n'est documenté                 |
| Les 5 critères de vérification            | Procédure de contrôle entièrement inventée             |
| « La même personne du devis au jour J »   | Continuité du suivi non documentée                     |
| « Sans partage de camion imposé »         | Contredit le principe même du groupage                 |
| « Appel non surtaxé »                     | Non vérifié                                            |
| « Évacuation des cartons vides »          | Absent de la formule luxe de référence                 |
| « Jusqu'à 38 % d'économie »               | Chiffre du marché, pas une donnée à nous               |
| Tous les montants en euros                | Demande explicite : aucune estimation de prix          |

Les horaires sont alignés sur ceux de la référence (lundi-samedi, 9h-18h) et
restent des **placeholders** à confirmer, comme le numéro de téléphone.

Ce qui reste est étayé : les kilomètres aller, les cartons sous 24 à 48 h,
l'assurance et le changement d'adresse compris, les trois formules et leur
partage des tâches, les cas particuliers, la validation par acompte.

**Les chiffres de la référence n'ont pas été recopiés** — ni les 80 000 € de
garantie, ni les 300 enseignes partenaires, ni leur ancienneté : ce sont leurs
données, pas les nôtres. Les équivalents doivent venir du client.

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

Structure relevée au pixel sur
[officiel-demenagement.com](https://www.officiel-demenagement.com/) — polices,
rayons et graisses lus dans leurs styles calculés, pas approximés. L'accent
secondaire s'en écarte volontairement : leur vert pomme est remplacé par un
**ambre**, accordé aux tons carton et bois de la photo du hero, et qui complète
le magenta au lieu de lui disputer l'attention.

| Jeton          | Valeur    | Emploi                                   | Contraste            |
| -------------- | --------- | ---------------------------------------- | -------------------- |
| `--magenta`    | `#CE0054` | **Action principale**, blanc dessus      | 5,60 — AA            |
| `--magenta-2`  | `#A3003F` | Survol, anneau de focus                  | 7,99 / blanc         |
| `--nuit`       | `#222E3A` | Ancre : hero, sections sombres, titres   | 13,82 / blanc        |
| `--nuit-3`     | `#19232C` | Pied de page                             | blanc à 15,93 dessus |
| `--ambre`      | `#F5A623` | **Accent secondaire**, encre navy dessus | 6,82 sur `--nuit`    |
| `--ambre-fonce`| `#8A5A00` | L'ambre en petit texte sur fond clair    | 5,93 / blanc         |
| `--ambre-pale` | `#FBE8C4` | Pastilles d'icônes, fonds de bloc        | navy à 11,48 dessus  |
| `--gris`       | `#F4F5F9` | Fond de page                             | —                    |
| `--ink`        | `#333333` | Texte courant                            | 12,63 / blanc        |

**Typographie :** **Roboto Slab** en titres (graisse **400**, comme eux — pas
du 700, qui donnait un ton « start-up ») et **Roboto** en texte. Auto-hébergées
depuis `fonts/`, licence Apache 2.0.

**Formes :** rayons de **12 px** sur les boutons, **8 px** sur les champs et
pastilles, **4 px** sur les grandes cartes — relevés chez eux. La version
précédente utilisait des pastilles à 999 px et des cartes à 30 px, ce qui
lisait « application mobile » plutôt que « déménageur ».

### Trois écarts volontaires, mesure à l'appui

1. Leur site pose du **blanc sur le vert pomme** : 2,04, illisible. L'action
   principale passe donc sur leur magenta, qui tient le blanc à 5,60, et
   l'accent secondaire devient l'ambre — qui ne porte lui non plus que
   l'encre navy.
2. Leur **gris de texte `#8F929B`** plafonne à 3,11. Remplacé par `#5B6472`,
   même famille ardoise, 5,98.
3. Aucun anneau de focus ne tient sur navy **et** sur blanc : le magenta foncé
   sert sur fond clair, une règle bascule sur l'ambre en section sombre.

### Le hero

Photo générée pour le projet (`img/hero-1600.jpg`, 110 Ko ; `hero-900.jpg`,
41 Ko sous 900 px) : un séjour vide avec des cartons, dans l'esprit de leur
hero photographique.

Le voile navy par-dessus est **calibré, pas estimé**. Le pixel le plus clair
sous le titre est du blanc pur — la fenêtre du cliché. Mesuré par
échantillonnage de l'image en canvas :

| Opacité du voile | Contraste du titre blanc |
| ---------------- | ------------------------ |
| 0,96             | 9,13                     |
| **0,90** (retenu) | **6,06**                |
| 0,86             | 4,94                     |
| 0,80             | 3,88 — sous le seuil     |

Le voile s'éclaircit jusqu'à 0,60 à droite, sous la carte du formulaire, où
aucun texte clair ne repose sur la photo : c'est là qu'on la laisse se voir.

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

### Aucun montant affiché

**La page ne communique aucun prix** — ni estimation personnalisée, ni grille
de tarifs. C'est le conseiller qui chiffre, sur le volume réel.

Le formulaire conserve en revanche son panneau de retour : il affiche le
**volume** et le **trajet** (« Environ 30 m³ — Lyon → Bordeaux, 544 km »). Il
remplit la même fonction qu'une estimation chiffrée — donner au visiteur le
sentiment d'être compris, et une raison d'aller au bout — sans engager un
montant que personne ne pourra tenir.

Le volume et la distance partent dans le lead&nbsp;: c'est ce dont le conseiller
a besoin pour préparer son appel.

> Si un prix devait revenir un jour, il faudrait le remettre à **cinq** endroits
> cohérents entre eux : le panneau du formulaire, le récapitulatif de `/merci`,
> le payload, et les mentions qualitatives du hero et des formules.

### Envoi du lead

L'endpoint vit dans l'attribut `data-endpoint` du `<form id="q-form">`.
Tant qu'il contient `REMPLACER`, **l'envoi est simulé** et le payload s'affiche
dans la console : la page est testable telle quelle, sans fuiter de lead.

Pour l'activer, remplacer par l'URL du webhook (Make, n8n, CRM…) :

```html
<form id="q-form" data-endpoint="https://hook.eu1.make.com/VOTRE_WEBHOOK">
```

Le payload JSON (39 champs) contient le projet (logement, volume, communes,
distance, étages, date, formule), la priorité (`chaud` / `tiede` / `froid` selon
l'échéance), le contact, la preuve de consentement horodatée, et tous les
identifiants publicitaires captés. **Aucun champ de prix.**

> ⚠️ Un `data-endpoint` est **public** : n'y mettez qu'une URL de webhook sans
> secret. Si l'endpoint doit être authentifié, passez par un petit proxy
> serveur — GitHub Pages ne sait pas en héberger un.

### Mesure

Événements `dataLayer` : `quiz_start`, `quiz_step`, `recap_projet_vu`,
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

- [ ] **Les quatre promesses commerciales.** Cartons offerts, assurance du
      mobilier comprise, changement d'adresse pris en charge, et « vous ne payez
      que les kilomètres aller ». Elles sont reprises du modèle de l'Officiel du
      Déménagement et **structurent toute la page** — hero, bandeau, section
      dédiée, formules, services offerts, FAQ, page `/merci`. Elles n'ont de
      valeur que si le réseau les honore réellement. Un bloc `⚠ À VALIDER` les
      signale dans `index.html`. **Soit on les confirme, soit on les retire
      partout à la fois** — une promesse à moitié tenue coûte plus cher qu'une
      promesse absente.
- [ ] **Le plafond de la garantie dommage** : la FAQ renvoie au conseiller plutôt
      que d'annoncer un montant. À fournir si vous voulez le publier.
- [ ] **Le délai de rappel et de devis** : volontairement absent faute de source.
      Si vous vous engagez sur un délai, il est très vendeur — redonnez-le et il
      retrouvera sa place dans le hero, les étapes et `/merci`.
- [ ] **La procédure de sélection des déménageurs** : la section qui la décrivait
      a été retirée (inventée). Si le réseau vérifie réellement SIRET, licence de
      transport et assurance, c'est un argument fort à réécrire sur pièces.
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
