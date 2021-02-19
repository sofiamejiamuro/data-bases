# CONSULTAS MULTITABLA

## Unión externa 

Se unen dos tablas para hacer una consulta

Operadores

- Union
- Union All

Los siguientes operadores no son soportados por todos los gestores de bd
- Except 
- Intersect
- Minus

### UNION
Para poder utilizar este operador es necesario cumplir algunos requisitos
- Las tablas deben tener el mismo numero de campos
- Los campos deben tener tipos de datos compatibles
- Pueden tener nombre de campo diferente. Cuando se juntan las tablas los campos se quedan con el nombre de la primer tabla

Si hay registros repetidos no muestra los duplicados, mostrando sólo el de la tabla 1

### UNION ALL
Es igual que UNION la diferencia es que sí muestra los duplicados


```sql

# UNION
SELECT * FROM productos WHERE sección='deportes' UNION SELECT * FROM productosNuevos WHERE seccion='deportes_de_riesgo';
# Mismo número de campos en las dos consultas auqnue tengan nombres diferentes
SELECT name, product, id FROM productos WHERE sección='deportes' UNION SELECT nombre, producto, num_id FROM productosNuevos WHERE seccion='deportes_de_riesgo';
# Con esta consulta me daria como primeros registros los de la tabla uno que cumplieran la condición y después los de la segunda tabla que cumplieran la otra condición
SELECT * FROM productos  WHERE precio<500 UNION SELECT * FROM productosNuevos WHERE seccion='alta_costura';

# Union de multiples tablas
SELECT name, product, id FROM productos WHERE sección='deportes' UNION SELECT nombre, producto, num_id FROM productosNuevos WHERE seccion='deportes_de_riesgo' UNION SELECT nombre, producto, num_id FROM productosMasNuevos WHERE seccion='deportes_de_baja_intensidad';

#UNION ALL 

```
## Unión Interna
- Inner Join
- Left Join
- Right Join

```sql
# 18 de fevereiro
# LeftJoin y rigth join tambien conocidos como outter join

use classicmodels;
SHOW TABLES;
SELECT * FROM customers;
SELECT * FROM orderdetails;
SELECT * FROM orders;
SELECT * FROM products;
SELECT * FROM offices;
SELECT * FROM employees;
# e.i. cada cliente puede realizar varios pedidos. es una relación de 1 a varios, 1:N, por eso tablas relacionales

# JOINS
# hacer consultas entre ambas tablas
# INNER JOIN, informacion común a ambas tablas
# Left JOIN nos devuelve la informacion en comun a las dost ablas y todos los registros del lado izquierdo de la query
# RIGHT JOIN

# e.g. 1 
# a travez de que campo se relacionan ambas tablas. customerNumber
SELECT * FROM customers INNER JOIN orders ON customers.customerNumber = orders.customerNumber;
# Me va a regresar todos los que compartan este customerNumber, en este caso todos

#e.g. 2 
# Unir las dos tablas a través del campo office code, estamos uniendo las tablas por el campo que tienen en comun, entonces dame la informacion del empleado y de su oficina
SELECT * FROM employees INNER JOIN offices ON employees.officeCode = offices.officeCode; 
SELECT * FROM employees INNER JOIN offices ON employees.officeCode = offices.officeCode WHERE jobTitle = "VP Sales";
SELECT * FROM employees INNER JOIN offices ON employees.officeCode = offices.officeCode WHERE jobTitle = "Sales Rep";
# Ahora regresame estas tres columnas que vienen de las dos tablas 
SELECT jobTitle, employeeNumber, phone FROM employees INNER JOIN offices ON employees.officeCode = offices.officeCode WHERE jobTitle = "Sales Rep";
```

![img-6](./assets/img-6.png)

![img-7](./assets/img-7.png)

![img-8](./assets/img-8.png)