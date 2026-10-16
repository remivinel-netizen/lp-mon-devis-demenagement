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

1. **Le retour à vide** — le levier de prix le plus fort du secteur, et le plus
   mal expliqué. Il a sa propre section, avec un schéma, parce qu'il ne se
   comprend pas en une ligne. Formulé comme un **mécanisme** et comme ce que le
   conseiller cherche à obtenir, non comme une garantie de facturation — voir
   plus bas.
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

### Le schéma du retour à vide

**Une seule barre, coupée en deux.** La piste entière vaut l'aller-retour, soit
1 380 km&nbsp;; l'incrustation rose vaut ce qui est facturé quand le camion
passait déjà par là. Le rapport est **exactement 2 pour 1**, mesuré à 0,500.

La version précédente empilait deux barres et faisait lire **huit zones de
texte** avant que l'argument n'arrive&nbsp;: un titre, deux libellés de ligne,
deux kilométrages, deux étiquettes dans les barres, un paragraphe. Elle
demandait aussi de décoder « aller chargé » et « retour à vide » — deux notions
de transport — pour comprendre qu'on paie la route deux fois. On en est à
quatre zones, et le rapport se voit sans compter.

Le fond hachuré porte désormais la piste entière, et non plus un segment&nbsp;:
l'étiquette de droite ne bouge donc jamais pendant que le rose se déploie.
C'est la **largeur** qui est animée, pas une mise à l'échelle — un `scaleX`
déformait le texte à l'intérieur pendant toute la transition.

### Pourquoi « le retour à vide » et non « vous ne payez que l'aller »

La page portait, en huit endroits, la promesse **« Vous ne payez que les
kilomètres aller »**. Elle venait telle quelle d'officiel-demenagement.com.
Elle n'est étayée **nulle part** sur matchmove.fr&nbsp;: ni groupage, ni mode
de facturation, ni tournées.

C'est une promesse de **prix**. Un client qui la lit, puis reçoit un devis
facturant l'aller-retour, a un grief fondé — et l'écart entre la promesse et la
facture relève de la pratique commerciale trompeuse. Le risque n'est pas
éditorial, il est juridique, et il porte sur le client final.

La section décrit donc le **mécanisme**, qui est vrai quel que soit le
déménageur&nbsp;: un camion mobilisé pour une seule famille doit rentrer, et ce
retour est facturé même à vide&nbsp;; un camion qui passait déjà par là repart
chargé par un autre client. Et elle dit ce que le conseiller **cherche à
obtenir** sur les mille déménageurs du réseau, sans le garantir sur chaque
trajet. Le schéma, lui, est inchangé dans sa démonstration.

Le titre annonce le **service** — « On cherche le camion qui passe déjà par
votre route » — et non le problème subi. Un titre qui ouvre sur ce que le
visiteur paie en trop le met en défense avant d'avoir lu la solution&nbsp;; le
retour à vide reste expliqué dans le paragraphe qui suit, à sa place de
mécanisme.

Si MatchMove garantit contractuellement l'aller seul, la formulation ferme peut
revenir partout&nbsp;: un commentaire dans `index.html` indique où.

### Ce que la section « qualité » affirme, et d'où ça vient

Tout ce qu'affirme la section `#qualite` relève du **droit français applicable à
toute entreprise de déménagement**, et non d'un engagement propre à MatchMove —
inscription au registre national des entreprises et au registre des
transporteurs et des loueurs, licence de transport, responsabilité civile
professionnelle, mentions obligatoires du devis, déclaration de valeur, et le
délai de **dix jours** pour confirmer des réserves par lettre recommandée avec
accusé de réception.

Vérifié sur [service-public.gouv.fr](https://www.service-public.gouv.fr/particuliers/vosdroits/F33997)
et sur [ecologie.gouv.fr](https://www.ecologie.gouv.fr/politiques-publiques/acces-exercice-profession-transporteur-marchandises).

C'est un choix de différenciation autant que de prudence&nbsp;: l'audit de
`lesartisansdemenageurs.fr` et `demenagement24.com` montre qu'**aucun des deux
ne publie d'engagement d'assurance, de montant de couverture, ni de voie de
recours**. Expliquer les droits du client là où les concurrents se taisent
coûte zéro promesse et construit la préférence.

Dès que matchmove.fr fournit un assureur, un montant de couverture et des
critères de sélection des partenaires, c'est dans cette section qu'ils
viennent — et l'écart devient difficile à rattraper.

### Rompre le mur de cartes

Quatre sections se suivaient avec la même grille — « Inclus dans les trois
formules », « Votre déménagement n'est pas standard », « Un interlocuteur » et
« Un métier réglementé » — soit **dix-sept cartes consécutives** au même
gabarit : icône nue de 25 px, titre, paragraphe. À l'échelle de la page cela
formait un mur que l'œil cesse de lire.

Trois leviers, aucun n'ajoutant de poids notable :

1. **Des médaillons plutôt que des icônes nues.** Pastille de 46 px, et une
   teinte par section : rose pâle sur « Inclus », bleu nuit sur les cas
   particuliers, blanc translucide sur la section sombre. Les grilles cessent
   de se ressembler à distance.
2. **Une photo dans la section support**, qui passe en deux colonnes. C'est la
   section la plus humaine de la page, autant qu'elle le montre.
3. **Un fond sombre sur la section qualité.** Après trois sections claires,
   c'est le changement de valeur qui redonne du rythme — et il va au propos.
   L'accent du titre y passe du magenta au rose : le magenta ne tient que
   **2,47:1** sur le bleu nuit, sous le seuil de 3:1 exigé même pour du grand
   texte, là où le rose atteint 5,16:1. Contrastes mesurés sur le reste :
   13,82:1 pour le titre, 8,28:1 pour le chapô, 11,68:1 et 6,65:1 dans les
   cartes, 6,30:1 pour la mention sous le bouton.

Les fonds de section alternent désormais blanc, gris, blanc, gris foncé, nuit,
rose. « Inclus » et « Cas particuliers » se suivaient auparavant sur deux gris
séparés d'un demi-pour-cent de luminance — la transition ne se voyait pas.

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

Huit photos générées pour le projet (hero, trois étapes, trois de galerie, une
de support), dans un registre commun : intérieurs français clairs, lumière
naturelle, **aucun visage**, aucun texte, aucune marque sur le camion.

Pas de visage, c'est une règle et non une préférence : un visage généré invente
une personne, et sur une page qui parle de conseillers réels cela reviendrait à
mettre un faux employé en vitrine. La photo de la section support montre donc un
poste de travail — casque, carnet, ordinateur — et pas quelqu'un qui le
tiendrait.

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

Cinq étapes, dans cet ordre :

1. **Adresse de départ** — adresse, code postal, ville
2. **Adresse d'arrivée** — idem
3. **Date de déménagement** — jour précis
4. **Surface du logement actuel** — six tranches, de « moins de 30 m² » à
   « plus de 180 m² », avec le volume indicatif affiché
5. **Coordonnées** — prénom, nom, téléphone, e-mail, consentement

Ce découpage **reprend celui d'officiel-demenagement.com**, dont le formulaire
est un Typeform à cinq écrans : mêmes questions, même ordre, mêmes intitulés.
Trois qualifications que nous posions auparavant ont disparu avec lui —
**étage**, **ascenseur** et **formule souhaitée**. C'est le parti pris de leur
modèle : un formulaire court, et un conseiller qui complète au téléphone. La FAQ
et la première étape de « Comment ça se passe » annoncent d'ailleurs cet appel.

Nous gardons deux choses qu'ils n'ont pas. La **ville est renseignée
automatiquement** par le code postal, à partir du nom officiel de la commune :
une saisie de moins, et plus de faute de frappe sur la commune. Et la date
passe par un **champ date natif** plutôt que trois champs jour / mois / année,
ce qui vaut surtout sur mobile.

La **surface remplace le nombre de pièces** pour estimer le volume, selon la
table ci-dessous. Les deux donnent un ordre de grandeur, pas une mesure — c'est
le conseiller qui confirme.

| Surface | Volume affiché |
|---|---|
| Moins de 30 m² | 10 m³ |
| 30 à 50 m² | 18 m³ |
| 50 à 80 m² | 28 m³ |
| 80 à 120 m² | 40 m³ |
| 120 à 180 m² | 58 m³ |
| Plus de 180 m² | 80 m³ |

La **priorité commerciale** ne vient plus d'une tranche d'urgence choisie par le
visiteur mais du nombre de jours qui séparent de la date saisie :
`chaud` à 45 jours ou moins, `tiede` jusqu'à 120, `froid` au-delà. Une date
déjà passée est refusée à l'étape — c'est presque toujours une faute d'année.

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
**volume** et le **trajet** (« Environ 28 m³ — Lyon → Bordeaux, 544 km »).
Comme le volume n'arrive plus qu'à la quatrième étape, le panneau s'ouvre dès
que le trajet est connu, en affichant alors le kilométrage (« 544 km — de
trajet »). Il
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

Le payload JSON contient le projet (adresses, codes postaux, villes saisies et
communes reconnues, distance, date, surface, volume), la priorité
(`chaud` / `tiede` / `froid` selon l'échéance), le contact, la preuve de
consentement horodatée, et tous les identifiants publicitaires captés.
**Aucun champ de prix.**

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

La carte du formulaire reste **au-dessus de la ligne de flottaison** à toutes
les largeurs testées : son haut se situe entre 400 et 440 px, la première
question entre 501 px (412 de large) et 558 px (320 de large). Le premier champ
tombe entre 599 et 657 px, donc sous la ligne sur un écran de 568 px de haut —
c'est le prix de l'étape « adresse de départ », qui ouvre sur un champ de texte
là où l'ancienne première étape ouvrait sur des boutons radio. Les champs font
55 px de haut et 16 px de corps — pas de zoom automatique sur iOS. Débordement
horizontal mesuré à 0 px de 320 à 412.

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
- **La moitié facturée du schéma** se déploie sur la piste&nbsp;: la longueur
  étant l'argument, la voir se construire vaut mieux que la découvrir figée.
  Sans JavaScript, la barre est d'emblée à sa largeur finale.
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

- [ ] **Les promesses commerciales.** Cartons offerts, assurance du
      mobilier comprise, changement d'adresse pris en charge. Elles sont reprises
      du modèle de l'Officiel du Déménagement et **structurent toute la page** —
      hero, bandeau, section dédiée, formules, services offerts, FAQ, page
      `/merci`. Elles n'ont de valeur que si le réseau les honore réellement. Un
      bloc `⚠ À VALIDER` les signale dans `index.html`. **Soit on les confirme,
      soit on les retire partout à la fois** — une promesse à moitié tenue coûte
      plus cher qu'une
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
