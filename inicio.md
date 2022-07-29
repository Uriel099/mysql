# principios de MySQL

## comandos para iniciar

<br>

para acceder a MySQL hay que iniciar un terminal o una aplicacion gráfica, en el caso de la terminal hay que dirigirse a la carpeta de la instalacion de MySQL y luego a la carpeta bin y ejecutar:

* **mysql -u** *"Usuario"* **-p** *"Base de datos"*
 
> `mysql -u root -p controlcore`

<br>

* **CREATE DATABASE** *"Nombre"*;
    * Este comando crea una base de datos con el nombre establecido por el usuario
> `CREATE DATABASE prueba;`

<br>

* **SHOW DATABASES;**
    * Gracias a este comando se pueden visualizar las bases de datos creadas en el gerstor
> `SHOW DATABASES;`

<br>

[Documentacion oficial de MySQL](https://dev.mysql.com/doc/)