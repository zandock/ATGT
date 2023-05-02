# Gestión de permisos 
En Linux, tanto para archivos como para directorios se pueden modificar los permisos que decidamos asignarles. Los permisos para ambos elementos son **escritura**, **lectura** y **ejecución**. Para entender esto mejor, hay que saber que Linux contempla tres tipos de usuarios diferentes, los cuales pueden o no tener los mismos permisos:

- *Usuario propietario*: es el usuario que creó dicho archivo y/o directorio, por lo que suele tener todos los permisos disponibles activos.
- *Grupo propietario*: es un conjunto de usuarios que, debido a sus permisos, pueden tener cierto accesso e incluso pueden modificar el elemento en caso de ser necesario.
- *Resto de usuarios*: son el grupo conformado por todos los demás usuarios que podrían ver nuestros elementos. A estos normalmente se les asigna únicamente permisos de lectura y/o ejecución.

## Cambiando permisos
El comando *chmod* es usado para modificar permisos, pero, por la notación que usa, puede basarse en números o letras que representan (en inglés) el permisos que dan y a quién se lo conceden.

### Cambiando permisos usando letras
Por ejemplo, si a nuestro archivo **myFile** queremos que el usuario propietario tenga todos los permisos, el grupo propietario pueda leer y escribir, y el resto de usuarios únicamente pueda leer el archivo; entonces, nos quedaría algo así:

*~$ chmod u=rwx,g=rw,o=r myFile*

nótese que *r* representa **read** (leer), *w* es **write** (escribir) y *x* es **execute** (ejecutar). La letra *u* es el **usuario propietario**, *g* es el **grupo propietario** y *o* son el **resto de usuarios**.

### Cambiando permisos usando números
El comando *chmod* también puede modificar permisos usando números, que son los permisos a asignar:

- 0 - Sin permisos
- 1 - Execute
- 2 - Write
- 3 - Execute + Write	
- 4 - Read
- 5 - Read + Execute	
- 6 - Read + Write	
- 7 - Read + Write + Execute 

Entonces, si queremos asignar los mismos permisos del ejemplo anterior, basta con hacer lo siguiente:

*~$ chmod 764 myFile*

donde el *7* representa los permisos para el **usuario propietario**, el *6* los permisos para el **grupo propietario** y el *4* para el **resto de ususarios**.
