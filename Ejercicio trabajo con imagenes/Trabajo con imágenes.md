# 				Trabajo con imágenes

[TOC]



### Servidor Web:



#### Apartado 1:

Arranca un contenedor que ejecute una instancia de la imagen php:7.4-apache , que se llame web y que sea accesible desde un navegador en el puerto 8000.

```bash
docker pull php:7.4-apache
docker images
docker run -p 8000:80 --name web
```



```bash

```

![image-20220113180613052](imagenes1.1.1.jpg)

![imagenes1.1.2](imagenes1.1.2.jpg)

![imagenes1.1.3](imagenes1.1.3.jpg)

#### APARTADO 2:

Colocar en el directorio raíz del servicio web ( /var/www/html ) de dicho contenedor un fichero llamado index.html con el siguiente contenido:

```bash
docker start web
echo"<h1>HOLA SOY DANIEL GARCIA CASTRO</h1>"
exit

```



![image-20220120173918063](imagenes2.1.jpg)

![image-20220120173941121](imagenes2.2.jpg)

#### APARTADO 3:

Colocar en ese mismo directorio raíz un archivo llamado mes.php que muestre el nombre del mes actual. Ver la salida del script en el navegador

```bash
docker exec -it web bash
echo "<?php echo date('F'); ?>" > mes.php
```

![image-20220120174347541](imagenes1.3.1.jpg)

![image-20220120174406022](imagenes1.3.2.jpg)

#### APARTADO 4:

```bash
docker stop web
docker rm web

```

![image-20220120175337047](imagenes1.4.1.jpg)
