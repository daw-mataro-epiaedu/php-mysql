# Docker: PHP & MySQL

Instal·la ràpidament un entorn de desenvolupament local per treballar amb [PHP](https://www.php.net/) i [MySQL](https://www.mysql.com/) utilitzant [Docker](https://www.docker.com).

## Configurar l'entorn de desenvolupament

Es pot utilitzar la configuració per defecte, però en ocasions és recomanable modificar la configuració perquè sigui igual al servidor de producció. La configuració es troba a l'arxiu `.env` amb les següents opcions:

* `PHP_PORT` port pel servidor web.
* `MYSQL_VERSION` versió de MySQL([Versions disponibles de MySQL](https://hub.docker.com/_/mysql)).
* `MYSQL_USER` nom d'usuari per connectar-se a MySQL.
* `MYSQL_PASSWORD` clau d'accés per conectar-se a MySQL.
* `MYSQL_DATABASE` nom de la base de dades que es crea per defecte.

## Instal·lar l'entorn de desenvolupament

La instal·lació es fa en línia de comandes:

```zsh
docker-compose up -d
```

Pots verificar la instal·lació accedint a: [http://localhost/info.php](http://localhost/info.php)

## Comandaments disponibles

Un cop instal·lat, es poden utilitzar els següents comandaments:

```zsh
docker-compose start    # Iniciar l'entorn de desenvolupament
docker-compose stop     # Parar l'entorn de desenvolupament (no usat habitualment)
docker-compose down     # Para i elimina l'entorn de desenvolupament
docker-compose restart  # Reiniciar l'entorn de desenvolupament
```

## Estructura d'arxius

* `/docker/` conté els arxius de configuració de Docker.
* `/www/` carpeta pels arxius PHP del projecte.

## Accesos

### Web

* `http://localhost/`

### Base de dades

Per accedir al gestor de la base de dades.

* `mysql`: per connexió des de els arxius PHP.
* `localhost`: per connexions externes.

Les credencials per defecte per la connexió són:

| Usuari |  Clau  | Base de dades |
|:------:|:------:|:-------------:|
| dbuser | dbpass |     dbname    |

### Creació de bases de dades

Utilitzant l'extensió de `VSCode` o `Azure Data Studio` ens connectem al servidor de MySQL i creem la base de dades.

![Connexió a MySQL](./img/pic01.png)

Un cop connectats, creem una nova consulta per tal de definir la taula i ompliar-la amb dades.

![Creació de la taula](./img/pic02.png)

Podem veure que la taula s'ha creat correctament.

![Taula creada](./img/pic03.png)

Ara des de l'app de PHP podem veure les dades de la taula.

![Dades de la taula](./img/pic04.png)
