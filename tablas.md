# tablas

Las tablas son elementos dentro de la base de datos donde se almacenarán nuestros datos, estas al igual que todo en SQL se crean con peticiones al SGBD. Los comandos de creacion y modificacion son los siguientes:

<br>

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
    |NULL           | el dato puede ser nulo   |
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
    texto varchar(255) NULL,
    caracter char NOT NULL.
    fecha date NOT NULL,
    fecha_hora datetime NULL,
);
~~~