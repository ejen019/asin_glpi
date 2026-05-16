![GLPI CI](https://github.com/glpi-project/glpi/workflows/GLPI%20CI/badge.svg?branch=9.5%2Fbugfixes)
[![Github All Releases](https://img.shields.io/github/downloads/glpi-project/glpi/total.svg)](#telechargement)
[![Twitter Follow](https://img.shields.io/twitter/follow/GLPI_PROJECT.svg?style=social&label=Follow)](https://twitter.com/GLPI_PROJECT)

## A propos de GLPI ASIN

Ce depot contient la version **GLPI ASIN** personnalisee pour les besoins internes :

* Interface de connexion personnalisee (charte ASIN)
* Ecran mot de passe oublie personnalise
* Theme visuel adapte (menu, topbar, boutons, dashboard)
* Textes d'interface francises sur les ecrans personnalises
* Journal des modifications dans `LOG_MODIFS.md`

L'objectif est d'avoir une base GLPI operationnelle, lisible, et adaptee aux usages ASIN sans repartir de zero a chaque installation.

## Sommaire

* [Structure du projet](#structure-du-projet)
* [Prerequis Windows](#prerequis-windows)
* [Installation Windows pas a pas](#installation-windows-pas-a-pas)
* [Post-installation](#post-installation)
* [Captures ASIN-GLPI](#captures-asin-glpi-a-completer)
* [Maintenance](#maintenance)

## Structure du projet

Fichiers et dossiers importants pour la personnalisation ASIN :

* `css/palettes/oceanic.scss` : palette visuelle ASIN
* `css/includes/_premium_overrides.scss` : surcharges de style (login/menu/dashboard)
* `templates/pages/login.html.twig` : page de connexion personnalisee
* `templates/password_form.html.twig` : page de recuperation mot de passe personnalisee
* `front/lostpassword.php` : logique de recuperation mot de passe
* `pics/` : logos et ressources graphiques
* `LOG_MODIFS.md` : historique des changements

## Prerequis Windows

Avant installation, preparer :

* **Windows 10/11**
* **Serveur web local** : XAMPP, WampServer ou equivalent (Apache + MariaDB/MySQL + PHP)
* **PHP compatible GLPI 10.0.x** (de preference PHP 8.1 ou 8.2)
* Extensions PHP actives : `curl`, `gd`, `intl`, `mysqli`, `zlib`, `xml`, `zip`, `openssl`
* **Git for Windows** (pour cloner le depot)
* Un navigateur recent (Chrome, Edge ou Firefox)

## Installation Windows pas a pas

### 1. Cloner le depot

Dans `PowerShell` ou `Git Bash` :

```bash
git clone https://github.com/ejen019/asin_glpi.git
```

### 2. Copier le projet dans le dossier web

Selon ton stack local :

* XAMPP : copier dans `C:\xampp\htdocs\glpi2`
* WampServer : copier dans `C:\wamp64\www\glpi2`

Tu peux aussi renommer le dossier, mais `glpi2` est recommande pour garder la meme structure que la doc projet.

### 3. Creer la base de donnees

Depuis `phpMyAdmin` (ou en SQL) :

* Creer une base, par exemple `glpi2`
* Creer un utilisateur SQL dedie, par exemple `glpi2_user`
* Donner tous les droits de cette base a cet utilisateur

### 4. Verifier les droits d'ecriture

Sur Windows, verifier que le compte du service Apache peut ecrire dans :

* `config/`
* `files/`
* `marketplace/`

### 5. Lancer l'installation web

Ouvrir le navigateur :

* XAMPP : `http://localhost/glpi2/`
* Wamp : `http://localhost/glpi2/`

Suivre l'assistant d'installation GLPI :

* Choisir la langue francaise
* Renseigner l'hote SQL (`localhost`), la base, l'utilisateur et le mot de passe
* Finaliser l'installation

### 6. Finaliser la securisation minimale

Apres installation :

* Supprimer/renommer le dossier `install/` selon la recommandation GLPI
* Verifier que le fichier `config/config_db.php` est bien genere
* Se connecter avec le compte administrateur, puis changer les mots de passe par defaut

## Post-installation

Checklist recommandee :

* Verifier l'affichage ASIN du login
* Tester le lien "Mot de passe oublie ?"
* Verifier le menu lateral et la topbar
* Verifier le dashboard
* Configurer la langue utilisateur en `Francais` pour eviter les textes anglais restants

## Captures ASIN-GLPI (a completer)

Les captures ci-dessous sont reservees a la personnalisation locale ASIN et seront ajoutees manuellement :

* Ecran de connexion :
* <img width="1919" height="1079" alt="Login" src="https://github.com/user-attachments/assets/b6c4dfd8-989b-482e-80b0-683ffe550221" />

* Ecran mot de passe oublie :
* <img width="1919" height="1072" alt="Mdp_Oublie" src="https://github.com/user-attachments/assets/21f567e4-7b73-451c-9006-8dc3299ab364" />

* Accueil SideBar Deployee :
* <img width="1920" height="1080" alt="Accueil-SideBar_deployee" src="https://github.com/user-attachments/assets/59f1de7d-3721-4905-93aa-2b860eb3b7ad" />

* Accueil SideBar Repliee :
* <img width="1920" height="1080" alt="Accueil-SideBar_repliee" src="https://github.com/user-attachments/assets/c995e45b-1476-47a8-be48-93bb45757764" />

* Page commune exemple :
* <img width="1919" height="1079" alt="Page_dexemple" src="https://github.com/user-attachments/assets/53c09c0d-c7e4-44c0-b7b8-ff95768fef40" />

* SideBar :
* <img width="403" height="1079" alt="SideBar" src="https://github.com/user-attachments/assets/fa46dfd0-61db-41a0-9fb2-f9da66be23ec" />

## Maintenance

* Suivre les modifications dans `LOG_MODIFS.md`
* Appliquer les changements via commits courts et explicites
* Tester login + recuperation mot de passe apres chaque modification de template
