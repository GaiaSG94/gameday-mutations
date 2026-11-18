# STYLE — Mutations · « Nocturne électrique » (02b)

> **VERROUILLÉ le 2026-11-18 (`/lock`, V2.1).** Fin des explorations : toute évolution passe par une nouvelle version datée dans `DESIGN.md`.
> Style de référence validé par Gaia (V1.1 → étape C).
> Source vivante : `G-DESIGN/planches/v1/02b-nocturne-electrique.html`.

## 1. Idée en une phrase

La cible du jour est une **ombre floue** au fond d'un champ bleu électrique ; l'espèce du joueur est la **forme éclairée** qui vient s'y poser ; seule la **mutation** s'allume en jaune acide.

## 2. Palette

| Rôle | Hex | Usage |
|------|-----|-------|
| Electric (fond) | `#2234f5` | Fond de tous les écrans du jeu, texte du bouton plein |
| Halo | `#5463ff` | Centre du halo radial de la scène uniquement |
| Bord de scène | `#1c2bd8` | Bord du halo radial |
| Ombre cible | `#0a1075` | Silhouette cible (dilatée 2,2 + flou 2,6) ; barres « communauté » dans les graphiques |
| Fond de vignette | `rgba(20,30,190,.45)` | Vignettes de lignée posées sur la scène |
| Crème | `#f6f1e6` | Texte principal, bouton plein, valeurs |
| Crème 78 % | `rgba(246,241,230,.78)` | Libellés mono |
| Crème 48 % | `rgba(246,241,230,.48)` | Texte tertiaire, dénominateurs (`/05`) |
| Trait | `rgba(246,241,230,.42)` | Cadres pointillés 1 px |
| Filet | `rgba(246,241,230,.16)` | Séparateurs pleins 1 px |
| **Acid (accent unique)** | `#e4ff3c` | Mutation choisie, point de série, repère « médiane », « toi » dans les classements. Jamais pour du texte courant. |

Éclairage du spécimen : dégradé linéaire `#ffffff → #9ea6ff (42 %) → #0c1270`, lumière en haut à droite (x1 215, y1 12 → x2 70, y2 150 dans le repère 240 × 150).
La mutation porte un halo : flou 3,5 fusionné sous la forme.

## 3. Typographie

Deux voix, jamais de gras.

| Rôle | Famille | Taille / graisse | Détail |
|------|---------|------------------|--------|
| Grand chiffre (% , génération) | Grotesque | 46–84 px / 300 | approche −0,04 em, unité à 22 px en crème 78 % |
| Mot-symbole « MUTATIONS » | Grotesque | 13–15 px / 400 | capitales, approche +0,22 em |
| Phrase / règle | Grotesque | 13,5–15 px / 400 | 2ᵉ moitié de phrase en crème 78 % |
| Libellé, mesure, bouton | Mono | 10–12 px / 500 | capitales, approche +0,08 à +0,12 em |

Piles des planches : grotesque `Helvetica Neue → Nimbus Sans → Liberation Sans → Arial` ; mono `SF Mono → Menlo → DejaVu Sans Mono`.
Dans l'app : embarquer une grotesque libre (Inter ou Familjen Grotesk, OFL) et une mono libre (JetBrains Mono ou Fira Code, OFL), sans appel réseau (CSP).

## 4. Grille

- **Desktop** (post déplié, embed 736 × 620) : en-tête 48 px · scène flexible · bande basse 196 px. Marges 18 px, gouttières 10 px.
- **Mobile** (embed 390 × 636) : en-tête 44 px · scène 250–292 px · contenu · bouton collé en bas avec 14 px de marge. Marges 14 px, gouttières 8 px.
- **Post dans le feed** (aperçu inline) : 736 × 420 desktop, 390 × 420 mobile.
- Les métadonnées vivent dans les **coins** de la scène (n° de lignée, génération, communauté) ; le centre est réservé au spécimen.

## 5. Composants

| Composant | Règle |
|-----------|-------|
| Scène | Halo radial 62 % × 58 % centré à 58 % / 44 %. Un seul spécimen, posé sur son ombre. |
| Ombre cible | Toujours alignée exactement sous l'espèce (jamais décalée), sinon la correspondance devient illisible. |
| Spécimen | Vecteur de traits → silhouette plate éclairée. Une seule partie peut être en acide à la fois. |
| Vignette de lignée | Cadre pointillé 1 px, 3 px de rayon ; « now » = trait acide plein ; « next » = 50 % d'opacité. |
| Tuile de trait | Pointillé → survol : plein crème 48 % → sélection : plein crème + fond crème 12 % + « SELECTED » en acide (point acide sur mobile). |
| Bouton plein | Crème, texte mono bleu, flèche grotesque 300 à droite, 48 px de haut, rayon 3 px. Un seul par écran. |
| Bouton secondaire | Pointillé crème, texte crème. |
| Chip | Pointillé, mono 10,5 px, point acide lumineux à gauche (série). |
| Barre de correspondance | Filet 1 px crème 48 % ; valeur 3 px crème ; repère médiane 1 × 11 px acide. |
| Graphiques communauté | Barres bleu nuit `#0a1075`, barre du joueur en acide, axe mono crème 48 %. |

## 6. Mouvement

- **Breed** : balayage de lumière sur le spécimen, 700 ms, ease-out ; la nouvelle partie pousse depuis le corps (scale 0 → 1, 450 ms), puis garde son acide jusqu'à la génération suivante.
- **%** : compte jusqu'à sa nouvelle valeur en 600 ms.
- **L'ombre ne bouge jamais.**
- Sélection d'une tuile : 120 ms, pas de rebond.
- `prefers-reduced-motion` : fondus de 150 ms seulement.

## 7. Règles d'états

- Rien choisi → bouton désactivé (pointillé, « Pick a trait »).
- Choisi → prévisualisation acide sur la scène + bouton plein.
- Pendant le breed → bouton acide « Breeding… », tuiles verrouillées.
- Génération passée → tuiles à 35 %.
- Partie finie → le post bascule sur la carte de fin, et la scène montre l'espèce finale sur l'ombre sans acide (sauf la partie manquée, cerclée en pointillé acide).
- Déjà joué aujourd'hui → l'aperçu du post affiche le % du joueur et « Next lineage in HH:MM:SS ».
- Chargement → ombre seule qui respire (opacité 60 → 100 %, 1,2 s), libellé mono « Growing lineage… ».

## 8. Interdits propres au style

- Pas de deuxième couleur d'accent ; pas d'acide sur du texte courant.
- Pas de graisse > 400 ; pas d'italique.
- Pas de dégradé hors halo de scène et éclairage du spécimen.
- Pas d'emoji, pas de Snoo, pas de karma, pas de logo.
