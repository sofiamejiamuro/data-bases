# CONSULTAS DE CÁLCULO

Cada gestor de db tiene sus propias consultas de cálculo

- NOW(), dia y hora actuales
- DATEDIFF() --> diferencia enttre dos fechas
- DATE_FORMAT() --> formatear resultados
- CONCAT() --> concatenar
- ROUND()
- TRUNCATE()

```sql
USE tienda;
SHOW TABLES;
USE classicmodels;
SELECT * FROM products;
SELECT productName, buyPrice, buyPrice*1.16 AS 'precio_mas_iva' FROM products; 
SELECT productName, buyPrice, ROUND(buyPrice*1.16) AS 'precio_mas_iva' FROM products; 
# CON DOS DECIMALES
SELECT productName, buyPrice, ROUND(buyPrice*1.16,2) AS 'precio_mas_iva' FROM products; 
SELECT productName, buyPrice,MSRP, buyPrice-MSRP AS 'ganancia_por_producto' FROM products WHERE productLine = 'Classic Cars'; 

USE kavak;
SHOW TABLES;
SELECT * FROM car;
#Dias de diferencia, en MySQL no identifica el alias para el dia de hoy, entonces se pone la funcion 
SELECT name, post_date, NOW() AS 'hoy', DATEDIFF('hoy',post_date) AS 'Desde hace cuanto esta publicado el auto' FROM car; 
SELECT name, post_date, NOW() AS 'hoy', DATEDIFF(NOW(),post_date) AS 'Desde hace cuanto esta publicado el auto' FROM car; 
# Cambiar el formato de un campo fecha DATE_FORMAT(%D-%M-%Y)
SELECT name, post_date, DATE_FORMAT(NOW(),'%D-%M-%Y') AS 'hoy', DATEDIFF(NOW(),post_date) AS 'Desde hace cuanto esta publicado el auto' FROM car; 

```