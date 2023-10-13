- select customers who have bought both a keyboard or a mouse
```sql
SELECT c.*
FROM customers c
INNER JOIN Orders o ON c.customer_id = o.customer_id
WHERE o.item = "Keyboard" OR o.item = "Mouse";
```

-  select the youngest customer, what they have ordered, and their shipping status.
```sql
SELECT c.first_name, c.last_name, c.age, o.item, s.status
FROM customers c, orders o, shippings s
WHERE age = (select min(age) from customers) AND o.customer_id = c.customer_id AND s.customer = c.customer_id;
```


-  select all the customers who have ordered items that start with M.

```sql
SELECT c.*
FROM customers c, orders o
WHERE o.item LIKE "M%" AND c.customer_id = o.customer_id;
```

-  select the customer details who has ordered the most expensive product.

```sql
SELECT c.*
FROM customers c, orders o
WHERE o.amount = (select max(o.amount) from orders o) AND c.customer_id = o.customer_id;
```


-  select all the products that are above 400 price range and are in pending state.

```sql
SELECT o.*
FROM orders o, shippings s
WHERE o.amount > 400 AND s.status = "Pending" AND o.customer_id = s.customer;
```