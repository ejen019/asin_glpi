# Journal des modifications (GLPI2)

Date de départ : 2026-03-12

## Note AMM
JE centralise ici les changements faits sur GLPI2 avec des phrases courtes et claires.

## 2026-03-12
- JE crée le dossier `/var/www/html/glpi2`.
- JE décompresse GLPI `10.0.16` dans ce dossier.
- JE crée la palette `oceanic` dans `css/palettes/oceanic.scss`.
- JE ajoute `css/includes/_premium_overrides.scss` pour le style login, menu, topbar, boutons et cartes.
- JE ajoute un aperçu de palette `oceanic.png`.
- JE copie les logos ASIN et le favicon dans `pics/`.
- JE configure Apache sur le port `8081` avec un vhost pour GLPI2.
- JE donne les droits nécessaires à Apache pour `config/`, `files/` et `marketplace/` pendant l’installation.
- JE crée la base `glpi2` et l’utilisateur SQL `glpi2_user`.
- JE ajuste plusieurs fois le rendu visuel : sidebar, topbar, hover, menu replié, logo, dashboard.
- JE personnalise la page login (logo, mise en page, footer, lien mot de passe oublié).
- JE remplace le texte “Interface standard” par “Interface standard ASIN-GLPI” dans les locales FR.

## 2026-05-11
- JE masque le choix de source d’authentification sur la page login.
- JE force l’authentification locale via un champ caché `auth=local`.
- JE modifie le footer login en `ASIN-2026`.
- JE corrige le lien “Mot de passe oublié ?” avec la bonne syntaxe Twig.
- JE corrige le cas de page vide dans `front/lostpassword.php`.
- JE garde le lien de récupération visible sur la page login.
- JE ajuste l’UI de la page “Mot de passe oublié” (icône, espacements, bouton retour).
- JE traduis en français les textes visibles des pages login et récupération.

## Fichiers principaux modifiés
- `css/palettes/oceanic.scss`
- `css/includes/_premium_overrides.scss`
- `templates/pages/login.html.twig`
- `templates/password_form.html.twig`
- `front/lostpassword.php`
- `pics/logos/logo-asin-colors.png`

## Note AMM (suite)
JE continuerai à tenir ce journal à chaque changement important.
