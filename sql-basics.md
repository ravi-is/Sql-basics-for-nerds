#### 1. Creating tables 📑

```sql
CREATE TABLE BookHistory (
	Auther VARCHAR(129),
	title VARCHAR(129),
	btype VARCHAR(129),
	year CHAR(4)
);
```

#### 2. To drop table column  

```sql
ALTER TABLE tableName DROP column-Name;
ex.
ALTER TABLE BookHistory DROP Auther;
```

#### 3. How to delete Data from a MySQL table ?

// Delete Statement is used to delete data, 
```sql

DELETE FROM table_name WHERE column_name = VALUE
EX. 
DELETE FROM BookHistory WHERE title = 'JungleBook'

```

#### 4. Inserting Value into Table.

```sql
INSERT INTO table_name (Column1, Column2, Column3 ) VALUES (value1, value3, value3);
EX. 
INSERT INTO BookHistory (Author, title, btype, year) VALUES ("James Camron", "Avatar", "Adventure", 2006);
```

#### 6. Update column name.

```sql
ALTER TABLE table_name RENAME COLUMN old_col_name TO new_col_name;
EX. 
ALTER TABLE BookHistory RENAME COLUMN btype TO Book_type;
```

#### 7. Add new column in table 

```sql
ALTER TABLE table_name ADD column_name DATATYPE;
EX. 
ALTER TABLE BookHistory ADD price INT(4);
```

#### 8. The Select Command : DQL- DATA QUERY LANGUAGE Command.
Used to visualize the table content.
    

```sql
SELECT * FROM table_name;
EX.
SELECT * FROM BookHistory;

// It will show all data present inside the BookHistory table
```

We can use SELECT command to retrieve specific data from the table using WHERE clause . Like below 

```sql
SELECT * FROM table_name WHERE condition;
EX.
SELECT * FROM BookHistory WHERE Book_type = "hacking";
```

#### 1. MySQL numeric Data types.

-MySQL has numeric data types for Integer, Fixed-point, Floating-Point and bit etc.
Numeric can be singed or unsinged.
    
| 1. TINYINT | 6. FLOAT |
| --- | --- |
| 2. SMALLINT | 7. DOUBLE |
| 3. MEDIUMINT | 8. BIT |
| 4. INT |  |
| 5. BIGINT |  |
    
#### 2. String Data type.

| 1. CHAR | 5. TINYBLOB |
| --- | --- |
| 2. VARCHAR | 6. MEDIUMBLOB |
| 3. BINARY | 7. LONGBLOB |
| 4. VARBINARY |  |
#### 3. Temporal Data Types in MySQL
1. **DATE** - A date value in 'CCYY-MM-DD'
2. **TIME**- Time in 'HH:MM:SS'
3. **DATETIME** - Date-Time - 'CCVV-MM-DD  HH:MM:SS'
4. **TIMESTAMP** - 'CCVV-MM-DD' HH:MM:SS
5. **YEAR** - CCYY or YY
#### 4. Create user in MySQL
- Syntax:
    ```sql
    CREATE USE 'user-name' IDENTIFIED BY 'sample-password';
    ```

## 1. What are the "VIEWS" ?**

- n MySQL , A view consists of a set of rows that returned if particular query is executed.

- Views also known as "Virtual Table" 

- Avantages : Simplicity, security, not consume any memory, maintainability.

##### 1. How to you create & Execute VIEWS in MySQL ?
    
- we can create views using the **CREATE VIEW** Statement;
    
- A view is table in  database that has no values, The views are created by joining one or more tables.
- Syntax for creating Views
    
    ```sql
    CREATE [or REPLACE] VIEW view_name AS SELECT columns FROM TABLES [ WHERE CONDITION ]
    ```
    
##### 2. SELECT AND command.
- Syntax : 
    ```sql
    SELECT * FROM cust_tbl WHERE f_name = "shubham" AND cust_id > 3;
    ```

##### 3. **Truncate :** It removes complete data without removing it’s structure. It is a DDL Command
  - Syntax : 
    ```sql
    TRUNCATE TABLE table_name;
    EX.
    TRUNCATE TABLE BookHistory;
    ```

##### 4. Update Command in MySQL.
- Syntax : 
    ```sql
    UPDATE 'table_name' SET 'column_name' = 'new_value' [WHERE CONDITION];
    EX.
    UPDATE BookHistory SET 'Auther' = 'James Bond' WHERE Auther = "JB"; 
    ```

##### 5. BETWEEN : Get values between particular condition.
- 
    ```sql
    SELECT * FROM cus_tbl WHERE ID = 8 AND 11;
    ```

##### 6. Find version of installed MySQL.
    
   - Type Following Command. 
```sql
SHOW VARIABLES LIKE "%version%";
```

##### 7. ENUM and SET.
    
- ENUM data type is used in the MySQL datatypes to select any one value from the predefined list. Example : 
 
    ```sql
    CREATE DATABASE newEnum;
    CREATE TABLE Clients (
    	id INT AUTO_INCREMENT PRIMARY KEY,
    	name VARCHAR(50), 
    	memberShip ENUM('silver', 'gold', 'Diamond'),
    	interested SET('Movie', 'Music', 'concert');
    )
    ```

> Cannot set multiple in ENUM but we can set multiple values in SET. 

### 4. What is different between Primary key and Foreign Key ?
    
- The database table uses Primary key to identify each row uniquely, It is necessary to declare a primary key on those tables that require tp create a relationship among them. - One or More field of table can be declared as primary key
    
- When primary key of any table is used in another table as the primary key or anther field for making a database relation then it is called Foreign Key.
    
- **Primary Key :**  Identified a record whereas foreign key refers the primary key of another tables. Primary key never accepts not null value. But Foreign key accepts null value.

#### 4. Filter duplicate values.
- A **DISTINCT** keyword is used to identify the duplicate data from table while retrieving the records. EX.
    
    ```sql
    SELECT * FROM items
    ```

- Output: 

    | id | name | type | brand | man_id |
    | --- | --- | --- | --- | --- |
    | 1 | samsung | mobile | samsung | 1 |
    | 2 | iPhone | mobile | apple | 2 |
    | 3 | Sony  | TV | Sony  | 3 |
- Using **DISTINCT** Keyword

    ```sql
    SELECT DISTINCT type FROM items;
    ```

- output:

    | type |
    | --- |
    | mobile |
    | TV |
### 1. Which statement is used in a select query statement for partial matching ?

- REGEXP and LIKE statement can be used in a select query for partial matching.

- **REGEXP** : used to Search records bases on the pattern matching
- **LIKE** : Is used to search any record by  matching string at beginning or end or middle of particular filed value.

##### Ex. 1. REGEXP (Search records start with ‘S’);
- Syntax: 
    ```sql
    SELECT * FROM BookHistory WHERE name REGEXP "^s";
    ```

##### Ex. 2. LIKE 
- Syntax: 
    ```sql
    SELECT * FROM BookHistory WHERE name LIKE "A%";
    ```
----------
#### 1. Rename Table
- Syntax: 
    ```sql
    RENAME TABLE table_name TO new_table_name;
    EX.
    RENAME TABLE items TO Products;
    ```

#### 2. Retrieve a portion of any Column value by using select Query ?

-   **SUBSTR()** Function is used to retrieve the portion of any column. EX

> OR we can we ‘**SUBSTRING**’ keyword


```sql
    SELECT SUBSTR(name, 1, 5) FROM Products;
```

##### Output:
 -

    | Samsu |
    | --- |
    | iPhon |
    | Sony |
####  3. Calculate Sum of any Column of table ?

- *SUM() Function is used to calculate the sum of any column. EX.**

    ```sql
    SUM(DISTINCT expression)
    EX.
    SELECT SUM(Price) as total FROM Products;
    ```

- Output:

    | total |
    | --- |
    | 2109.00 |

# ———— **The Practical Approach ————**

##### 1. Fetch FIRST_NAME from worker table. 
- Syntax
    ```sql
    SELECT First_name as worker_name from Woker;
    
    //will return all first_name 's
    ```

##### 1. Fetch FIRST_NAME as Upper Case
- Syntx
    ```sql
    SELECT upper(First_name) FROM Worker
    
    // Will return all name in upper case
    ```

##### 2. Fetch unique Values from Department
-
    ```sql
    SELECT DISTINCT department FROM Worker;
    ```

- Output : 

    | department  |
    | --- |
    | HR |
    | ADMIN |
    | ACCOUNT |
##### 3. Find position of alphabets (”a”) in first_name column ‘Amitabh’ from worker.
- Syntax
```sql
SELECT INSTR(first_name, BINARY'a') FROM worker WHERE first_name = "Amitabh";
```
- Output :

    | INSTR( first_name, BINARY ’a’ ) |
    | --- |
    | 5 |
##### 4. Remove white Spaces 
 1. **RTRIM** : To remove white spaces from right side. EX
    
    ```sql
    SELECT RTRIM(first_name) FROM Worker;
    ```
    
    . **LTRIM** : To remove white spaces from left side. EX
    
    ```sql
    SELECT LTRIM(Department) FROM Worker;
    ```
    
##### 5. Query to print **`first_name`** and **`salary`** from worker table into a single column NAME_SALARY

- We use **`CONCAT()`** keyword to get combined result from two or more tables. EX

```sql
SELECT CONCAT(first_name, "=" , Salary) AS 'NAME_SALARY' FROM Worker;
```

##### 6. Query to print all worker details from worker table order by First_Name Ascending.
- Syntax
```sql
SELECT * FROM Worker ORDER BY First_Name ASC;
```

##### 7. Print details for worker with First_name as ‘Shubham’ and ‘NICK’ from worker table.
- Syntx
```sql
SELECT * FROM Worker WHERE First_Name In('Shubham', 'NICK');
```

##### 8. Query to fetch the count of employee working in the department ‘admin’.

- The count function return cunt of given queries : EX.
- Syntax :

```sql
SELECT COUNT(*) FROM Worker WHERE Department = 'Admin';
```

- Output : 

    | count(4) |
    | --- |
    | 4 |

# AGGREGATE FUNCTIONS : -

SQL Aggregate functions is used to perform calculations on multiple row of a single column of a table it return single value.

1. COUNT()
2. SUM()
3. AVG()
4. MAX()
5. MIN()

---

1. **COUNT()** 

→ Count the number of rows in  database; It uses function COUNT(*) that return all rows

```sql
SELECT COUNT(*) FROM Worker WHERE Department = 'Admin';
```

1. SUM()

→ SUM() Function is used to calculate the sum of all selected columns. it only work on numeric values.  Syntax: sum();

```sql
SELECT SUM(salary) FROM Worker;
or 
SELECT 
```

1. AVG()

→ Used to calculate average value of the numeric type. AVG function return the average of all non-null values. Syntax: AVG();

```sql
SELECT Avg(salary) FROM Workder;
```

1. MAX(): 

→ Max function used to find the maximum value of a certain column . This function determines the largest value of all selected values of column. Syntax: MAX();

```sql
SELECT MAX(SALARY) FROM Worker;
```

1. MIN();

→ MIN used to find minimum value of a certain column. this function determines the smallest value of all selected of a column.

```sql
SELECT MIN(SALARY) FROM Worker 
```

---

## SQL Command :

→ SQL commands are the instructions used to communicate with the database, also use to perform specific task, functions & queries of data.

→ **5 Types of SQL Commands**

1. DDL → DATA DEFINATION LANGUAGE

| CREATE | DROP | ALTER | TRUNCATE |
| --- | --- | --- | --- |
1. DML → DATA MANIPULATION LANGUAGE

| INSERT | UPDATE | DELETE |
| --- | --- | --- |
1. DCL → DATA CONTROL LANGUAGE

| GRANT | REVOKE |
| --- | --- |
1. TQL → TRANSACTION CONTROLL LANGUAGE

| COMMIT | ROLLBACK | SAVEPOINT |
| --- | --- | --- |
1. DQL → DATA QUERY LANGUAGE

| SELECT |
| --- |

- > Update Multiple values at a time
