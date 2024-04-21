# Query SQL con JOIN

Le "join" in SQL sono utilizzate per combinare righe da due o più tabelle basandosi su una condizione di collegamento tra di esse. Questa condizione di collegamento è specificata nella clausola JOIN della query SQL. Le join sono fondamentali quando si desidera estrarre informazioni da più tabelle correlate in un unico risultato.

## INNER JOIN

L'INNER JOIN restituisce solo le righe che hanno corrispondenze in entrambe le tabelle coinvolte.

```sql
SELECT
    customers.customer_id,
    customers.customer_name,
    orders.order_id,
    orders.order_date
FROM
    customers
INNER JOIN
    orders ON customers.customer_id = orders.customer_id;
