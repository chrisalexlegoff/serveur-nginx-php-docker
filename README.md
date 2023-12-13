# serveur-php-nginx

Dockerfile pour le build d'un serveur Nginx - php.

## Bien démarrer

Ces instructions couvriront les informations d'utilisation de cette image.

### Prérequis

Pour utiliser ce Dokerfile, vous devez installer Docker..

- [Windows](https://docs.docker.com/windows/started)
- [OS X](https://docs.docker.com/mac/started/)
- [Linux](https://docs.docker.com/linux/started/)

### Usage

#### L'image

PULL via Docker Hub :

```shell
docker pull blackcustom/serveur-php-nginx
```

BUILD via Dokerfile :

```shell
docker build -t monserveur:dev .
```

ARGUMENTS :

- php-version : 7.4 par défaut

```shell
docker build -t monserveur:dev --build-arg PHP_VERSION=<'votreversion'> .
```

- dossier site local : par défaut ./app

```shell
docker build -t monserveur:dev --build-arg FOLDER_APP=<'votredossierlocal'> .
```

- dossier config local : par défaut ./config

```shell
docker build -t monserveur:dev --build-arg FOLDER_CONFIG=<'votredossierlocal'> .
```

#### Paramètres du conteneur

Lister les différents paramètres disponibles pour votre conteneur

```shell
docker run -d -p 8080:80 --name monserveurtest monserveur:dev
```

Comment démarrer également un shell dans votre conteneur

```shell
docker run -d -ti monserveur:dev bash
```

#### Environment Variables

- `php_cppflags` - "$php_cppflags -std=c++11"
- `TERM` - xterm-256color

#### Emplacements de fichiers utiles

- `/etc/entrypoint.sh` - démarrage Nginx + PHP-fpm

## Me trouver

- [GitHub](https://github.com/chrisalexlegoff/serveur-nginx-php-docker)
- [Docker-Hub](https://hub.docker.com/r/blackcustom/serveur-php-nginx)

## Auteur

- **Christophe Le Goff** - [Mon site personnel](https://christophe-le-goff.com)
