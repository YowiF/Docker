---
Title: Ejercicio - Crea una Imagen con Dockerfile
Author: Yoel Fernández Suárez y Daniel García Castro
---

# 		Ejercicio - Crea una Imagen con Dockerfile

[TOC]

## Apartado 1.

Pantallazo/bloque de código con el Dockerfile:

```bash
gedit Dockerfile
```

![dockerfile1.1](dockerfile1.1.jpg)



```bash
FROM nginx
ADD public_html /usr/share/nginx/html
EXPOSE 80
```

![dockerfile1.2](dockerfile1.2.jpg)

## Apartado 2.

Pantallazo donde se vea el comando que crea la nueva imagen:

```bash
docker build -t danielgarca88/imagendockerfile:imgdf .
```

![dockerfile2.1](dockerfile2.1.jpg)



```bash
docker push danielgarca88/imagendockerfile:imgdf
```

![dockerfile2.2](dockerfile2.2.jpg)

## Apartado 3.

Pantallazo donde se vea la imagen subida a tu cuenta de Docker Hub:

![dockerfile3.1](dockerfile3.1.jpg)

## Apartado 4.

 Pantallazo donde se vea la bajada de la imagen - por parte de otra persona del grupo - y la creación de un contenedor:

![dockerfile4.1](dockerfile4.1.JPG)



```bash
sudo docker pull danielgarca88/imagendockerfile:imgdf
```

![dockerfile4.2](dockerfile4.2.JPG)



```bash
sudo docker run -d --name dfimagen -p 8080 danielgarca88/imagendockerfile:imgdf
```

![dockerfile4.3](dockerfile4.3.JPG)

## Apartado 5.

Pantallazo donde se ve el acceso al navegador con el sitio servido:

(Ejercicio sin completar)
