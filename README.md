# Práctica UNION y UNION ALL - RetailChain

## 1. ¿Cuántas filas devuelve cada consulta y por qué son distintas?

La consulta con `UNION` devolvió 11 registros, mientras que `UNION ALL` devolvió 14.

Esto sucede porque `UNION` elimina las filas duplicadas. En este caso, los productos con ID 103, 104 y 106 aparecían en ambas sucursales con el mismo `id_producto`, `nombre_producto` y `categoria`, por lo que se mostraron una sola vez.

`UNION ALL`, en cambio, conserva todos los registros.

## 2. ¿Por qué UNION ALL es más eficiente que UNION?

`UNION ALL` es más eficiente porque solamente combina los resultados de ambas consultas.

`UNION` realiza un proceso adicional para identificar y eliminar registros duplicados, lo que requiere mayor procesamiento.

## 3. ¿En qué casos de negocio usarías UNION y UNION ALL?

Un ejemplo de `UNION` sería combinar clientes de una tienda física y una tienda en línea para obtener una lista de clientes únicos.

Otro ejemplo sería combinar listas mensuales de representantes para conocer qué representantes distintos colocaron vasos promocionales durante el año.

`UNION ALL` podría utilizarse cuando se quieren conservar todas las compras de ambos canales o todos los registros mensuales de colocación de promocionales para después calcular el total.

## 4. ¿Qué ocurre si las consultas tienen diferente número de columnas o tipos de datos incompatibles?

Ambos `SELECT` deben tener la misma cantidad de columnas y tipos de datos compatibles.

Si tienen diferente número de columnas, SQL genera un error porque no puede combinar los resultados. Si los tipos de datos son incompatibles, puede producirse un error de conversión.
