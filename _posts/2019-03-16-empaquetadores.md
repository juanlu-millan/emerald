---
title: Empaquetadores,Compresores y Descompresores
date: 2019-03-14T11:34:00Z
tags: ["Empaquetadores","Compresores","Descompresores"]
---

Existen distintas maneras de agrupar ficheros,imágenes o programas, veremos una gran variedad de formatos y sus opciones para hacerlo de manera óptima.

### Tar
– Es un empaquetador de archivos que como su propio nombre indica utiliza el formato .tar, básicamente se utiliza para almacenar ficheros y directorios en un mismo archivo.

#### Ejemplos:

tar -vcf /carpeta/archivos

#### Opciones Básicas:
-c: Crea un nuevo fichero

-v: visualiza el trabajo que realiza el comando

-x: descomprimir/extraer el fichero

-f: archivar/crear el directorio

-t: realiza un listado de los ficheros empaquetados     

#### Sufijos:
```
-j, –bzip2
Comprime con el formato bzip2
“tar -vjcf archivo.tar.bz2 directorio/”
-J, –xz
Comprime con el formato xz
“tar -vJcf archivo.tar.xz directorio/”
-z, –gz
Comprime con el formato gz
“tar -vzcf archivo.tar.gz directorio/”
-z, –lzip
Comprime con el formato lzip
“tar -vcf archivo.tar.lz directorio/”
```

### Gzip
– Su función es comprimir y descomprimir archivos, por lo que reduce el tamaño de los ficheros considerablemente.

– Su extensión es .gz

#### Ejemplo:

gz fichero.gz fichero
#### Opciones:
-d: Se utiliza para descomprimir
-f: Fuerza la compresión o descompresión, incluso si el archivo tiene varios enlaces o si ya existe el archivo.
-l: Se utiliza para listar

### Zip
– Es unos de los compresores más utilizados, se utiliza para documentos,imágenes o programas, zip comprime cada archivo independientemente del resto de archivos comprimidos permite recuperar cada uno de los ficheros sin tener que leer el resto, lo que aumenta el rendimiento.

– Su extensión es .zip

– En caso de descomprimir se utiliza unzip

#### Ejemplo:

comprimir: zip -r carpeta.zip carpeta/

descomprimir: unzip carpeta.zip
#### Opciones:

-r: Realiza la compresión de manera recursiva, de esa manera podemos comprimir un directorio y sus ficheros.

-P: Agrega una contraseña al fichero. | zip -P “contraseña” archivo.zip archivo |

-T: Comprueba el nuevo archivo zip. Si falla la comprobación el archivo zip antiguo no se modifica.

-v: Muestra información más detallada

-i: Incluye solo los archivos especificados

-sf: muestra los ficheros que se están operando

### Xz
– Este compresor esta bastante extendido pero uno de sus problemas es que no puede
comprimir directorios y tiene que ayudarse del comando tar.

#### Ejemplo:
xz archivo | xz -d archivo | xz -k (archivo o archivo.xz)
#### Opciones:
-z: Realiza la compresión al formato .xz, al agregar la opción -z no puede utilizar más opciones de operación.

-d: Descomprimir.

-k: No elimina los archivos de entrada después de la compresión o descompresión.

-l: Lista el contenido del fichero comprimido.

-t: Comprueba la integridad del archivo.

-F: Especifica el tipo de formato con el que quieres comprimir y descomprimir.


➔ auto: Este es el predeterminado Al comprimir, auto es equivalente a xz.

➔ xz: Comprimir al formato de archivo .xz y acepta solo archivos .xz al descomprimir.

➔ Lzma: Comprimir al formato de archivo .lzma y acepta archivos .lzma al descomprimr

➔ raw: Comprime y descomprime una secuencia sin encabezado.

#### Comandos Alias
unxz es equivalente a xz –decompress .

xzcat es equivalente a xz –decompress –stdout .

lzma es equivalente a xz –format = lzma .

unlzma es equivalente a xz –format = lzma –decompress .

lzcat es equivalente a xz –format = lzma –decompress –stdout .


#### Lzma
El compresor LZMA utiliza una versión mejorada y optimizada del algoritmo de compresión LZ77, tiene una alta relación de compresión

Ejemplo:

lzma -k archivo

#### Opciones:

-f: Fuerza la compresión o descompresión
-d: Descomprimir
-k: No elimina los archivos de entrada después de la compresión o descompresión
-q: Suprime todos los advertencias
-V: Ver versión de lzma.

### Rar
El RAR es más lento que el ZIP, pero posee una mayor tasa de compresión. Otra característica de RAR es que posee una mejor redundancia de datos que ZIP. Además, este formato permite lo que se conoce como compresión sólida que permite comprimir varios ficheros juntos, de forma que un mismo diccionario se aplica a toda la información, con lo que el nivel de compresión es mayor.

#### Ejemplo:
rar directorio.rar directorio/
#### Opciones:
•  a: Añade ficheros al archivo

•  cw: Escribe un comentario de archivo en un archivo especificado.

•  d: Eliminar archivos del archivo.

•  e: Extraer archivos al directorio actual. No crea ningún subdirectorio.

•  f: Actualizar ficheros del archivo. Actualiza esos archivos cambiados desde que fueron empaquetados al archivo.
•  k: Bloquear el archivo. Cualquier comando que pretenda cambiar el archivo será ignorado.


### 7z
Es un formato de compresión de datos sin pérdida, con tasas muy altas que superan a las de los populares formatos zip y rar. El formato 7z permite el cifrado utilizando el algoritmo AES con claves de 256-bit. Estas claves son generadas por medio de una contraseña suministrada por el usuario.

#### Ejemplo:

7z a directorio.7z directorio/
 

#### Opciones:

• a: Añade ficheros al archivo

• d: Eliminar archivos del archivo

• e: Extraer archivos del archivos

• i: Mostrar información sobre los formatos soportados

• l: Lista de contenidos del archivo comprimido.

• rn: Renombra

• t: Test de integridad de archivos.

• u: Actualizar ficheros del archivo
