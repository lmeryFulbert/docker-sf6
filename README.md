# docker-sf6

## :checkered_flag: Installation ##

```bash
# Installer et demarrer les containers
$ docker compose up -d

# Cloner le dépôt du  projet dans le dossier app
$ cd app
$ git clone https://github.com/...

# Se connecter au container php
$ docker exec -it <container_name> bash

# Installer les dépendences avec composer
# Composer a été installé dans le bulid du contaner php-fpm8
$ composer install

# se connecter à phpmyadmin http://@serv:8080
# Créer la base de données [dbname]
# Créer l'utilisateur [appuser] avec le mot de passe [password]

# Verifier le fichier ./app/.env  (env.txt) et modifier la ligne faisant référence au SGBD
DATABASE_URL="mysql://[appuser]:[password]@mariadb:3306/[dbname]?serverVersion=8&charset=utf8"

# Faire les migrations (pour la base de données)
$ php bin/console make:migration
$ php bin/console doctrine:migrations:migrate

# Charger les jeux de données
$ php bin/console doctrine:fixtures:load

# se rendre sur le serveur
$ http://ip_server

```

## :sparkles: Enjoy

