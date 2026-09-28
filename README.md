# Transaction · emlyon

Site de **Transaction**, l'association finance d'emlyon business school (« Transaction · emlyon — Finance Student Club ») : les projets de l'asso, dont **Le Salon**, l'agenda, l'équipe, les partenaires et le recrutement.

Un seul fichier, `index.html` : HTML, CSS et JavaScript, sans framework ni étape de compilation. Seule dépendance externe : Google Fonts.

## Fichiers

| Fichier | Rôle |
|---|---|
| `index.html` | Le site complet |
| `assets/logo-transaction.png` | Le médaillon de l'asso (aussi utilisé comme favicon) |
| `assets/logo-le-salon.svg` | L'arche du Salon |

## Voir le site

Ouvre `index.html` dans un navigateur. Pour un rendu identique à la mise en ligne, sers le dossier avec un petit serveur local :

```bash
python3 -m http.server 8000
```

puis va sur http://localhost:8000.

## Modifier le contenu

Tout ce qui change est regroupé dans l'objet `DATA`, en haut du `<script>` de `index.html` ; les listes du site sont générées à partir de lui.

- `asso` : e-mail, liens Instagram et LinkedIn, adresse, formulaire et période de candidature, mentions légales.
- `chiffres` : remplace `valeur: null` par un nombre ; le chiffre compte jusqu'à sa valeur à son apparition.
- `projets` : ajouter un projet = ajouter une entrée. Son `id` donne l'adresse partageable de sa fiche (`#projet-le-salon`). `provisoire: true` affiche « [Projet à valider] ».
- `agenda` : dates au format `AAAA-MM-JJ` ; les rendez-vous sont triés et les dates passées disparaissent seules.
- `temoignages`, `equipe`, `partenaires`, `faq`.

Règle : ce qui n'est pas confirmé reste **[entre crochets]**. Un lien entre crochets affiche « Lien à venir » au clic, au lieu d'une page introuvable.

## Avant la mise en ligne

- Remplacer tous les contenus [entre crochets] : chiffres, dates, noms, liens, témoignages, partenaires.
- Faire valider, remplacer ou retirer les huit projets proposés.
- Brancher l'envoi de la newsletter (fonction `initNewsletter`) et ajouter la mention RGPD sous le champ.
- Ajouter la vidéo du Salon dans `assets/lesalon.mp4`, puis indiquer `video: "assets/lesalon.mp4"` dans le projet `le-salon`.
- Une fois le domaine connu, donner à `og:image` une adresse absolue.

## Mettre en ligne

Le dossier se publie tel quel.

- **GitHub Pages** : Settings → Pages → Deploy from a branch → `main`, dossier `/ (root)`.
- **Netlify** : glisser-déposer le dossier sur https://app.netlify.com/drop.
