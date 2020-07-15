---
title: Creación múltiple de cuentas de usuario en Debian.
tags: ["Usuarios","Creación","Debian"]
---

En este post veremos de manera sencilla y rápida como crear cusuarios por lotes en Debian 10 en introducirlos en nuestro fichero de /etc/passwd.

##### Crear ficheros de usuarios

- Para crear este fichero tenemos que fijarnos en la estructura de nuestro passwd y con el comando for crearemos varios usuarios, lo añadimos a un fichero llamado alumnosnew para después sacar la información de dicho fichero.

<em>
 for i in {1..4};do `echo alumno$i:x:121$i:121$i:alumno$i:/home/alumno$i:/bin/bash >> alumnosnew`;done
</em>

##### Crear contraseñas con pwgen

- Una vez creado los usuarios vamos a crear las contraseñas con pwgen, creamos un for para introducir las contraseñas.

<em>
 for i in {1..4};do echo alumno$i:`pwgen` >> contraseñanew ;done
</em>

#####  Agregar usuarios con newusers

- Ejecutamos el comando newusers (lee un fichero y utiliza la información para crear usuarios por lotes) con el fichero alumnosnew que hemos creado anteriormente.

<em>
 newusers < usuariosnew
</em>
#####  Agregar contraseña a los usuarios creados

- Ahora solo nos queda agregar las contraseñas con chpasswd a los usuarios correspondientes.

<em>
  chpasswd < contraseñasnew
</em>

##### Comprobación

- Muestra de los usuarios creados en /etc/passswd.

![comprobacion](/QuestTIC/img-post/batch/comprobacion.png))

- Comprobación con un login de un usuario.

![comprobacion](/QuestTIC/img-post/batch/login.png))
