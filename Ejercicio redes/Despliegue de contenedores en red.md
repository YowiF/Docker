---

@athor Yoel Fernández Suárez y Daniel Garcia Castro
---

#  							

# 									Ejercicio Redes

[TOC]



#### Apartado 1:

Crea una red bridge redbd

```bash
sudo docker network create redbd
```

![red1.1](red1.1.jpg)



#### Apartado 2:

 Crea un contenedor con una imagen de mariaDB que estará en la red redbd . Este contenedor se ejecutará en segundo plano, y será accesible a través del puerto 3306. (Es necesario definir la contraseña del usuario root y un volumen de datos persistente)

```bash
sudo docker run -d --name cont1 --network redbd -v ~/datav:var/lib/mysql -p 3336:3336 -e MYSQL_ROOT_PASSWORD=123 mariadb


```

![red1.2](red1.2.jpg)



#### Apartado 3:

Crear un contenedor con Adminer que se pueda conectar al contenedor de la BD

```bash
sudo docker run -d --name cont2 --network redbd --link cont1:mariadb -p 8080:8080 adminer
```

![red1.3](red1.3.jpg)

#### Apartado 4:

Comprobar que el contenedor Adminer puede conectar con el contenedor mysql abriendo un navegador web y accediendo a la URL: http://localhost:8080

![red2.1](red2.1.jpg)

#### ![red2.2](red2.2.jpg)

#### Resultados:

![red1.4](red1.4.jpg)

![red3.1](red3.1.jpg)

![red4.1](red4.1.jpg)

![red5.1](red5.1.jpg)

![red5.2](red5.2.jpg)