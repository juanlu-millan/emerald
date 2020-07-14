---
title: Creación batch de cuentas de usuario.
tags: ["Usuarios","Creación","Debian"]
---

##### Crear ficheros de usuarios

- Para crear este fichero tenemos que fijarnos en la estructura de nuestro passwd y con el comando for crearemos varios usuarios, lo añadimos a un fichero llamado usuariosnew para después sacar la información de dicho fichero.

<pre>
 for i in {1..4};do `echo alumno$i:x:121$i:121$i:alumno$i:/home/alumno$i:/bin/bash >> alumnosnew`;done
</pre>

##### Crear contraseñas con pwgen

- Una vez creado los usuarios vamos a crear las contraseñas con pwgen, creamos un for para introducir las contraseñas.

<pre>
 for i in {1..4};do echo alumno$i:`pwgen` >> contraseñanew ;done
</pre>

#####  Agregar usuarios con newusers

- Ejecutamos el comando newusers (lee un fichero y utiliza la información para crear usuarios por lotes) con el fichero alumnosnew que hemos creado anteriormente.

<pre>
 newusers < usuariosnew
</pre>
#####  Agregar contraseña a los usuarios creados

- Ahora solo nos queda agregar las contraseñas con chpasswd a los usuarios correspondientes.

<pre>
  chpasswd < contraseñasnew
</pre>

##### Comprobación

- Muestra de los usuarios creados
![comprobacion](/QuestTIC/img-post/batch/comprobacion.png))

-Comprobación con un login de un usuario creados
![comprobacion](/QuestTIC/img-post/batch/login.png))
