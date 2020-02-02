# SQL COMMANDS AND TIPS

### General Select Commands
 - These queries only work with Chinook
 
> SELECT Name from Artist; - Returns All artist names;  
> SELECT Name From MediaType;  

### General Where Clause

> SELECT * FROM Track WHERE Composer = 'U2';  
> SELECT * FROM Album WHERE AlbumId = 232;
> SELECT FirstName, LastName, Title FROM Employee WHERE Title = 'IT Staff';

### Order By
> SELECT * FROM Album ORDER BY Title;   
> SELECT * FROM Album ORDER BY Title desc;  
> SELECT * FROM Album ORDER BY ArtistId, Title;  

````mysql
SELECT InvoiceDate, BillingCity, Total From Invoice   
Order BY Total Desc  
LIMIT 5;
````

### Count
````mysql
SELECT COUNT(*) FROM Customer;
````

````mysql
SELECT COUNT(FirstName) FROM Customer;
````

````mysql
SELECT COUNT(*) FROM Customer
WHERE FirstName = 'Frank';
````

### Min Function
````mysql
SELECT MIN(LastName) From Customer;
````

### Min Function
````mysql
SELECT MAX(LastName) From Customer;
````

### AVG Function
````mysql
SELECT AVG(Total) FROM Invoice;
````

### ROUND Function
````mysql
SELECT ROUND(AVG(Total), 2) FROM Invoice;
````

### SUM Function
````mysql
SELECT TOTAL FROM Invoice
    -> WHERE InvoiceId = 2;
````
````mysql
SELECT SUM(UnitPrice * Quantity) FROM InvoiceLine
    -> WHERE InvoiceId = 2;
````

### The GROUP BY Clause
````mysql
SELECT COUNT(*) FROM Track
    -> GROUP BY AlbumId;
````

````mysql
SELECT AlbumId, COUNT(*) FROM Track
    -> GROUP BY AlbumId;
````

````mysql
SELECT Album.Title, COUNT(*) FROM Track
    -> INNER JOIN Album ON Track.AlbumId = Album.AlbumId
    -> GROUP BY Track.AlbumId;
````

````mysql
SELECT AlbumId, MIN(UnitPrice) FROM Track
    -> GROUP BY AlbumId;
````

````mysql
SELECT AlbumId, MAX(UnitPrice)  FROM Track
    -> GROUP BY AlbumId;
````

````mysql
SELECT AlbumId, ROUND(SUM(UnitPrice), 2) FROM Track
    -> GROUP BY AlbumId;
````

````mysql
SELECT Album.Title, ROUND(SUM(UnitPrice), 2) FROM Track
    -> INNER JOIN Album ON Track.AlbumId = Album.AlbumId
    -> GROUP BY Track.AlbumId;
````

### The INSERT Statement
````mysql
INSERT INTO MediaType (Name)
    -> VALUES ("Test Media Type 1");
````

````mysql
INSERT INTO Album (Title, ArtistId)
    -> VALUES ("Boy", 150);
````








### Pro tip
- Enable output of sql commands to file  
> tee file.txt - Enable  
> notee - Disable  
> Show Tables