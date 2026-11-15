# CAP Bascule · site

Site d'une page, statique, publié avec GitHub Pages depuis la branche `main`.
Tout tient dans `index.html` : pas de build, pas de dépendance à installer.

Adresse actuelle : https://almosnishirley.github.io/CAP90/

L'ancien site CAP90 (offres Alerte, Prévention, Relais) est conservé dans le tag Git `cap90-archive`.

## Modifier les textes

Ouvrir `index.html` et chercher le texte à changer. Chaque section est précédée d'un commentaire numéroté :

| Commentaire | Section |
|---|---|
| `<!-- 1. HERO -->` | Titre, sous-titre, boutons, trois repères |
| `<!-- 2. SITUATIONS -->` | Liste des situations |
| `<!-- 3. ENJEUX -->` | Pourquoi ces situations s'enlisent |
| `<!-- 4. RÔLE -->` | Ce que CAP Bascule permet |
| `<!-- 5. FRISE -->` | Frise en quatre temps (dessin + cartes des étapes + parcours) |
| `<!-- 6. PARCOURS -->` | CAP Clarifier, CAP Traverser, CAP Rebond |
| `<!-- 7. CADRE / FINANCEMENT -->` | Entreprise / personne / CAP Bascule |
| `<!-- 8-9. BÉNÉFICES -->` | Ce que chacun y gagne |
| `<!-- 10. CONFIDENTIALITÉ -->` | Confidentialité et limites |
| `<!-- 11. NOUS -->` | Présentation, liens LinkedIn, cas clients (masqués) |
| `<!-- 12. FAQ -->` | Questions / réponses (un bloc `<details>` par question) |
| `<!-- 13. CONTACT -->` | Appel à l'action final |

Les noms des étapes affichés dans le dessin de la frise (CADRER, ÉCLAIRER…) sont dans la balise `<svg class="frise-svg">`.

**Afficher les cas clients** : dans la section 11, remplacer les textes entre crochets puis supprimer l'attribut `hidden` de `<div class="wrap cases" hidden>`.

**Ajouter une question à la FAQ** : copier une ligne `<details>…</details>` et changer la question (`<summary>`) et la réponse.

## Modifier les couleurs

En haut du fichier, dans `:root`, chaque couleur est une variable :

```css
--bg: #F5F0EA;      /* sable chaud : fond de page */
--surface: #FCFBF9; /* blanc cassé : sections et cartes */
--ink: #17232B;     /* encre : texte et bandes sombres */
--muted: #59636A;   /* gris texte */
--green: #2F6F63;   /* vert confiance : repères */
--coral: #ED6A52;   /* corail : bouton principal et point de bascule */
```

Le thème sombre (pour les visiteurs dont l'appareil est en mode sombre) est défini juste en dessous, dans deux blocs identiques. Changer les deux ensemble.

## Modifier les e-mails et les liens

En bas du fichier, dans le `<script>` :

```js
const TO = "shirley.chiche@buildrh.co", CC = "coralie@ellipse.cn.com";
const SUBJECT = "CAP Bascule · Une situation à clarifier";
const BODY = "…";
```

Tous les boutons portant l'attribut `data-mail` ouvrent cet e-mail pré-rempli.

Les liens LinkedIn sont dans la section 11 (`<a class="founder" href="…">`).

## Publier une modification

Chaque `git push` sur `main` met le site à jour en une minute environ.
