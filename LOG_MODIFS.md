# Journal des actions (GLPI2)

Date de départ: 2026-03-12

## Actions effectuées
1. Création du dossier de travail `glpi2` dans `/var/www/html`.
2. Extraction d’une base propre GLPI `10.0.16` depuis `glpi-10.0.16.tgz` vers `/var/www/html/glpi2`.

## À venir
- Analyse de l’interface actuelle.
- Application des modifications UI “premium” selon ta palette et tes instructions.
- Documentation continue de chaque changement.

## 2026-03-12 — Palette Oceanic + Premium UI (en cours)
1. Ajout de la nouvelle palette `oceanic` avec les couleurs marque (bleu/vert) dans `css/palettes/oceanic.scss`.
2. Ajout d’un fichier d’overrides UI premium dédié (`css/includes/_premium_overrides.scss`) pour :
   - page de login (fond dégradé, carte plus premium, logo re-stylé),
   - menu latéral et topbar (dégradés, arrondis, survols),
   - boutons d’action principaux (dégradés et ombres),
   - cartes et dashboard (rayons + ombres plus douces).
3. Ajout d’un aperçu de palette `oceanic.png` (copie temporaire) dans `css/palettes/previews/`.

## À décider / prochaine étape
- Activer la palette `oceanic` dans la config GLPI (ou la définir par défaut si tu veux).
- Ajuster/valider l’aperçu de palette avec les vraies couleurs.
- Itérer sur login, dashboard, menu latéral et actions après ton feedback visuel.

## 2026-03-12 — Branding logo + favicon
1. Copie des assets branding depuis `J:\Logo_asin` :
   - `asin.png` -> `pics/logos/logo-asin.png`
   - `title_icon_asin.png` -> `pics/logos/logo-asin-icon.png`
   - `favicon_asin.ico` -> `pics/favicon.ico` (remplace le favicon GLPI).
2. Mise à jour de la palette `oceanic` pour utiliser le logo client :
   - `logo-asin.png` pour le logo principal et le login.
   - `logo-asin-icon.png` pour l’icône du menu replié.

## 2026-03-12 — Accès GLPI2 via port dédié (Apache)
1. Ajout d’un port d’écoute Apache `8081` dans `/etc/apache2/ports.conf`.
2. Création du VirtualHost `glpi2.conf` (port 8081) pointant sur `/var/www/html/glpi2`.
3. Activation du vhost `glpi2.conf` et rechargement d’Apache.

### URL de test
- http://172.21.27.187:8081

## 2026-03-12 — Droits d’écriture pour l’installation GLPI2
1. Attribution des droits d’écriture à Apache sur `/var/www/html/glpi2/config` (chown + chmod) pour permettre la création de `config_db.php` et `glpicrypt.key`.

### À faire après installation
- Retirer l’écriture si nécessaire (retour en permissions plus strictes).

## 2026-03-12 — Correctifs d’installation GLPI2
1. Droits d’écriture accordés à Apache sur `files/` et `marketplace/` (création des sous-dossiers _cache, _log, etc.).
2. Vhost Apache sécurisé: DocumentRoot déplacé vers `/var/www/html/glpi2/public`.
3. Reload Apache pour appliquer le changement.

## 2026-03-12 — Correctif d’accès à l’install (temporaire)
1. Repointage temporaire du vhost GLPI2 vers `/var/www/html/glpi2` pour permettre l’accès à `/install` pendant l’installation.
2. Reload Apache.

### À faire après installation
- Revenir à un DocumentRoot `/var/www/html/glpi2/public` + alias nécessaires, si tu veux la configuration sécurisée.

## 2026-03-12 — Base de données GLPI2
1. Création de la base `glpi2` (utf8mb4).
2. Création de l’utilisateur SQL `glpi2_user` (localhost) et attribution des droits complets sur `glpi2`.

## 2026-03-12 — Ajustements logo + hover menu
1. Ajustement des logos du menu latéral :
   - Mode normal (barre ouverte) : logo `asin` avec taille réduite.
   - Mode replié : icône `asin` plus petite et centrée.
2. Changement du survol des liens du menu latéral : texte noir + fond clair pour contraste.

## 2026-03-12 — Sidebar background + sous-menus
1. Ajustement du background sidebar/topbar (dégradé plus sombre pour mieux faire ressortir le logo).
2. Ajout d’un fond léger derrière le logo (navbar-brand) pour améliorer la lisibilité.
3. Sous-menus : fond clair + survol en vert (`#5fa6af`) pour un repère visuel net.

## 2026-03-12 — Sidebar blanche (lisibilité logo)
1. Sidebar/topbar passées en blanc pour améliorer la lisibilité du logo.
2. Suppression du fond du bloc logo (navbar-brand) pour un rendu plus propre.
3. Ajustement des états actifs/survols avec les teintes de la marque (bleu/vert) sur fond clair.

## 2026-03-12 — Couleur texte menu latéral
1. Couleur par défaut des liens du menu latéral définie sur un gris-bleu foncé pour la lisibilité sur fond blanc.

## 2026-03-12 — Couleurs bouton Chercher, sous-menus, burger
1. Bouton "Chercher" (fuzzy) stylé avec teinte de marque sur fond blanc.
2. Sous-menus : fond blanc + texte sombre pour meilleure visibilité.
3. Icône burger : couleur alignée sur la marque.

## 2026-03-12 — Libellé interface
1. Remplacement du texte "Interface standard" par "Interface standard ASIN-GLPI" dans les locales françaises (fr_FR, fr_BE, fr_CA).

## 2026-03-12 — Bouton Réduire le menu
1. Application du même style que le bouton "Chercher" au bouton "Réduire le menu" pour une meilleure visibilité.
