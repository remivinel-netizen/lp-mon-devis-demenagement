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

### D'où vient le contenu

Deux sources, deux statuts.

**[matchmove.fr](https://matchmove.fr/formules-demenagement/) — l'offre réelle.**
C'est de là que viennent les faits : les trois formules **Éco / Standard / Luxe**
et leur partage des tâches poste par poste, le **devis en 1 heure**, les **97 %
de clients satisfaits**, les **1 000+ déménageurs partenaires**, l'**annulation
gratuite jusqu'à deux semaines** avant, le transfert des contrats (eau, gaz,
électricité, internet, assurance), le garde-meuble sur 350+ sites, le téléphone
et les horaires.

**[officiel-demenagement.com](https://www.officiel-demenagement.com/) — le
registre.** Structure du discours, vocabulaire de réassurance, l'argument des
« kilomètres aller », la grammaire visuelle. Aucun de leurs chiffres n'est
repris : ni les 80 000 € de garantie, ni les 300 enseignes partenaires, ni leur
ancienneté — ce sont leurs données.

### Un piège à ne pas refaire

**Les cartons ne sont pas inclus dans les trois formules.** Ils sont en
**option** en Éco et Standard, et **fournis en Luxe** seulement. Une version
antérieure de cette page les annonçait partout, par analogie avec le modèle
d'Officiel du Déménagement — c'était faux. Un commentaire le rappelle dans
`index.html`, au-dessus du hero.

Ce qui est vraiment inclus partout : le transfert des contrats, la protection
du mobilier (housses, bulle, housses matelas), le chargement et la livraison,
et le droit de modifier ou d'annuler.

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
| `img/`                  | Logo (2 variantes), favicon et photo du hero.               |

`index.html` et `merci.html` embarquent leur CSS : ce sont les deux pages qui
doivent s'afficher sans requête bloquante.

## Charte graphique

Structure relevée au pixel sur
[officiel-demenagement.com](https://www.officiel-demenagement.com/) — polices,
rayons et graisses lus dans leurs styles calculés, pas approximés.

La charte tient en **deux teintes et des gris** : le navy et le magenta. Pas de
troisième couleur. Sur fond sombre, où le magenta ne tient pas (2,47 sur le
navy), c'est sa version claire qui prend le relais — même famille, pas un
nouvel accent.

| Jeton          | Valeur    | Emploi                                   | Contraste            |
| -------------- | --------- | ---------------------------------------- | -------------------- |
| `--magenta`    | `#CE0054` | **Action principale**, blanc dessus      | 5,60 — AA            |
| `--magenta-2`  | `#A3003F` | Survol, anneau de focus                  | 7,99 / blanc         |
| `--nuit`       | `#222E3A` | Ancre : hero, sections sombres, titres   | 13,82 / blanc        |
| `--nuit-3`     | `#19232C` | Pied de page                             | blanc à 15,93 dessus |
| `--rose`       | `#FF7389` | **Accent sur fond sombre** uniquement     | 5,31 sur `--nuit`    |
| `--rose-2`     | `#F0576E` | Décor : survols, filets                  | —                    |
| `--rose-pale`  | `#FCDDE1` | Pastilles d'icônes, étiquettes           | navy à 10,90 dessus  |
| `--gris`       | `#F4F5F9` | Fond de page                             | —                    |
| `--ink`        | `#333333` | Texte courant                            | 12,63 / blanc        |

**Typographie : Archivo**, une seule famille pour toute la page. Son **axe de
largeur** fait la hiérarchie à la place d'un second caractère — titres élargis
à **112 %**, sur-titres resserrés à **88 %** avec un interlettrage de 0,18 em.
Graisse 700 partout, tracking serré (−0,035 em) sur les titres.

Le fichier est réduit aux plages réellement utilisées (wght 400-700, wdth
85-115) par instanciation partielle&nbsp;: **72,6 Ko** au lieu de 88, soit le
poids des deux fichiers Roboto qu'il remplace. Le français tient entièrement
dans le subset `latin` (é, è, à, ç sont sous U+00FF), donc `latin-ext` ne se
charge jamais ici.

> Les versions précédentes utilisaient Roboto Slab + Roboto, par mimétisme avec
> la référence. Roboto est la police système d'Android&nbsp;: c'est le degré
> zéro de la personnalisation, et ça se voyait. Deux autres pistes avaient été
> comparées en contexte — **Fraunces + Instrument Sans** (serif à caractère) et
> **Bricolage Grotesque + Inter** (grotesque contemporain).

**Formes :** boutons à **angles droits**, en capitales avec interlettrage —
8 px sur les champs et pastilles, 4 px sur les grandes cartes. Le bouton à coins
arrondis et graisse moyenne lisait « gabarit »&nbsp;; l'angle vif et les
capitales lui donnent une intention.

### Trois écarts volontaires, mesure à l'appui

1. Leur site pose du **blanc sur le vert pomme** : 2,04, illisible. L'action
   principale passe donc sur leur magenta, qui tient le blanc à 5,60, et leur
   vert disparaît de la charte — remplacé non par une autre couleur mais par
   la version claire du magenta, là où le magenta lui-même ne tient pas.
2. Leur **gris de texte `#8F929B`** plafonne à 3,11. Remplacé par `#5B6472`,
   même famille ardoise, 5,98.
3. Aucun anneau de focus ne tient sur navy **et** sur blanc : le magenta foncé
   sert sur fond clair, une règle bascule sur le rose clair en section sombre.

### Le logo

Fourni par le client (archive `logo-1e`) : trois cartons arrondis en décalé —
accent, encre et gris — suivis du lockup « MON DEVIS » / « Déménagement » en
Roboto Slab 600 et 800.

Les fichiers livrés ont été **remis en état de production** :

- **La police est embarquée.** Les SVG d'origine n'avaient aucun `font-family`.
  Chargé via `<img>`, un SVG n'a pas accès aux polices de la page : le texte
  serait retombé sur une serif système. Roboto Slab est donc sous-ensemblée aux
  seuls glyphes du logo (4,3 Ko contre 34 Ko) et intégrée en base64 — les
  fichiers sont autonomes et rendent partout à l'identique.
- **Le texte a une couleur.** Aucun `fill` n'était défini : sur la variante
  sombre, le texte serait resté noir, donc invisible sur le navy.
- **7,7 Ko de métadonnées C2PA retirés** de chaque fichier.

L'accent du logo, `#FF6F80`, est devenu l'accent de toute la page : deux rouges
voisins auraient fini par diverger.

Le favicon n'a pas de texte, il reste donc un fichier autonome sans traitement
particulier.

### Le schéma des « kilomètres aller »

Deux barres dont la **longueur** porte l'argument : le déménageur isolé facture
deux fois la route, nous une seule. Le rapport est **exactement 2 pour 1**, par
largeurs explicites de 50 % — avec `flex:1` il tombait à 1,91, l'élément vide ne
portant pas le même rembourrage que le segment.

Le rose ne marque plus que le bon scénario. Dans la version précédente il
colorait ce qui vous est facturé **dans les deux cas**, si bien que l'œil ne
distinguait pas le problème de la solution — et rien ne montrait l'économie. Le
trajet à vide est désormais hachuré&nbsp;: il se lit comme du poids mort.

### La carte de France

Un **SVG**, pas une image : net à toutes les tailles, aux couleurs de la charte,
et animable.

Le tracé vient du jeu de données ouvert
[france-geojson](https://github.com/gregoiredavid/france-geojson) (ODbL,
données IGN), projeté en **Mercator** — celle de toutes les cartes en ligne,
donc la forme que l'œil attend — puis simplifié par **Douglas-Peucker** à
environ 1 px près : **18,8 Ko au lieu de 68**, soit −73 % sans différence
visible à cette échelle.

**Un point par département** — les 96 de métropole — placés au *centroïde
d'aire* de l'anneau principal de chaque département, plus juste que la moyenne
des sommets qui se laisse tirer par les côtes découpées. Ils se posent en
cascade à l'entrée dans l'écran.

Au survol, la région passe au magenta. Le groupe des points est en
`pointer-events:none`, sans quoi il capterait le survol à la place de la région
qui le porte.

> **Piège rencontré, à ne pas refaire.** Les points portaient leur position en
> attribut `transform="translate(…)"` et l'animation en CSS `transform:scale()`.
> Or **le transform CSS écrase l'attribut** : les points se sont tous empilés à
> l'origine du SVG, formant une tache rose en haut à gauche. La position vit
> désormais sur un `<g>` extérieur et l'animation sur un `<g>` intérieur.
>
> Second piège : l'observateur visait le `<g>` des points, dont la boîte était
> collabée à **6 × 6 px** — un groupe SVG n'a pas de boîte de mise en page
> fiable. Il vise maintenant le conteneur HTML `.carte__wrap` (520 × 501).

**Vérification géométrique** : les 30 pastilles ont été testées une à une avec
`isPointInFill` contre les tracés de régions — toutes tombent à l'intérieur.
C'est la preuve que la projection du contour et celle des villes coïncident ;
une erreur de projection aurait fait flotter les villes hors des terres.

> Attribution ODbL : le jeu de données d'origine doit rester crédité. Un
> commentaire le fait dans le SVG.

### Les avatars d'avis

**Des initiales, pas des portraits.** Les avis cités sont ceux de personnes
réelles, nommées sur Trustpilot ; leur attribuer un visage généré inventerait
leur apparence. C'est aussi le parti de Trustpilot lui-même. La teinte de
l'avatar est dérivée du nom, donc stable d'un chargement à l'autre.

Pour de vrais portraits, il faut l'accord écrit de chaque personne citée.

### Les images

Quatre photos générées pour le projet (hero + trois étapes), dans un registre
commun : intérieurs français clairs, lumière naturelle, aucun visage, aucun
texte, aucune marque sur le camion.

Les trois images d'étapes font **3:2 à ratio fixe**, ce qui aligne les cartes
quelle que soit la longueur du texte, et sont en `loading="lazy"` —
elles sont loin sous la ligne de flottaison. Entre 43 et 69 Ko chacune.

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

## Les avis

Relevés sur la [page Trustpilot de MatchMove](https://fr.trustpilot.com/review/matchmove.fr),
cités tels que publiés. Trois sur la page d'accueil, deux sur `/merci` — c'est
le moment où le visiteur vient d'engager sa demande, donc celui où une preuve
pèse le plus.

**La note du profil est affichée telle quelle** (4,3/5 sur 202 avis), et non la
moyenne des avis montrés. Sélectionner des avis positifs sans donner la note
réelle reviendrait à maquiller le résultat — et le profil Trustpilot est public,
donc vérifiable en un clic.

> Note et nombre d'avis sont figés dans le HTML : ils ne se mettent pas à jour
> tout seuls. À rafraîchir en même temps que les citations.

## Mobile

Audité par mesure à **320, 360, 375, 414 et 768 px**, sur les cinq pages.
Critères vérifiés à chaque largeur : débordement horizontal, texte tronqué,
champs sous 16 px (iOS zoome au focus en dessous), texte sous 12 px, et zones
de frappe sous 30 px.

Ce que l'audit a trouvé et corrigé :

| Problème | Cause |
| --- | --- |
| Libellé du bouton collant **tronqué** à 320 px | 232 px de contenu pour 225 disponibles — capitales interlettrées |
| CTA de section à 295 px dans un conteneur de 284 | 44 px de rembourrage de chaque côté |
| **197 px de débordement** sur la page confidentialité | `<li>` en flex : `min-width:auto` empêche de se rétrécir sous un `<code>` insécable |
| Liens du pied de page à 16 px de haut | Pas de rembourrage vertical |
| Libellés du schéma à 11,5 px | Règle résiduelle de l'ancien schéma, `width:64px` comprise |

Le formulaire reste **au-dessus de la ligne de flottaison** à toutes les
largeurs testées (première option entre 591 et 693 px), ses champs font 55 px
de haut et 16 px de corps — pas de zoom automatique sur iOS.

**Aucun alignement en dur dans le HTML.** Un `style="text-align:left"` ne peut
pas être surchargé par une requête média : l'appel à l'action de la section
« kilomètres » restait collé à gauche une fois la section passée en une
colonne. Il est désormais porté par `.sec-cta--g`, qui n'aligne à gauche
qu'au-dessus de 951 px — le seuil de la section elle-même.

> `page.css` est appelée avec `?v=2`. Sans build qui hache les noms de
> fichiers, **il faut incrémenter ce numéro à chaque modification du CSS**,
> sinon les visiteurs déjà venus gardent l'ancienne feuille. C'est exactement
> ce qui a masqué un correctif pendant cet audit.

## Animations

Deux propriétés seulement — `opacity` et `transform` — donc tout reste sur le
compositeur, sans recalcul de mise en page. Un seul `IntersectionObserver` pour
la page entière, et chaque élément cesse d'être observé dès qu'il est apparu.

- **Apparition au défilement** des en-têtes de section et des grilles, les
  enfants en cascade (70 ms d'écart).
- **Les barres du schéma** se déploient depuis la gauche&nbsp;: la longueur
  étant l'argument, la voir se construire vaut mieux que la découvrir figée.
- **Compteurs** sur les deux chiffres du bandeau de preuve, avec décélération.
- **Boutons**&nbsp;: élévation de 2 px, flèche qui avance de 4 px, et un reflet
  oblique qui traverse le bouton en 0,6 s.

**Trois garde-fous**, parce qu'une animation ratée sur une page de conversion
coûte plus cher qu'une page sans animation&nbsp;:

1. La classe `js-anim` n'est posée **que par le script**. Sans JavaScript, rien
   n'est masqué.
2. Ce qui est **déjà à l'écran au chargement** est révélé immédiatement, sans
   passer par l'observateur.
3. Si l'observateur n'a **rien émis au bout de six secondes**, `js-anim` est
   retirée et tout redevient visible. Testé.

`prefers-reduced-motion: reduce` désactive l'ensemble, reflet compris.

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
- [x] ~~Téléphone et horaires~~ — renseignés depuis matchmove.fr
      (04 51 42 04 47, lundi-samedi 8h-18h).
- [x] ~~Avis clients~~ — avis réels relevés sur Trustpilot, avec la note du
      profil (4,3/5 sur 202 avis). **À rafraîchir périodiquement** : la note et
      le nombre d'avis sont figés dans le HTML, ils ne se mettent pas à jour
      seuls. Ils vivent dans le tableau `AVIS` d'`index.html` et de
      `merci.html`, plus l'en-tête de la section avis.
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
