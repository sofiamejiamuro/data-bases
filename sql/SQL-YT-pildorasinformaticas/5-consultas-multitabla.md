# CONSULTAS MULTITABLA

## Unión externa 

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

## Unión Interna
- Inner Join
- Left Join
- Right Join

