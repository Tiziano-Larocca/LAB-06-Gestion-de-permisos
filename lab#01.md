# Actividad: Trabajando con Permisos en Linux

## Objetivo

Esta actividad tiene como objetivo que los estudiantes comprendan y practiquen la gestión de permisos en Linux, utilizando los comandos `chmod`, `chown` y `ls`.

## Instrucciones

### 1. Preparación

1. Abrí una terminal en tu distribución de Linux.
2. Crea un directorio llamado `actividad_permisos` y accede a él.

```sh
mkdir actividad_permisos
cd actividad_permisos
```
### 2. Creación de Archivos y Directorios
Dentro del directorio actividad_permisos, crea los siguientes archivos y un subdirectorio:
```sh
touch archivoA.txt archivoB.txt archivoC.txt
mkdir subdirectorio
```
### 3. Exploración de Permisos
Usa el comando ls -l para ver los permisos actuales de los archivos y directorios creados.
```sh
ls -l
```
2. Anota los permisos actuales de cada archivo y directorio en la siguiente tabla:

| **Nombre**      | **Permisos Actuales** |
|-----------------|-----------------|
| archivoA.txt	  |    -rw-r– -r– -   |
| archivoB.txt    |    -rw-r– -r– -   |
| archivoC.txt    |    -rw-r– -r– -   |
| subdirectorio   |    drwxr-xr-x   |

### 4. Modificación de Permisos
Cambia los permisos de archivoA.txt para que el usuario tenga permisos de lectura y escritura, el grupo solo lectura y otros no tengan permisos.
```sh
chmod 640 archivoA.txt
```
Cambia los permisos de archivoC.txt para que el usuario tenga todos los permisos, el grupo solo lectura y otros solo ejecución.
```sh
chmod 741 archivoC.txt
```
Cambia los permisos del subdirectorio para que el usuario tenga todos los permisos, el grupo y otros solo tengan permisos de lectura y ejecución.
```sh
chmod 755 subdirectorio
```
### 5. Verificación de Cambios
```sh
ls -l
```
Anota los nuevos permisos de cada archivo y directorio en la siguiente tabla:

| **Nombre**      | **Permisos Actuales** |
|-----------------|-----------------|
| archivoA.txt	  |    -rw–r- - - - -|
| archivoB.txt    |    -rw-r- -r- -  |
| archivoC.txt    |    -rwxr- - - -x |
| subdirectorio   |    drwxr-xr-x    |

### 6. Cambio de Propietarios
1. Cambia el propietario de archivoA.txt a otro usuario (reemplaza otro_usuario con el nombre de un usuario existente en el sistema o crealo).
```sh
chown otro_usuario archivoA.txt
```
3. Cambia el grupo de archivoB.txt a otro grupo (reemplaza otro_grupo con el nombre de un grupo existente en el sistema o crealo).
```sh
chown :otro_grupo archivoB.txt
```
5. Cambia el propietario y grupo de archivoC.txt a otro_usuario y otro_grupo.
```sh
chown otro_usuario archivoC.txt
chown :otro_grupo archivoC.txt
```
### 7. Verificación de Cambios de Propietarios
1. Usa el comando ls -l para verificar los cambios en los propietarios y grupos.
2. Anota los nuevos propietarios y grupos de cada archivo en la siguiente tabla:

| **Nombre**      | **Nuevo propietario** | **Nuevo grupo**|
|-----------------|-----------------|-----------------------|
| archivoA.txt	  |  otro_usuario   |  root                 |
| archivoB.txt    |  root           |  otro_grupo           |
| archivoC.txt    |  otro_usuario   |  otro_grupo           |
| subdirectorio   |  root           |  root                 |

### 8. Reflexión
¿Qué diferencias observaste en el comportamiento de los archivos y directorios al cambiar sus permisos y propietarios?
```sh
Al cambiar los permisos de los archivos con los comandos chmod y chown,
hemos notado que otros usuarios tienen diferentes maneras de
visualizar ya sea por escritura, lectura o ejecución.
```
¿Por qué es importante gestionar correctamente los permisos en un sistema Linux?
```sh
Es importante gestionar correctamente los permisos en un sistema Linux
ya que la persona que pueda acceder a esos archivos no pueda hacer otra cosa que no sea la tarea requerida.
Por ejemplo: En el trabajo el empleado solo debe leer, escribir y ejecutar un archivo solicitado.
El superior a cargo solo deberá leer, pero si se requiere podrá modificarlo. 
```
