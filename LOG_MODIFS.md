# Journal des modifications (GLPI2)

Date de départ : 2026-03-12

## Note AMM
Centralisation des changements faits sur GLPI2 avec des phrases courtes et claires.

## 2026-03-12
- Creation du dossier `/var/www/html/glpi2`.
- Decompression de GLPI `10.0.16` dans ce dossier.
- Creation de la palette `oceanic` dans `css/palettes/oceanic.scss`.
- Ajout de `css/includes/_premium_overrides.scss` pour le style login, menu, topbar, boutons et cartes.
- Ajout d’un apercu de palette `oceanic.png`.
- Copie des logos ASIN et du favicon dans `pics/`.
- Configuration d’Apache sur le port `8081` avec un vhost pour GLPI2.
- Attribution des droits necessaires a Apache pour `config/`, `files/` et `marketplace/` pendant l’installation.
- Creation de la base `glpi2` et de l’utilisateur SQL `glpi2_user`.
- Ajustements visuels successifs : sidebar, topbar, hover, menu replie, logo, dashboard.
- Personnalisation de la page login (logo, mise en page, footer, lien mot de passe oublie).
- Remplacement du texte “Interface standard” par “Interface standard ASIN-GLPI” dans les locales FR.

## 2026-05-11
- Masquage du choix de source d’authentification sur la page login.
- Forcage de l’authentification locale via un champ cache `auth=local`.
- Modification du footer login en `ASIN-2026`.
- Correction du lien “Mot de passe oublie ?” avec la bonne syntaxe Twig.
- Correction du cas de page vide dans `front/lostpassword.php`.
- Conservation du lien de recuperation visible sur la page login.
- Ajustement de l’UI de la page “Mot de passe oublie” (icone, espacements, bouton retour).
- Traduction en francais des textes visibles des pages login et recuperation.

## 2026-05-16
- Francisation des textes restants en anglais sur les ecrans de connexion et de recuperation du mot de passe.

## Fichiers principaux modifiés
- `css/palettes/oceanic.scss`
- `css/includes/_premium_overrides.scss`
- `templates/pages/login.html.twig`
- `templates/password_form.html.twig`
- `front/lostpassword.php`
- `pics/logos/logo-asin-colors.png`

## Note AMM (suite)
Mise a jour continue de ce journal a chaque changement important.
