# AGRUPACIONES
```sql
# EL having sustituye al where en las consultas de agrupaciones
SELECT color, AVG(price) AS 'avg_color' FROM car GROUP BY color HAVING color = 'negro' OR color = 'blanco';
# Cuántos carros hay por color? Recurda: un campo para agrupar y un campo para contar
# COUNT() no cuenta registros en blanco
SELECT c,olor COUNT(color) FROM car GROUP BY color;
# EL precio del carro más caro por modelo
SELECT  model, COUNT(model) FROM car GROUP BY model;
SELECT  name, COUNT(model) AS 'model' FROM car GROUP BY name;
# EL precio mas alto por color de carro
SELECT color, MAX(price) FROM car Group BY color;
#EL precio más alto por color de carrro dorado
SELECT color, MAX(price) FROM car  WHERE color = 'dorado' Group BY color;
#solo lleva dos elementos la consulta de agrupación
```

