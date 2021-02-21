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

