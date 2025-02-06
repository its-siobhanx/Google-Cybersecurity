# Query a database using SQL:

### `SELECT`

The `SELECT` keyword specifies which columns to retrieve from a table.

*   **Selecting Specific Columns:** List the column names separated by commas after `SELECT`.
    ```sql
    SELECT column1, column2, column3
    ```

*   **Selecting All Columns:** Use `SELECT *` to retrieve all columns.
    ```sql
    SELECT *
    ```

### `FROM`

The `FROM` keyword indicates the table from which to retrieve data. It always follows the `SELECT` statement.

*   **Usage:** `FROM table_name`
*   **Example:**
    ```sql
    SELECT name, age
    FROM users;
    ```

### `ORDER BY`

The `ORDER BY` keyword sorts the result set based on the specified column.  It's placed at the end of the query.

*   **Usage:** `ORDER BY column_name`
*   **Example:**
    ```sql
    SELECT *
    FROM products
    ORDER BY price;  -- Sorts products by price in ascending order (default)
    ```

*   **Descending Order:** Use the `DESC` keyword after `ORDER BY` to sort in descending order.
    ```sql
    SELECT *
    FROM products
    ORDER BY price DESC; -- Sorts products by price from highest to lowest
    ```

### Statement Terminator

SQL statements typically end with a semicolon (`;`).  This is important, especially when executing multiple queries at once.

**Example Combining all three:**

```sql
SELECT product_name, quantity
FROM inventory
ORDER BY quantity DESC;

## Filtering Data with `WHERE` and `LIKE`

This document explains how to filter data in SQL using the `WHERE` clause and the `LIKE` operator with wildcards.

### `WHERE` Clause

The `WHERE` clause is used to filter records based on a specified condition. It follows the `FROM` clause.

*   **Basic Filtering:**  Use the equals sign (`=`) to specify the condition.
    ```sql
    SELECT *
    FROM customers
    WHERE city = 'London';  -- Selects customers from London
    ```

### `LIKE` Operator and Wildcards

The `LIKE` operator is used in a `WHERE` clause to search for patterns in a column.  It's often used with wildcards.

**Wildcards:**

Wildcards are special characters that can represent one or more other characters.  Two common wildcards are:

*   **Percentage Sign (`%`):** Represents zero or more characters.
    *   `WHERE name LIKE 'J%'`: Matches names starting with "J" (e.g., "John", "Jane").
    *   `WHERE name LIKE '%son'`: Matches names ending with "son" (e.g., "Johnson", "Wilson").
    *   `WHERE name LIKE '%a%'`: Matches names containing "a" (e.g., "Sarah", "Amanda").

*   **Underscore (`_`):** Represents exactly one character.
    *   `WHERE city LIKE 'L_ndon'`: Matches cities like "London" or "Lyndon".
    *   `WHERE city LIKE 'M__'`: Matches cities with three letters, starting with "M" (e.g., "Man").

| Pattern | Possible Results | Explanation |
|---|---|---|
| `'a%'` | `apple123`, `art`, `a` | Matches strings that *start* with "a". The `%` wildcard matches zero or more characters following the "a". |
| `'a_'` | `as`, `an`, `a7` | Matches strings that start with "a" and are *exactly two characters* long. The `_` wildcard matches any single character. |
| `'a__'` | `ant`, `add`, `a1c` | Matches strings that start with "a" and are *exactly three characters* long. Each `_` matches a single character. |
| `'%a'` | `pizza`, `Z6ra`, `a` | Matches strings that *end* with "a". The `%` wildcard matches zero or more characters preceding the "a". |
| `'_a'` | `ma`, `1a`, `Ha` | Matches strings that are *exactly two characters* long and the second character is "a". |
| `'%a%'` | `Again`, `back`, `a` | Matches strings that *contain* "a" anywhere within them. The `%` wildcards match zero or more characters before and/or after the "a". |
| `'_a_'` | `Car`, `ban`, `ea7` | Matches strings that are *exactly three characters* long and the middle character is "a". |

**Example Combining `WHERE` and `LIKE`:**

```sql
SELECT *
FROM products
WHERE product_name LIKE 'Laptop%'; -- Selects products whose names start with "Laptop"

## SQL Comparison Operators

When filtering numeric, date, and time data in SQL, comparison operators are essential for specifying conditions in your `WHERE` clause.  These operators allow you to select only the rows that meet your criteria.

| Operator | Use                               |
|---|---|
| `<` | Less than                             |
| `>` | Greater than                          |
| `=` | Equal to                              |
| `<=` | Less than or equal to                  |
| `>=` | Greater than or equal to                 |
| `<>` or `!=` | Not equal to                         |

**Example:**

```sql
-- Select customers with an age less than 30
SELECT *
FROM customers
WHERE age < 30;

## The `BETWEEN` Operator

The `BETWEEN` operator is used to filter numeric, date, and time data within a specified range (inclusive).  It simplifies range checks in your `WHERE` clause.

**Syntax:**

```sql
WHERE column_name BETWEEN value1 AND value2

# Summary of Logical Operators in SQL

Logical operators—**AND**, **OR**, and **NOT**—are essential tools for filtering queries and returning specific information, especially for security analysts.

- **AND**: Filters on two conditions, where both conditions must be true for the result to be returned.  
  Example: `WHERE country = 'USA' AND status = 'Active'`

- **OR**: Filters on two conditions, where either condition can be true for the result to be returned.  
  Example: `WHERE country = 'USA' OR status = 'Active'`

- **NOT**: Works on a single condition and negates it. It returns records where the condition is not true.  
  Example: `WHERE NOT country = 'USA'`

### Pro Tip:
You can use the `<>` or `!=` operators as an alternative to `NOT` for checking inequality.  
Example: `WHERE country <> 'USA'` is equivalent to `WHERE NOT country = 'USA'`.

### Combining Logical Operators:
You can combine logical operators in a single query. For instance, to exclude both the USA and Canada, you can use:  
```sql
WHERE NOT country = 'USA' AND NOT country = 'Canada';


## SQL joins combine data from multiple tables based on shared columns. Key types include:

* **INNER JOIN:** Returns rows only where a match exists in *both* tables.
* **LEFT JOIN:** Returns all rows from the *left* table, and matching rows from the right (NULLs if no match).
* **RIGHT JOIN:** Returns all rows from the *right* table, and matching rows from the left (NULLs if no match).
* **FULL JOIN:** Returns all rows from *both* tables (NULLs where no match).
* **CROSS JOIN:** Returns every combination of rows from both tables (Cartesian product).

Example: If you have `customers` and `orders` tables, a `LEFT JOIN` on `customer_id` would show all customers, even those without orders. An `INNER JOIN` would only show customers who *have* placed orders.
