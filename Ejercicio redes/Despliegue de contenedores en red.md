---
Title: Ejercicio Redes. Despliegue de contenedores en red: Adminer y MariaDB.
Author: Yoel Fernández Suárez y Daniel García Castro
---

#  							

# 									Ejercicio Redes. Despliegue de contenedores en red: Adminer y MariaDB.

[TOC]

## Apartado 1.

Pantallazos donde se vean los contenedores creados y en ejecución:

```bash
sudo docker network create redbd
```

![red1.1](red1.1.jpg)



```bash
sudo docker run -d --name cont1 --network redbd -v ~/datav:var/lib/mysql -p 3336:3336 -e MYSQL_ROOT_PASSWORD=123 mariadb
```

![red1.2](red1.2.jpg)



```bash
sudo docker run -d --name cont2 --network redbd --link cont1:mariadb -p 8080:8080 adminer
```

![red1.3](red1.3.jpg)



```bash
docker ps -a
```

![red1.4](red1.4.jpg)

## Apartado 2.

 Pantallazo donde se vea el acceso a la BD a través de la interfaz web de Adminer:

![red2.1](red2.1.jpg)



![red2.2](red2.2.jpg)

## Apartado 3.

Pantallazo donde se vea la creación de una BD con la interfaz web Adminer:

![red3.1](red3.1.jpg)

## Apartado 4.

Pantallazo donde se entre a la consola del servidor web en modo texto y se
compruebe que se ha creado la BD:

```sql
create database adminerdb
```

![red4.1](red4.1.jpg)

## Apartado 5.

Borrar los contenedores la red y los volúmenes utilizados:

```bash
docker rm cont1
docker rm cont2
docker ps -a
```

![red5.1](red5.1.jpg)



```bash
docker volume rm datav
```

![red5.2](red5.2.jpg)