# AGRUPACIONES
```sql
# EL having sustituye al where en las consultas de agrupaciones
SELECT color, AVG(price) AS 'avg_color' FROM car GROUP BY color HAVING color = 'negro' OR color = 'blanco';
# Regresa una columna con el atributop de color y una columna con el avg_price y dos registros, los del los autos colos negro y los de los autos color blanco


# Cuántos carros hay por color? Recurda: un campo para agrupar y un campo para contar
# COUNT() no cuenta registros en blanco
SELECT color , COUNT(color) FROM car GROUP BY color;
# A diferencia del ejemplo de arriba me da los registros con todos los colores en la columna color porque no tiene restircciones y la columna de operación es contar cuantos registros por color


# Agrupar por modelo de la auto
SELECT  model, COUNT(model) FROM car GROUP BY model;


# EL precio mas alto por color de carro
SELECT color, MAX(price) FROM car Group BY color;


#EL precio más alto de los carros color dorado
SELECT color, MAX(price) FROM car  WHERE color = 'dorado' Group BY color;

#solo lleva dos elementos la consulta de agrupación
```

