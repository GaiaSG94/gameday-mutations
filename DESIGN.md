# DESIGN — Mutations (gameday-mutations)

> Journal de design. Versions datées, jamais écrasées. Tenu par Claude (directeur artistique), à partir de `PROMPT-DESIGN.md`.

## V2.1 — 2026-11-18 · `/lock`

**Statut : style verrouillé, fin des explorations.** Validation de Gaia : « Validé, lock ».

### Planches de référence (à implémenter)
| Page | Planche |
|------|---------|
| Post | `G-DESIGN/planches/v1/p1-post.html` |
| Jeu | `G-DESIGN/planches/v1/02b-nocturne-electrique.html` |
| Carte de fin | `G-DESIGN/planches/v1/p3-carte-de-fin.html` |
| Séries & classement | `G-DESIGN/planches/v1/p4-series-classement.html` |

Règles : `G-DESIGN/STYLE.md`. Les planches d'exploration 01, 02 et 03 restent dans le dossier pour l'historique ; elles ne font plus foi.

### Reste ouvert pour l'implémentation (décisions produit, pas de style)
Questions 1 à 7 de `G-DESIGN/PAGES.md` (traits par génération, écart ancêtre / cible, % visible en cours de partie, génération définitive, données communautaires, départage des égalités, commentaire posté par le joueur). Les planches les dessinent selon l'hypothèse notée ; changer la réponse ne change pas le style.

## V2 — 2026-11-18 · Étape C : style verrouillé sur 02b, déclinaison des pages

**Statut : en revue (3 nouvelles planches).** Validation de Gaia : « Oui, étape C » sur 02b Nocturne électrique.

### Fait
- `G-DESIGN/STYLE.md` : palette avec hex, échelle typo (deux voix, jamais de gras), grille desktop / mobile / aperçu feed, composants, mouvement, règles d'états, interdits propres au style.
- `G-DESIGN/planches/v1/p1-post.html` : aperçu dans le feed (736 × 420 / 390 × 420). L'ancêtre du jour, une flèche « 5 generations », la grande ombre de l'espèce. États : à jouer, en cours, déjà joué (% + compte à rebours), chargement.
- `G-DESIGN/planches/v1/p3-carte-de-fin.html` : espèce finale sur l'ombre, partie ratée cerclée en pointillé acide, 88 %, rang 612 / 2 184, top 28 %, série 07 (+1), lignée en 5 vignettes, commentaire sans spoiler (`Mutations 047 · 88% · ■■■■□ · streak 7`), prochaine lignée dans 08:14:32.
- `G-DESIGN/planches/v1/p4-series-classement.html` : série (07, record 12, calendrier de 4 semaines), histogramme des % du jour avec ta tranche en acide et la médiane, classement du jour trié par correspondance puis série, ta ligne toujours visible. Sur mobile : onglets « Today / Streak ».

### Décisions
- Ombre cible : filtre remplacé (flou 3 + opacité ×1,7 au lieu d'une dilatation + flou), qui laissait des rayures quand l'ombre est seule à l'écran. Appliqué aussi à 02b pour rester identique.
- Données de démo prolongées : à la génération V le joueur choisit « Brow horns » au lieu de la crête → 4 traits sur 5, 88 %.
- Un seul bouton plein par écran : « Start breeding », « Post to comments », « Discuss today ». L'action communautaire renvoie toujours vers les commentaires du post.
- Acide réservé à : mutation, point de série, case du jour, ta tranche, ta ligne, anneau de la partie ratée.

### Questions ouvertes (nouvelles)
- Départage des égalités à 100 % dans le classement (dessiné : série la plus longue d'abord).
- Classement visible avant d'avoir joué ? (dessiné : verrouillé.)
- Le commentaire est posté par le joueur (pas de post automatique) : à confirmer côté Devvit.
- Onglet « Streak » mobile et classement des séries au long cours : non dessinés, à décider.

### Suite
Quand les 4 planches sont validées (Post, Jeu = 02b, Carte de fin, Séries & classement) → `/lock`.

## V1.1 — 2026-11-18 · Retour de Gaia : « le deuxième avec style bleu flashy »

**Statut : en revue (une planche, variante de 02).** V1 reste en place, rien n'est écrasé.

### Fait
- `G-DESIGN/planches/v1/02b-nocturne-electrique.html` : la mise en scène de 02 (cible = ombre floue, espèce = forme éclairée, cadres en pointillé, grotesque fin + mono), passée dans le bleu électrique de 03.

### Décisions
- Fond bleu électrique `#2234f5`, halo `#5463ff` derrière le spécimen, ombre cible bleu nuit `#0a1075`, texte crème `#f6f1e6`.
- La forme éclairée va du blanc au bleu nuit (`#ffffff → #9ea6ff → #0c1270`), la lumière vient d'en haut à droite.
- Accent unique : le jaune acide `#e4ff3c` de 03 remplace l'ambre de 02, réservé à la mutation choisie (et au point de série).
- Ombre cible foncée de `#0f188f` à `#0a1075` après vérification : la crête manquante était trop faible sur le bleu.

### À valider
Si 02b est retenue, elle devient le style de référence : étape C (`G-DESIGN/STYLE.md`, puis les planches Post, Carte de fin et Séries & classement).

## V1 — 2026-11-18 · Exploration de la page principale (« Jeu »)

**Statut : en attente de validation de Gaia (étape B du process, on s'arrête ici).**

### Fait
- `G-DESIGN/REFS.md` : Primal Instinct ouvert et décodé (l'ombre avant la forme, lumière sur une seule partie, grotesque + mono, chrome en pointillé). **Sponge (`sponge.com`) inexploitable** : le domaine redirige vers une page de revente. URL à fournir.
- `G-DESIGN/PAGES.md` : 4 pages proposées (Post, Jeu, Carte de fin, Séries & classement), à valider, avec 5 questions produit ouvertes.
- 3 planches de la page **Jeu**, chacune avec le cadre desktop 1440 × 900 (post ouvert dans un feed neutre) et le cadre mobile 390 × 844, plus une bande d'états des composants :
  - `G-DESIGN/planches/v1/01-cabinet.html` : la direction du brief poussée au bout. Planche gravée os / vert profond, cible hachurée, espèce à l'encre, mutation en rose, arbre des traits avec les choix écartés.
  - `G-DESIGN/planches/v1/02-nocturne.html` : d'après Primal Instinct. Noir pierre, la cible est une ombre floue, l'espèce est une forme éclairée, la mutation s'allume en ambre.
  - `G-DESIGN/planches/v1/03-field.html` : s'écarte du brief. Champ cobalt plein cadre, espèce énorme en noir sur la découpe bleu nuit de la cible, accent jaune acide, panneau crème façon produit lancé.

### Données de démo communes
Lignée Nº 047, mardi 18 nov. Ancêtre commun : corps allongé, sans pattes, cou court. Cible : quatre pattes, cou long, épines dorsales, queue éventail, crête. Gén. I quatre pattes, II cou long, III épines (61 % de correspondance, médiane du jour 74 %). État figé : choix de la génération IV, « Fan tail » sélectionnée et prévisualisée sur la scène, leurres « Whip tail » et « Brow horns ». Série de 6 jours, 2 184 éleveurs.
Les silhouettes sont générées par le même petit script dans les trois planches (un vecteur de traits → une silhouette), pour que la comparaison porte sur le style et pas sur le dessin.

### Décisions
- Feed hôte dessiné en gris neutre, sans logo ni Snoo ni karma (critère Reddit-y « pas on the nose »).
- Zéro dépendance réseau : piles de polices système/libres. Les polices définitives seront embarquées dans l'app à l'étape C.
- UI en anglais ; planches annotées en français.
- Le % de correspondance n'est montré qu'après chaque génération, jamais avant de choisir (sinon le puzzle disparaît). À confirmer (question 3 de `PAGES.md`).

### Choix recommandé
**01 — Cabinet.** Pourquoi : c'est la seule où la règle se lit en 5 secondes sans légende (hachure = cible, encre = toi, rose = ce qui change). L'arbre des traits donne une matière à commenter (« j'ai écarté la queue éventail en III »), ce qui sert directement le critère Reddit-y.
02 est la plus singulière, mais sa lisibilité dépend d'un rendu de lumière qui sera fragile sur mobile. 03 est la plus « produit lancé » et la plus visible dans un feed, mais elle perd l'étrangeté qui distingue le jeu des autres puzzles du jour.
Piste possible : 01 avec le spécimen en grand format et le panneau « bottom sheet » mobile de 03 (`/compare 01 03`).

### Questions ouvertes (bloquantes pour l'étape C)
Voir `G-DESIGN/PAGES.md` §« Questions produit ouvertes » : nombre de traits proposés par génération, ancêtre et cible à exactement 5 traits d'écart, % visible pendant la partie, génération validée définitive, données communautaires affichées. Et l'URL réelle de la référence Sponge.
