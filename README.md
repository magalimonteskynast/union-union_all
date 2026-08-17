**¿Cuántas filas devuelve cada consulta y por qué son distintas? Explicá con ejemplos concretos de los datos qué filas se eliminaron 
con UNION.**
La consulta 1 (UNION) devuelve 11 filas mientras que la consulta 2 (UNION ALL) devuelve 14 filas. Son distintas ya que UNION elimina aquellas
filas duplicadas mientras que UNION ALL mantiene todas las filas, incluso aquellas que se encuentran duplicadas. 
Un ejemplo concreto de filas eliminadas en la consulta 1 utilizando UNION son el ID 103, 104 y 106, productos que se repiten en ambas sucursales y,
como se busca un catálogo unificado de ambas, sin precisar el stock, se eliminan al utilizar UNION.

**¿Por qué UNION ALL es más eficiente que UNION? ¿Qué operación adicional realiza UNION internamente que consume más recursos?**
UNION ALL es más eficiente que UNION ya que es más rápido y menos costoso, combinando todos los datos sin utilizar ningún filtro. Por el contrario,
UNION es más costoso y realiza filtros previo a mostrar el resultado final ya que debe evaluar primeramente el contenido de las filas para excluir 
aquellas que se encuentran duplicadas.

**¿En qué casos de negocio usarías cada uno? Dá al menos dos ejemplos reales distintos a los del ejercicio.**
**UNION**: para ver el listado unificado de vendedores de la empresa incluyendo todas las sucursales, o bien listar todas las campañas de marketing 
llevadas a cabo en distintas plataformas (por ejemplo, incluyendo Meta, Google, Display, etc.)
**UNION ALL**: para ver las ventas realizadas por los vendedores de las diferentes sucursales de la compañía (considerando que los vendedores pueden rotar
entre las distintas sucursales), o bien para identificar campañas con el mismo nombre pertenecientes a distintas plataformas de anuncios.

**¿Qué pasa si las columnas de ambas consultas no coinciden en número o tipo? ¿Qué error genera SQL?**
El hecho de que las columnas coincidan en número y tipo es un aspecto y condición fundamental para llevar a cabo los operadores UNION y UNION ALL. Si
esto no se cumple, entonces SQL traerá el siguiente error: "All queries combined using a UNION, INTERSECT or EXCEPT operator must have an equal number 
of expressions in their target lists." En el caso de que no coincidan en tipo de dato, SQL genera un error de conversión.
