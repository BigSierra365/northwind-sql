# Ejercicios Prácticos

## Sección 1. Fundamentos: filtrado y agregación

## Pregunta 1 — Catálogo comercial activo

**Enunciado:** Obtén los productos que no están descatalogados y cuyo precio unitario esté entre 10 y 50 euros, ambos incluidos. Muestra el nombre del producto y su precio redondeado a dos decimales, ordenado de mayor a menor precio.

**Consulta:** 

```sql

```

**Resultado:**

![Resultado pregunta 1](./img/p01.png)

**Comentario:** 
He optado por usar CAST a DECIMAL(10,2) antes del ROUND() para asegurar precisión 
en cálculos monetarios, aunque ROUND() por sí solo hubiera funcionado. La consulta 
devuelve 52 productos activos en el rango de precio solicitado, ordenados de mayor 
a menor precio como se pedía.

---

## Pregunta 2 — Concentración geográfica de la cartera

**Enunciado:** Cuenta cuántos clientes hay en cada país y muestra únicamente aquellos países con 5 o más clientes, ordenados de mayor a menor. Indica también cuántas ciudades distintas hay en cada uno de esos países.

**Consulta:**

```sql

```

**Resultado:**

![Resultado pregunta 2](img/p02.png)

**Comentario:**

---

## Pregunta 3 — Alerta de reposición

**Enunciado:** Localiza los productos activos cuyas unidades en stock sean inferiores o iguales a su nivel de reposición. Muestra el nombre, las unidades en stock, el nivel de reposición, las unidades ya pedidas al proveedor y una columna de texto que indique `'CRÍTICO'` cuando el stock sea 0 y `'AVISO'` en el resto de casos.

**Consulta:**

```sql

```

**Resultado:**

![Resultado pregunta 3](img/p03.png)

**Comentario:**

---

## Sección 2. INNER JOIN

## Pregunta 4 — Ficha completa de producto

**Enunciado:** Para los productos suministrados por empresas de Italia, Francia o España, muestra el nombre del producto, el nombre de la categoría, el nombre del proveedor, su país y su ciudad. Ordena por país y, dentro de cada país, por nombre de producto.

**Consulta:**

```sql

```

**Resultado:**

![Resultado pregunta 4](img/p04.png)

**Comentario:**

---

## Pregunta 5 — Detalle valorizado de un pedido

**Enunciado:** Muestra, para el pedido 10248, el nombre del producto, el precio unitario aplicado, la cantidad, el descuento y el importe final de cada línea. Añade el nombre del cliente y la fecha del pedido.

**Consulta:**

```sql

```

**Resultado:**

![Resultado pregunta 5](img/p05.png)

**Comentario:**

---

## Pregunta 6 — Ranking de categorías por facturación

**Enunciado:** Calcula la facturación total de cada categoría durante toda la historia de la compañía. Muestra el nombre de la categoría, el número de líneas de pedido que ha generado, el número de productos distintos vendidos y la facturación total. Incluye únicamente las categorías que superen los 100.000 euros de facturación, ordenadas de mayor a menor.

**Consulta:**

```sql

```

**Resultado:**

![Resultado pregunta 6](img/p06.png)

**Comentario:**

---

## Sección 3. Uniones externas, reflexivas y cruzadas

## Pregunta 7 — Clientes sin actividad comercial

**Enunciado:** Lista todos los clientes con el número de pedidos que ha realizado cada uno y la fecha de su último pedido. Los clientes sin ningún pedido deben aparecer igualmente, con un 0 en el conteo y el texto `'SIN PEDIDOS'` en lugar de la fecha. Ordena de forma que los clientes inactivos aparezcan primero.

**Consulta:**

```sql

```

**Resultado:**

![Resultado pregunta 7](img/p07.png)

**Comentario:**

---

## Pregunta 8 — Organigrama de la fuerza de ventas

**Enunciado:** Muestra cada empleado con su nombre completo, su cargo, el nombre completo de la persona a la que reporta y el cargo de esa persona. El empleado que no reporta a nadie debe aparecer también, con el texto `'DIRECCIÓN GENERAL'` en el campo del responsable.

**Consulta:**

```sql

```

**Resultado:**

![Resultado pregunta 8](img/p08.png)

**Comentario:**

---

## Pregunta 9 — Rejilla de cobertura categoría × año

**Enunciado:** Genera todas las combinaciones posibles de las 8 categorías con los 3 años del histórico (24 filas) y asocia a cada combinación su facturación. Si una categoría no vendió nada en un año concreto, debe aparecer con un 0, no desaparecer de la tabla. Ordena por categoría y año.

**Consulta:**

```sql

```

**Resultado:**

![Resultado pregunta 9](img/p09.png)

**Comentario:**

---

## Pregunta 10 — Mapa de países: clientes frente a proveedores

**Enunciado:** Construye una única tabla que muestre, para cada país en el que la compañía tiene presencia, cuántos clientes y cuántos proveedores hay. Deben aparecer los países que solo tienen clientes, los que solo tienen proveedores y los que tienen ambos. Incluye una columna `tipo_presencia` que indique `'SOLO CLIENTES'`, `'SOLO PROVEEDORES'` o `'AMBOS'`.

**Consulta:**

```sql

```

**Resultado:**

![Resultado pregunta 10](img/p10.png)

**Comentario:**

---

## Sección 4. Operadores de conjunto

## Pregunta 11 — Directorio unificado de contactos

**Enunciado:** Construye una sola tabla que reúna los contactos de clientes, los de proveedores y los empleados. Cada fila debe indicar el origen (`'CLIENTE'`, `'PROVEEDOR'`, `'EMPLEADO'`), el nombre de la persona de contacto en mayúsculas, la organización a la que pertenece, la ciudad y el país. Para los empleados, la organización es el literal `'NORTHWIND TRADERS'` y el nombre de contacto se forma concatenando nombre y apellidos. Ordena por origen y luego por país.

**Consulta:**

```sql

```

**Resultado:**

![Resultado pregunta 11](img/p11.png)

**Comentario:**

---

## Pregunta 12 — Mercados con desequilibrio

**Enunciado:** Resuelve las dos preguntas en dos consultas independientes:
- **a)** Países donde hay clientes pero **ningún** proveedor.
- **b)** Países donde hay **a la vez** clientes y proveedores.

Ordena ambos resultados alfabéticamente.

**Consulta (a) — Países solo con clientes:**

```sql

```

**Resultado:**

![Resultado pregunta 12a](img/p12a.png)

**Consulta (b) — Países con clientes y proveedores:**

```sql

```

**Resultado:**

![Resultado pregunta 12b](img/p12b.png)

**Comentario:**

---

## Sección 5. Subconsultas

---

## Pregunta 13 — Clientes que nunca han comprado pescado

**Enunciado:** Localiza los clientes que nunca han incluido un producto de la categoría `'Seafood'` en ninguno de sus pedidos. Muestra el nombre del cliente, su país y el número total de pedidos que sí ha realizado, de mayor a menor.

**Consulta:**

```sql

```

**Resultado:**

![Resultado pregunta 13](img/p13.png)

**Comentario:**

---

## Pregunta 14 — Productos por encima de la media

**Enunciado:** Muestra los productos activos cuyo precio unitario supere el precio medio de todo el catálogo. Incluye en cada fila el precio del producto, el precio medio general y la diferencia entre ambos, todo redondeado a dos decimales. Ordena por diferencia descendente.

**Consulta:**

```sql

```

**Resultado:**

![Resultado pregunta 14](img/p14.png)

**Comentario:**

---

## Pregunta 15 — Ticket medio por cliente

**Enunciado:** Calcula, para cada cliente que haya comprado alguna vez, el número de pedidos, el importe total acumulado y el importe medio por pedido. Muestra los 15 clientes con mayor ticket medio.

El cálculo tiene dos niveles: primero obtén el importe de cada pedido sumando sus líneas, y solo después promedia esos importes por cliente.

**Consulta:**

```sql

```

**Resultado:**

![Resultado pregunta 15](img/p15.png)

**Comentario:**

---

## Sección 6. Subconsultas correlacionadas y CTE

---

## Pregunta 16 — El producto más caro de cada categoría

**Enunciado:** Para cada categoría, muestra el producto con el precio unitario más alto. Incluye el nombre de la categoría, el nombre del producto, su precio y el precio medio de su categoría.

Resuélvelo con una subconsulta correlacionada: para cada producto, comprueba si su precio coincide con el máximo de su propia categoría.

**Consulta:**

```sql

```

**Resultado:**

![Resultado pregunta 16](img/p16.png)

**Comentario:**

---

## Pregunta 17 — Segmentación ABC de la cartera de clientes

**Enunciado:** Usando expresiones de tabla común (CTE), construye una consulta que:

1. Calcule la facturación total de cada cliente.
2. Divida los clientes en cuartiles según esa facturación.
3. Asigne una etiqueta de segmento: `'A - Estratégico'` al cuartil superior, `'B - Consolidado'` al segundo, `'C - Ocasional'` al tercero y `'D - Marginal'` al cuarto.
4. Devuelva, por segmento, el número de clientes, la facturación total del segmento y el porcentaje que representa sobre el total de la compañía.

**Consulta:**

```sql

```

**Resultado:**

![Resultado pregunta
