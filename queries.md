# Database Queries

### Display the ProductName and CategoryName for all products in the database. Shows 76 records.

SELECT productname, categoryname 
FROM categories as c
join products as p
on c.categoryID = p.categoryID;

### Display the OrderID and ShipperName for all orders placed before January 9, 1997. Shows 161 records.

SELECT orderID, shippername 
from orders as o
join shippers as s
on o.shipperID = s.shipperID
where orderdate<'1997-01-09';

### Display all ProductNames and Quantities placed on order 10251. Sort by ProductName. Shows 3 records.

SELECT productname, quantity
FROM products as p
join orderdetails as o
on p.productID = o.productID
where orderID = '10251';

### Display the OrderID, CustomerName and the employee's LastName for every order. All columns should be labeled clearly. Displays 196 records.

SELECT orderID, customerID, lastname as EmployeeLastname
FROM orders as o
join employees as e
on o.employeeID = e.employeeID;

### (Stretch)  Displays CategoryName and a new column called Count that shows how many products are in each category. Shows 9 records.

SELECT categoryname, count(*) as Count
FROM categories as c
join products as p
on c.categoryID = p.categoryID
group by c.categoryname;

### (Stretch) Display OrderID and a  column called ItemCount that shows the total number of products placed on the order. Shows 196 records. 

SELECT orderID, quantity as ItemCount
FROM orderdetails
group by orderID;