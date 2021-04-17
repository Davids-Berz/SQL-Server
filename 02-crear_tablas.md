# 2 - Crear una tabla (create table - sp_tables - sp_columns - drop table)


Una **tabla** es una estructura de datos que organiza los datos en columnas y filas; 
cada columna es un campo (o atributo) y cada fila, un registro. 
La intersección de una columna con una fila, contiene un dato específico, un solo valor.

```
create table NOMBRETABLA(
  NOMBRECAMPO1 TIPODEDATO,
  ...
  NOMBRECAMPON TIPODEDATO
 ); 
```

Para ver la estructura de tablas usamos e siguiente procedimiento almacenado

`exec sp_columns usuarios;`

Para eliminar una tabla usamos "drop table" junto al nombre de la tabla a eliminar

`drop table NOMBRETABLA;`

Para ver las tablas de la base de datos usamos el siguiente procedimiento almacenado

`exec sp_tables @table_owner='dbo';`

La tabla debe ser definida con un nombre que la identifique y con el cual accederemos a ella.

Creamos una tabla llamada "usuarios" y entre paréntesis definimos los campos y sus tipos:

```
 create table usuarios (
  nombre varchar(30),
  clave varchar(10)
 );
 ```
 
 Para ver la estructura de una tabla usamos el procedimiento almacenado "sp_columns" junto al nombre de la tabla:

`exec sp_columns usuarios;`

aparece mucha información que no analizaremos en detalle, como el nombre de la tabla, su propietario, los campos, el tipo de dato de cada campo, su longitud, etc.:


|...COLUMN_NAME|	TYPE_NAME	|LENGHT|
| :--------: | :-------: | :--------: |
  | nombre|	varchar	|	30	|
  | clave|	varchar	|	10|

Para eliminar una tabla usamos "drop table" junto al nombre de la tabla a eliminar:

`drop table usuarios;`

Si intentamos eliminar una tabla que no existe, aparece un mensaje de error indicando tal situación y la sentencia no se ejecuta. Para evitar este mensaje podemos agregar a la instrucción lo siguiente:
```
 if object_id('usuarios') is not null
  drop table usuarios;
```
En la sentencia precedente especificamos que elimine la tabla "usuarios" si existe.

