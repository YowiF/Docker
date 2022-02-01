---
Title: Ejercicio inicial
Author: Yoel Fernández Suárez y Daniel García Castro
---

#                     EJERCICIO INICIAL

[TOC]

## Apartado 1.

Pantallazo donde se vea la creación del contenedor y podamos comprobar que el contenedor está funcionando:

```bash
docker run -d -p 8181:80 --name servidor_web nginx
docker ps -as
```

![image-20220113172658090](inicial1.1.jpg)

![image-20220113172718999](inicial1.2.jpg)

## Apartado 2.

Pantallazo donde se vea el acceso al servidor web utilizando un navegador web (recuerda que tienes que acceder a la ip del ordenador donde tengas instalado docker):

![image-20220113172949652](inicial2.1.jpg)

## Apartado 3.

Pantallazo donde se vean las imágenes que tienes en tu registro local:

```bash
docker images
```

![image-20220113173037087](inicial3.1.jpg)

## Apartado 4.

Pantallazo donde se vea cómo se elimina el contenedor (recuerda que antes debe estar parado el contenedor):

```bash
docker stop servidor_web
docker rm servidor_web
docker ps -a
```

![image-20220113173337683](inicial4.1.jpg)