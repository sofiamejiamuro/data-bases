# Subconsultas

Existen tres tipos de subconsultas

Una consulta es un SELECT dentro de otro SELECT, el SELECT hijo es un filtro del SELECT padre

- Suconsulta escalonada: El SELECT interno devuelve una unica columna con un único registro
- Subconsulta de lista: El SELECT interno en vez de devolver un unico registro devuelve una lista de registros, es muy comun usar los operadores IN, ANY, ALL

- Subconsulta correlacionada

EN las subconsultas se ocupan mucho los operadores

- Lógicos
  - AND
  - OR
  - NOT

- Comparación
  - LIKE
  - <,>, <=, >=
  - BETWEEN
  - IN
  - ANY
  - ALL

```SQL
# SUBCONSULTA escalonada
# E.g Obtener el nombre, el color y el precio de los autos que superen la media de precio, primero tengo que obtener la media y a partir de ese criterio obetner el nombre y el color de los autos

SELECT * FROM car;
# Esta primer consulta nos devuelve un único registro y un único campo
SELECT AVG(price) AS 'promedio' FROM car;

SELECT name, color, price FROM car WHERE price > (SELECT AVG(price) FROM car);

# Subconsulta de lista
# Obtener todos lo autos cuyo precio es superior a al precio de todos los x modelo de auto,es decir la primer consulta es para obtener los precios de todos los autos modelo MAZDA 3 (que todos tienen precios diferentes) y despues buscar todos los autos que sean mayores al precio maximo que salio de esa consulta3
# Primero obtenemos todos los precios de los Mazda 3 
SELECT price FROM car WHERE model = "Mazda 3" ORDER BY price DESC; 

# ALL indica que todos los registros deben cumplir la condicion, todos y cada uno de los resigtros
SELECT name, price FROM car WHERE price > ALL (SELECT price FROM car WHERE model = "Mazda 3" ORDER BY price DESC) ORDER BY price ASC;

# ANY cualquiera que nos devuelva la subconsulta, no necesariamente el mayor
SELECT name, price FROM car WHERE price > ANY (SELECT price FROM car WHERE model = "Mazda 3" ORDER BY price DESC) ORDER BY price ASC;
```