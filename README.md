# mariagogs

Docker containerized Gogs with MariaDB backend

## Commands

MariaDB docker run:

`# docker run --name maria -d -p 3306:3306 mariadb`

Gogs docker run:

`# docker run --name gogs --link maria:mariagogs -d -p 80:3000 gogsbin`