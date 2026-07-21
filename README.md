## 1. ¿Por qué usaste LEFT JOIN para la Consulta 1 y no INNER JOIN? ¿Qué se perdería si usaras INNER JOIN?

Utilicé `LEFT JOIN` porque la consulta busca identificar los productos del catálogo que nunca fueron vendidos. Un `LEFT JOIN` devuelve todos los registros de la tabla de la izquierda (`productos`), incluso cuando no tienen una venta asociada. En el caso que hubiese utilizado `INNER JOIN`, solo aparecerían los productos que tienen una coincidencia en la tabla `ventas` y los productos **108 (Hub USB-C 7p)** y **109 (Parlante Bluetooth)** no aparecerían en el resultado, ya que nunca fueron vendidos. 

## 2. ¿Por qué usaste RIGHT JOIN para la Consulta 2? ¿Qué tabla está a la izquierda y cuál a la derecha?

Utilicé `RIGHT JOIN` porque la consulta busca mostrar las ventas de aquellos productos que no figuran en el catálogo. Es decir, que no tienen coincidencias en ambas tablas pero arroja los valores que solo aparecen en la tabla de ventas. 

En la consulta:

- La tabla **productos** está a la izquierda.
- La tabla **ventas** está a la derecha.

## 3. ¿Qué representan los valores NULL en cada resultado?

Los valores `NULL` indican que no existe valor, no hay coincidencia entre ambas tablas o cuando en algunas de las tablas no encentra valor en la otra. 

## 4. ¿Cuándo usarías FULL OUTER JOIN en un caso real de negocio?

Usaría `FULL OUTER JOIN` cuando necesite realizar una auditoría completa entre dos tablas relacionadas. 

Por ejemplo, en una tienda podría utilizarse para comparar el catálogo de productos con el historial de ventas y detectar:

- Productos que nunca fueron vendidos.
- Ventas registradas con productos inexistentes.
- Registros faltantes o errores de carga de datos.

Este tipo de consulta es útil para tareas de control de calidad de la información, conciliación de datos y auditorías, ya que muestra todos los registros de ambas tablas, tengan o no una coincidencia.
