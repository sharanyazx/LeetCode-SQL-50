# LeetCode-SQL-50-Solutions

## Description 
The SQL 50 on LeetCode provided an extensive collection of SQL problems covering a wide range of concepts and techniques.
This challenge included easy, medium and hard level questions from various topics like-
- Selects
- Basic Joins
- Basic Aggregate Functions
- Sorting and grouping
- Advanced Select and joins
- Subqueries
- Advanced String Functions / Regex / Clause

## Here is an overview of the concept that helps to solve SQL 50  


---

### 1. **Selects**

The `SELECT` statement is used to query a database and retrieve specific data from one or more columns in a table.

#### Example: Simple Select

```sql
SELECT name, population FROM World WHERE area >= 3000000;
```

- **Explanation**: This query selects the `name` and `population` columns from the `World` table where the `area` is greater than or equal to 3,000,000 square kilometers.

#### Key Concepts:
- **Basic Select**: Fetches data from a table.
- **WHERE clause**: Filters data based on conditions.

---

### 2. **Basic Joins**

A `JOIN` operation is used to combine data from two or more tables based on a related column.

#### Example: Inner Join

```sql
SELECT customer.name, order.amount
FROM customer
JOIN order ON customer.id = order.customer_id;
```

- **Explanation**: This query retrieves the names of customers and the amount of their orders by joining the `customer` and `order` tables on the `customer.id` and `order.customer_id` columns.

#### Key Concepts:
- **INNER JOIN**: Returns rows where there is a match in both tables.
- **ON clause**: Specifies the condition for the join (matching columns).

---

### 3. **Basic Aggregate Functions**

Aggregate functions perform a calculation on multiple rows and return a single result.

#### Example: `COUNT`

```sql
SELECT COUNT(*) FROM customer WHERE referee_id IS NOT NULL;
```

- **Explanation**: This query counts how many customers were referred by another customer (i.e., `referee_id` is not `NULL`).

#### Key Concepts:
- **COUNT()**: Returns the number of rows matching the condition.
- **AVG()**, **SUM()**, **MIN()**, and **MAX()** are also common aggregate functions.

---

### 4. **Sorting and Grouping**

Sorting arranges the results in a particular order, while grouping organizes data into sets based on certain column values.

#### Example: Sorting and Grouping

```sql
SELECT customer_id, SUM(amount) AS total_amount
FROM order
GROUP BY customer_id
ORDER BY total_amount DESC;
```

- **Explanation**: This query calculates the total amount for each customer and sorts the result in descending order based on `total_amount`.

#### Key Concepts:
- **GROUP BY**: Groups rows based on one or more columns.
- **ORDER BY**: Sorts the result set in ascending or descending order.

---

### 5. **Advanced Select and Joins**

These include using more complex joins, such as `LEFT JOIN`, `RIGHT JOIN`, and `FULL JOIN`, and more advanced techniques like `DISTINCT` and subqueries.

#### Example: Left Join

```sql
SELECT employee.name, department.name
FROM employee
LEFT JOIN department ON employee.department_id = department.id;
```

- **Explanation**: This query selects the names of employees along with their department names, but even employees without a department will be included (as a result of the `LEFT JOIN`).

#### Key Concepts:
- **LEFT JOIN**: Returns all rows from the left table, even if there is no match in the right table.
- **RIGHT JOIN**: Returns all rows from the right table, even if there is no match in the left table.
- **FULL JOIN**: Returns all rows when there is a match in either the left or right table.

---

### 6. **Subqueries**

A subquery is a query within another query. It can be used in `WHERE`, `SELECT`, or `FROM` clauses.

#### Example: Subquery in `WHERE` clause

```sql
SELECT name, age
FROM employee
WHERE department_id IN (SELECT id FROM department WHERE name = 'Sales');
```

- **Explanation**: This query retrieves the names and ages of employees who belong to the 'Sales' department.

#### Key Concepts:
- **Subquery**: A nested query used inside another query to filter or compute results.
- **IN**: Checks if a value matches any value in the list returned by the subquery.

---

### 7. **Advanced String Functions / Regex / Clause**

SQL provides string functions and regex capabilities to manipulate or match string patterns.

#### Example: Using `REGEXP`

```sql
SELECT name
FROM customer
WHERE name REGEXP '^A';
```

- **Explanation**: This query retrieves the names of customers whose names start with the letter 'A' (using regex).

#### Key Concepts:
- **REGEXP**: Used to perform regular expression pattern matching.
- **String Functions**: Functions like `CONCAT()`, `SUBSTRING()`, `LOWER()`, `UPPER()` allow for string manipulation.
- **LIKE**: Another pattern matching operator (e.g., `WHERE name LIKE 'A%'`).

---



### Summary of Concepts with Examples:

1. **Selects**: Basic retrieval of data using the `SELECT` statement.
2. **Basic Joins**: Combining data from multiple tables, such as `INNER JOIN` and `LEFT JOIN`.
3. **Basic Aggregate Functions**: Performing calculations like `COUNT()`, `SUM()`, etc., over groups of rows.
4. **Sorting and Grouping**: Sorting results (`ORDER BY`) and grouping rows for aggregate functions (`GROUP BY`).
5. **Advanced Select and Joins**: Using advanced `JOIN` types like `RIGHT JOIN` and `FULL JOIN`, and complex queries.
6. **Subqueries**: Using subqueries to filter or manipulate data in the main query.
7. **Advanced String Functions / Regex / Clause**: Manipulating strings using functions and matching patterns with `REGEXP` or `LIKE`.



