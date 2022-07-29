# tablas

Las tablas son elementos dentro de la base de datos donde se almacenarán nuestros datos, estas al igual que todo en SQL se crean con peticiones al SGBD. Los comandos de creacion y modificacion son los siguientes:

<br>

## Crear tabla

* **CREATE TABLE** Nombre_tabla(columna1 tipo, columna2 tipo, ...) **;**

    * Este comando crea una tabla dentro de la base de datos seleccionada, se tiene que establecer el nombre de la tabla despues de create table y entre parentesis definir las columnas con su nombre y su tipo de dato.

    tipos de datos más importantes:
    
    | Tipo     | descripcion      |
    |----------|------------------|
    | int      | numeros enteros  |
    | varchar(n)  | cadenas de texto |
    | char     | carácter         |
    | date     | fechas           |
    | datetime | fecha con hora   |
    | boolean | dato cuyo valor es true o false   |

    De igual manera se puede definir si se requiere que el dato no sea nulo

    |tipo           |  descipcion              |
    |---------------|--------------------------|
    |DEFAULT NULL           | el dato puede ser nulo   |
    |NOT NULL       | el dato no puede ser nulo|
    |AUTO_INCREMENT | este tipo solo puede ser aplicado a enteros y cada que se registre algo nuevo este dato será secuencial al dato anterior|

    establecer llaves
    |tipo                | descripcion               |
    |--------------------|---------------------------|
    |PRIMARY KEY(columna)| Este comando establece la llave primaria, la llave primaria es NOT NULL por defecto|
    |FOREIGN KEY(columna) REFERENCES Tabla(Columna)| Este comando establece las relaciones entre tablas| 
~~~
CREATE TABLE prueba(
    ID int NOT NULL AUTO_INCREMENT,
    texto varchar(255) DEFAULT NULL,
    caracter char NOT NULL.
    fecha date NOT NULL,
    fecha_hora datetime DEFAULT NULL,
    status boolean,
    PRIMARY KEY(ID),
    FOREIGN KEY(status) REFERENCES Tabla(prueba) ON DELETE CASCADE
);
~~~

<br>

* **SHOW DATABASES;**
    * Al ejecutar este comando el SGBD nos mostrará todas las tablas dentro de la base de datos que estemos utilizando en ese momento
~~~ 
SHOW DATABASES
~~~

<br>

* **SHOW CREATE TABLE** tabla **;**
    * Al ejecutar este comando el SGBD nos mostrará el comando para crear la tabla, es muy util cuando hemos modificado la tabla.
~~~ 
SHOW CREATE TABLE prueba;
~~~

<br>

## Modificar tablas

* **ALTER TABLE** tabla **MODIFY COLUMN** columna tipo extra **;**
    * Gracias a este comando podemos modificar columnas ya hechas en nuestar tabla
~~~ 
ALTER TABLE prueba MODIFY COLUMN ID int AUTO_INCREMENT;
~~~

<br>

* **ALTER TABLE** tabla **ADD** columna tipo extra **AFTER** columna **;**
    * Gracias a este comando agregar una nueva columna a la tabla y podemos elegir su posicion gracias a *AFTER* de lo contrario la nueva columna será enviada hasta la ultima columna
~~~ 
ALTER TABLE prueba ADD Nombre varchar(255) NOT NULL AFTER columna1;
~~~

<br>

* **ALTER TABLE** tabla **DROP** columna **;**
    * Con esta peticion podemos eliminar una columna, este comando elimina al igual los registros de esa columna.
~~~ 
ALTER TABLE prueba DROP Nombre;
~~~