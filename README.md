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
| `assets/og.png` | Image de partage (1200 × 630) |
| `favicon.svg`, `apple-touch-icon.png` | Icônes |
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
- Animations : uniquement sur `transform` et `opacity`, déclarées dans `@media (prefers-reduced-motion: no-preference)`. Avec « Réduire les animations », plus rien ne bouge.
- Téléphone de l'accueil : sans capture, son écran montre seulement l'icône (`favicon.svg`) sur fond `#050506`. Les captures d'écran de l'app vont dans `assets/captures/` (`capture-1.webp`, `capture-2.webp`…, 590 px de large, 150 Ko au plus), avec un texte alternatif qui décrit l'écran montré ; jamais de fausse interface.
- Verre dépoli : chaque élément a d'abord un fond opaque, remplacé par le verre translucide dans `@supports (backdrop-filter)`. Tout nouveau couple texte/fond doit rester au contraste AA, y compris sur le verre.
- Tableaux des pages légales : chaque cellule `<td>` porte un `data-label` (titre de sa colonne), affiché quand le tableau devient une liste de cartes sous 600 px.
