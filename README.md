# Business Management SQL Documentation

This project contains a set of SQL queries designed to retrieve important business information from the `business_managment` database. Each query is used to inspect a specific part of the organization’s operations, including payments, orders, employee records, office locations, and product inventory.

## Database Used

```sql
USE business_managment;
```

The queries run against the `business_managment` database, which stores records related to company operations and internal business data.

---

## 1. Payment Records

```sql
SELECT checkNumber, paymentDate, amount 
FROM payments;
```

### Purpose
Retrieves a list of all payment transactions from the `payments` table.

### Returned Data
- `checkNumber`: the payment reference code
- `paymentDate`: the date the payment was made
- `amount`: the payment amount

### Business Use
This query helps finance and accounting teams review customer or vendor payment activity.

---

## 2. Orders in Progress

```sql
SELECT orderDate, requiredDate, status 
FROM orders 
WHERE status = 'In Process' 
ORDER BY orderDate DESC;
```

### Purpose
Displays all orders whose status is `In Process`, ordered from newest to oldest.

### Returned Data
- `orderDate`: when the order was placed
- `requiredDate`: the requested delivery date
- `status`: the order state

### Business Use
This is useful for operations or fulfillment teams to identify orders that are currently being processed and prioritize follow-up work.

---

## 3. Sales Representatives

```sql
SELECT firstName, lastName, email 
FROM employees 
WHERE jobTitle = 'Sales Rep' 
ORDER BY employeeNumber DESC;
```

### Purpose
Lists all employees whose job title is `Sales Rep`, sorted by employee number in descending order.

### Returned Data
- `firstName`: employee first name
- `lastName`: employee last name
- `email`: employee email address

### Business Use
This helps management or HR quickly view the current sales team and their contact information.

---

## 4. Office Information

```sql
SELECT * 
FROM offices;
```

### Purpose
Returns all data stored in the `offices` table.

### Returned Data
This query returns every column in the `offices` table, which typically includes details about company office locations and contact information.

### Business Use
This provides a complete overview of company branches or office locations for administrative and reporting purposes.

---

## 5. Cheapest Products by Purchase Price

```sql
SELECT productName, quantityInStock 
FROM products 
ORDER BY buyPrice ASC 
LIMIT 5;
```

### Purpose
Shows the five products with the lowest purchase price, along with their current stock quantity.

### Returned Data
- `productName`: product name
- `quantityInStock`: number of units currently available

### Business Use
This query is useful for inventory analysis, procurement review, and identifying lower-cost products in stock.

---

## Summary

These queries provide a practical overview of the business management database and support common operational tasks such as:

- reviewing payment activity
- tracking active orders
- viewing sales staff contacts
- checking company office details
- analyzing stock and purchasing data

This set of queries is a simple reporting layer for business operations and administrative monitoring.
