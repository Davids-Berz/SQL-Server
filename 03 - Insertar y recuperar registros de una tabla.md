# 3 - Insertar y recuperar registros de una tabla

Un registro es una fila de la tabla que contiene los datos propiamente dichos. Cada registro tiene un dato por cada columna (campo). Nuestra tabla "usuarios" consta de 2 campos, "nombre" y "clave".

Al ingresar los datos de cada registro debe tenerse en cuenta la cantidad y el orden de los campos.

La sintaxis básica y general es la siguiente:

```
 insert into NOMBRETABLA (NOMBRECAMPO1, ..., NOMBRECAMPOn)
 values (VALORCAMPO1, ..., VALORCAMPOn);
 ```

 Usamos "insert into", luego el nombre de la tabla, detallamos los nombres de los campos entre paréntesis y separados por comas y luego de la cláusula "values" colocamos los valores para cada campo, también entre paréntesis y separados por comas.

Para agregar un registro a la tabla tipeamos:

`insert into usuarios (nombre, clave) values ('Mariano','payaso');`

Note que los datos ingresados, como corresponden a cadenas de caracteres se colocan entre comillas simples.

Para ver los registros de una tabla usamos "select":

`select * from usuarios;`

El comando "select" recupera los registros de una tabla.
Con el asterisco indicamos que muestre todos los campos de la tabla "usuarios".

Ingresemos el siguiente lote de comandos:

```
if object_id('usuarios') is not null
  drop table usuarios;

 create table usuarios(
  nombre varchar(30),
  clave varchar(3)
 );

 insert into usuarios (nombre, clave) values ('David','142');

 select * from usuarios;

 insert into usuarios (nombre, clave) values ('Josue','533');

 select * from usuarios;

 insert into usuarios (nombre,clave) values ('Samuel','237');

 select * from usuarios;
```

||nombre|clave|
|:-:|:-:|:-:|
|1|David|142|
|2|Josue|533|
|3|Samuel|237|