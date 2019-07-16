# java-sql

A student that completes this project shows that they can:
* Query data from a single table
* Query data from multiple tables
* Create a new datadaase using PostgreSQL

# Introduction

Working with SQL

# Instructions

Surf to [SQL Try Editor at W3Schools.com](https://www.w3schools.com/Sql/tryit.asp?filename=trysql_select_top)  

### **Clicking the `Restore Database` button in the page will repopulate the database with the original data and discard all changes you have made**.

Answer the following data queries. Keep track of the SQL you write by pasting it into this document under its appropriate header below. You will be submitting that through the regular fork, change, pull process.

<details>
<summary><strong>find all customers that live in London. Returns 6 records.</strong></summary>

```
SELECT *
FROM Customers
WHERE City = "London";

CustomerID    CustomerName            ContactName         Address                        City     PostalCode   Country
4             Around the Horn         Thomas Hardy        120 Hanover Sq.                London   WA1 1DP      UK
11            B's Beverages           Victoria Ashworth   Fauntleroy Circus              London   EC2 5NT      UK
16            Consolidated Holdings   Elizabeth Brown     Berkeley Gardens 12 Brewery    London   WX1 6LT      UK
19            Eastern Connection      Ann Devon           35 King George                 London   WX3 6FW      UK
53            North/South             Simon Crowther      South House 300 Queensbridge   London   SW7 1RZ      UK
72            Seven Seas Imports      Hari Kumar          90 Wadhurst Rd.                London   OX15 4NB     UK
```
</details>

<details>
<summary><strong>find all customers with postal code 1010. Returns 3 customers.</strong></summary>

```
SELECT *
FROM Customers
WHERE PostalCode = "1010";

CustomerID   CustomerName                 ContactName        Address                               City           PostalCode   Country
12           Cactus Comidas para llevar   Patricio Simpson   Cerrito 333                           Buenos Aires   1010         Argentina
54           Océano Atlántico Ltda.       Yvonne Moncada     Ing. Gustavo Moncada 8585 Piso 20-A   Buenos Aires   1010         Argentina
64           Rancho grande                Sergio Gutiérrez   Av. del Libertador 900                Buenos Aires   1010         Argentina
```
</details>

<details>
<summary><strong>find the phone number for the supplier with the id 11. Should be (010) 9984510.</strong></summary>

```
SELECT Phone
FROM Suppliers
WHERE SupplierID = "11";

Phone
(010) 9984510
```
</details>

<details>
<summary><strong>list orders descending by the order date. The order with date 1997-02-12 should be at the top.</strong></summary>
> This can be done with SELECT, WHERE, and ORDER BY clauses
</details>

<details>
<summary><strong>find all suppliers who have names longer than 20 characters. You can use `length(SupplierName)` to get the length of the name. Returns 11 records.</strong></summary>
> This can be done with SELECT and WHERE clauses
</details>

<details>
<summary><strong>find all customers that include the word "market" in the name. Should return 4 records.</strong></summary>
> This can be done with SELECT and a WHERE clause using the LIKE keyword

> Don't forget the wildcard '%' symbols at the beginning and end of your substring to denote it can appear anywhere in the string in question
</details>

<details>
<summary><strong>add a customer record for <em>"The Shire"</em>, the contact name is <em>"Bilbo Baggins"</em> the address is <em>"1 Hobbit-Hole"</em> in <em>"Bag End"</em>, postal code <em>"111"</em> and the country is <em>"Middle Earth"</em>.</strong></summary>
> This can be done with the INSERT INTO clause
</details>
 
<details>
<summary><strong>update <em>Bilbo Baggins</em> record so that the postal code changes to <em>"11122"</em>.</strong></summary>
> This can be done with UPDATE and WHERE clauses
</details>
 
<details> 
<summary><strong>list orders grouped by customer showing the number of orders per customer. <em>Rattlesnake Canyon Grocery</em> should have 7 orders.</strong></summary>
> This can be done with SELECT, COUNT, JOIN and GROUP BY clauses. Your count should focus on a field in the Orders table, not the Customer table

> There is more information about the COUNT clause on [W3 Schools](https://www.w3schools.com/sql/sql_count_avg_sum.asp)
</details>
 
<details>
<summary><strong>list customers names and the number of orders per customer. Sort the list by number of orders in descending order. <em>Ernst Handel</em> should be at the top with 10 orders followed by <em>QUICK-Stop</em>, <em>Rattlesnake Canyon Grocery</em> and <em>Wartian Herkku</em> with 7 orders each.</strong></summary>
> This can be done by adding an ORDER BY clause to the previous answer
</details>
 
<details>
<summary><strong>list orders grouped by customer's city showing number of orders per city. Returns 58 Records with <em>Aachen</em> showing 2 orders and <em>Albuquerque</em> showing 7 orders.</strong></summary>
> This is very similar to the previous two queries, however, it focuses on the City rather than the CustomerName
</details>

<details>
<summary><strong>Data Normalization</strong></summary>

Note: This step does not use PostgreSQL!

Take the following data and normalize it into a 3NF database.

| Person Name | Pet Name | Pet Type | Pet Name 2 | Pet Type 2 | Pet Name 3 | Pet Type 3 | Fenced Yard | City Dweller |
|-------------|----------|----------|------------|------------|------------|------------|-------------|--------------|
| Jane        | Ellie    | Dog      | Tiger      | Cat        | Toby       | Turtle     | No          | Yes          |
| Bob         | Joe      | Horse    |            |            |            |            | No          | No           |
| Sam         | Ginger   | Dog      | Miss Kitty | Cat        | Bubble     | Fish       | Yes         | No           |
</details>

---
## Stretch Goals

<details>
<summary><strong>delete all customers that have no orders. Should delete 17 (or 18 if you haven't deleted the record added) records.</strong></summary>
> This is done with a DELETE query

> In the WHERE clause, you can provide another list with an IN keyword this list can be the result of another SELECT query. Write a query to return a list of CustomerIDs that meet the criteria above. Pass that to the IN keyword of the WHERE clause as the list of IDs to be deleted
 
> Use a LEFT JOIN to join the Orders table onto the Customers table and check for a NULL value in the OrderID column
</details>
 
<details>
<summary><strong>Create Database and Table</strong></summary>

### Keep track of the code you write and paste at the end of this document

- use pgAdmin to create a database, naming it `budget`.
- add an `accounts` table with the following _schema_:

  - `id`, numeric value with no decimal places that should autoincrement.
  - `name`, string, add whatever is necessary to make searching by name faster.
  - `budget` numeric value.

- constraints
  - the `id` should be the primary key for the table.
  - account `name` should be unique.
  - account `budget` is required.
</details>
