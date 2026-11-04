# kcalis-site

Site vitrine et pages légales de l'application Kcalis, publié par GitHub Pages sur https://kcalis.app (branche `main`, racine).

Site 100 % statique : HTML et CSS, sans framework, sans étape de construction, sans JavaScript, sans cookie ni traceur, sans ressource externe.

## Fichiers

| Fichier | Rôle |
| --- | --- |
| `index.html` | Accueil |
| `confidentialite.html` | Politique de confidentialité |
| `conditions.html` | Conditions d'utilisation |
| `mentions-legales.html` | Mentions légales |
| `support.html` | Aide (questions fréquentes) |
| `404.html` | Page introuvable |
| `assets/style.css` | Feuille de style unique (aucun style inline : la CSP l'interdit) |
| `assets/og.png` | Image de partage (1200 × 630), logo sur fond clair |
| `favicon-32.png`, `apple-touch-icon.png` | Icône d'onglet (32 px) et icône d'écran d'accueil (180 px) |
| `app-ads.txt` | Déclaration AdMob |
| `robots.txt`, `sitemap.xml` | Référencement |
| `.well-known/security.txt` | Contact sécurité (à renouveler avant le 4 novembre 2027) |
| `.nojekyll` | Indique à GitHub Pages de publier `.well-known` |
| `CNAME` | Domaine personnalisé |

## Modifier le site

- L'en-tête, le pied de page et le `<head>` sont recopiés dans chaque page : une modification doit être faite dans toutes les pages.
- Ne jamais ajouter d'attribut `style`, de balise `<style>`, de script ni de ressource venant d'un autre domaine : la politique de sécurité (CSP) de chaque page les bloquerait.
- Les valeurs à fournir sont marquées `[à compléter]` (classe CSS `todo`). Pour les retrouver : `grep -n "à compléter" *.html`.
- Après une modification d'une page légale, mettre à jour la date « Dernière mise à jour » et `lastmod` dans `sitemap.xml`.
- Logo : tant que son fichier n'est pas dans le dépôt, l'en-tête affiche le mot « Kcalis » en texte noir (classe `brand`), et `favicon-32.png`, `apple-touch-icon.png` et `assets/og.png` sont des versions provisoires tirées de ce texte. Quand le fichier arrive : le mettre dans `assets/`, remplacer le texte de `brand` par l'image (avec `alt="Kcalis"`) dans chaque page, et refaire les trois images à partir du logo.
- Animations : uniquement sur `transform` et `opacity`, pilotées par le défilement (`animation-timeline`) et déclarées seulement dans `@supports (animation-timeline: view())` et `@media (prefers-reduced-motion: no-preference)`. Sans cette fonction, ou avec « Réduire les animations », rien ne bouge et tout reste lisible.
- Téléphone de l'accueil : il reste au centre de la scène. Son écran montre les captures de l'app quand il y en a (`assets/captures/capture-1.webp`…, 590 px de large, 150 Ko au plus, texte alternatif qui décrit l'écran, aucune autre marque que Kcalis), sinon le logo sur fond blanc ; jamais de fausse interface. L'agrandissement final (`--zoom-end`) dépend des proportions de l'écran : si la taille du téléphone (`--ph`) change, il faut le recalculer.
- Verre dépoli : chaque élément a d'abord un fond opaque, remplacé par le verre translucide dans `@supports (backdrop-filter)`. Tout couple texte/fond doit rester au contraste AA, y compris sur le verre.
- Tableaux des pages légales : chaque cellule `<td>` porte un `data-label` (titre de sa colonne), affiché quand le tableau devient une liste de cartes sous 600 px.
