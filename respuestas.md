## Pregunta 1 — Catálogo comercial activo

**Enunciado:** Lista todos los clientes con el número de pedidos que ha
El equipo de ventas prepara la tarifa de la próxima campaña y necesita el catálogo depurado.

Obtén los productos que **no** están descatalogados y cuyo precio unitario esté entre 10 y 50 euros, ambos incluidos. 
Muestra el nombre del producto y su precio redondeado a dos decimales, ordenado de mayor a menor precio.

**Consulta:**

```sql
-- Clientes con su volumen de pedidos, incluidos los que nunca han comprado
SELECT c.company_name AS cliente,
       c.country      AS pais,
       COUNT(o.order_id) AS num_pedidos
FROM customers c
LEFT JOIN orders o ON o.customer_id = c.customer_id
GROUP BY c.company_name, c.country
ORDER BY num_pedidos;
```

**Resultado:**

!Resultado pregunta 7

**Comentario:** He usado `COUNT(o.order_id)` en lugar de `COUNT(*)` porque...
