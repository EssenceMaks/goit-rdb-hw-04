# **Теми 4. DML та DDL команди. Складні SQL вирази**

## **p1_a**

![p1_a](/p1_a.png)

---

---

## **p1_b**

![p1_b](/p1_b.png)

---

---

## **p1_c**

![p1_c](/p1_c.png)

---

---

## **p1_d**

![p1_d](/p1_d.png)

---

---

## **p1_e**

![p1_e](/p1_e.png)

---

---

## **p1_f**

![p1_f](/p1_f.png)

---

---

## **p2**

![p2](/p2_a_b.png)

---
![p2](/p2_a_c.png)

---
![p2](/p2_d.png)

---

---

## **p3**

![p3](/p3.png)

---

---

## **p4_1**

![p4_1](/p4_1.png)

---

---

## **p4_2**

![p4_2](/p4_2.png)

---

---

## **p4_3**

![p4_3](/p4_3.png)

---

---

## **p4_4**

![p4_4](/p4_4.png)

---

---

## **p4_5**

![p4_5](/p4_5.png)

---

---

## **p4_6**

![p4_6](/p4_6.png)

---

---

## **p4_7**
---

---

![p4_7](/p4_7.png)

---

---
_______________________________________________________________________________________________________
Або замість  goit_csv_imports. використовувати   use goit_csv_imports


-- p4_3
use goit_csv_imports;
SELECT *
FROM orders
INNER JOIN employees ON orders.employee_id = employees.employee_id
WHERE employees.employee_id > 3 AND employees.employee_id <= 10;

-- p4_4
use goit_csv_imports;
SELECT 
    categories.name AS category_name,
    COUNT(*) AS total_orders,
    AVG(order_details.quantity) AS avg_quantity
FROM orders
INNER JOIN order_details ON orders.id = order_details.order_id
INNER JOIN products ON order_details.product_id = products.id
INNER JOIN categories ON products.category_id = categories.id
GROUP BY categories.name;

-- p4_5
use goit_csv_imports;
SELECT 
    categories.name AS category_name,
    COUNT(*) AS total_orders,
    AVG(order_details.quantity) AS avg_quantity
FROM orders
INNER JOIN order_details ON orders.id = order_details.order_id
INNER JOIN products ON order_details.product_id = products.id
INNER JOIN categories ON products.category_id = categories.id
GROUP BY categories.name
HAVING avg_quantity > 21;

-- p4_6
use goit_csv_imports;
SELECT 
    categories.name AS category_name,
    COUNT(*) AS total_orders,
    AVG(order_details.quantity) AS avg_quantity
FROM orders
INNER JOIN order_details ON orders.id = order_details.order_id
INNER JOIN products ON order_details.product_id = products.id
INNER JOIN categories ON products.category_id = categories.id
GROUP BY categories.name
HAVING avg_quantity > 21
ORDER BY total_orders DESC;

-- p4_7
use goit_csv_imports;
SELECT 
    categories.name AS category_name,
    COUNT(*) AS total_orders,
    AVG(order_details.quantity) AS avg_quantity
FROM orders
INNER JOIN order_details ON orders.id = order_details.order_id
INNER JOIN products ON order_details.product_id = products.id
INNER JOIN categories ON products.category_id = categories.id
GROUP BY categories.name
HAVING avg_quantity > 21
ORDER BY total_orders DESC
LIMIT 4 OFFSET 1;

