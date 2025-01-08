# <mark style="background: #69E772;">02 Advanced Database Queries:</mark>

### <mark style="background: #69E772;">Joins:</mark>

<mark style="background: #69E772;">When do I use:</mark>  
- ``JOIN ... USING``  
- ``JOIN... ON``  
- ``LEFT JOIN``  
- ``RIGHT JOIN``  
- ``FULL OUTER JOIN``

<mark style="background: #69E772;">Observe the queries on the next slide, assuming you will solve them with a join, note:</mark>
- The most appropriate type of join.  
- The efficiency of your query.  
- Upload and run the 'Builder Join problems' SQL file in your Builder schema.

![](https://i.imgur.com/pLUASLs.png)

### <mark style="background: #69E772;">Aggregation:</mark>

```SQL
SELECT [aggregate function], [aggregating attribute set]  
FROM [set of tables]  
[GROUP BY [aggregating attribute set]]  
[WHERE [condition calculated on each row]]  
[HAVING [condition calculated on aggregate result]];
```

Used to give summary information.  

Can be sub-grouped.  

Can be filtered on the aggregate result.  

Upload and run the 'Builder Aggregate problems' SQL file in your Builder schema.

![](https://i.imgur.com/ssqWd4N.png)

### <mark style="background: #69E772;">Windowing:</mark>

Window functions allow us to look at each row, with summary information alongside.  

We will use a different example to learn.  
- Upload and run the SQL file 'WinFunCreate.SQL' with sample tables.  
- Upload and individually run the queries in '

### <mark style="background: #69E772;">Create the tables:</mark>

```SQL
Create TABLE product_groups (  
	group_id serial PRIMARY KEY,  
	group_name VARCHAR (255) NOT NULL  
);  

Create TABLE products (  
	product_id serial PRIMARY KEY,  
	product_name VARCHAR (255) NOT NULL,  
	price DECIMAL (11, 2),  
	group_id INT NOT NULL,  
	FOREIGN KEY (group_id) REFERENCES product_groups (group_id)
);
```

### <mark style="background: #69E772;">Add rows:</mark>

```SQL
INSERT INTO product_groups (group_name)  
VALUES  
	('Smartphone'),  
	('Laptop'),  
	('Tablet');
```

```SQL
INSERT INTO products (product_name, group_id,price)  
VALUES  
	('Microsoft Lumia', 1, 200),  
	('HTC One', 1, 400),  
	('Nexus', 1, 500),  
	('iPhone', 1, 900),  
	('HP Elite', 2, 1200),  
	('Lenovo Thinkpad', 2, 700),  
	('Sony VAIO', 2, 700),  
	('Dell Vostro', 2, 800),  
	('iPad', 3, 700),  
	('Kindle Fire', 3, 150),  
	('Samsung Galaxy Tab', 3, 200);
```

### <mark style="background: #69E772;">Run the queries - individual rows:</mark>

```SQL
select * from products  
join product_groups using (group_id);
```

![](https://i.imgur.com/cSDj0GC.png)


### <mark style="background: #69E772;">Run an aggregate</mark>

```SQL
-- get averages for each group  
SELECT group_name, AVG (price)  
FROM products  
JOIN product_groups USING (group_id)  
GROUP BY group_name;
```

### <mark style="background: #69E772;">Introducing the windows concept:</mark>

Windows functions allow you to combine the two:

```SQLite
SELECT product_name, price, group_name, AVG (price) OVER (  
	PARTITION BY group_name)  
FROM products  
JOIN product_groups 
USING (group_id);
```

![](https://i.imgur.com/jJ5wXcV.png)

This gives a row for every product, with its group name and the aggregate average over the group.  

The <mark style="background: #69E772;">partition</mark> by clause tells the SQL engine how to sub-group the rows.

### <mark style="background: #69E772;">More advanced functions:</mark>

The ``ROW_NUMBER()``, ``RANK()``, and ``DENSE_RANK()`` functions assign an integer to each row based on its order in its result set.  

``FIRST_VALUE`` and ``LAST_VALUE`` pick out first and last items in a partition  

``LAG`` and ``LEAD`` allow each row to be compared with the previous / next row.

<mark style="background: #69E772;">ROW_NUMBER():</mark>

The ``ROW_NUMBER()`` function assigns a sequential number to each row in each partition.  

```SQL
SELECT product_name, group_name, price, ROW_NUMBER () OVER (  
	PARTITION BY group_name  
	ORDER BY price)  
FROM products  
JOIN product_groups USING (group_id);
``` 

Run this query to see the result.

<mark style="background: #69E772;">RANK():</mark>

The ``RANK()`` function assigns ranking within an ordered partition.  

If rows have the same values, the ``RANK()`` function assigns the same rank, with the next ranking(s) skipped.  

```SQL
SELECT product_name, group_name, price, RANK () 
OVER (  
	PARTITION BY group_name  
	ORDER BY price)  
FROM products  
JOIN product_groups USING (group_id);
```

Run this query to see the result.

<mark style="background: #69E772;">DENSE_RANK():</mark>

The ``DENSE_RANK()`` function assigns a rank to each row within an ordered partition, but the ranks have no gap. i.e. the same ranks are assigned to multiple rows and no ranks are skipped.  

```SQL
SELECT product_name, group_name, price, DENSE_RANK () OVER (  
PARTITION BY group_name  
ORDER BY price)  
FROM products  
JOIN product_groups USING (group_id);
```

Run this query to see the result. Do you see how it differs from the previous one?

<mark style="background: #69E772;">First_value and Last_value:</mark>

The ``FIRST_VALUE()`` function returns a value evaluated against the first row within its partition.  

```SQL
SELECT product_name, group_name, price, FIRST_VALUE  
(price) OVER (  
	PARTITION BY group_name  
	ORDER BY price  
) AS lowest_price_per_group  
FROM products  
JOIN product_groups USING (group_id);
```

``LAST_VALUE()`` returns a value evaluated against the last row in partition.

```SQL
SELECT product_name, group_name, price, LAST_VALUE (price) OVER (  
	PARTITION BY group_name  
	ORDER BY price RANGE BETWEEN UNBOUNDED PRECEDING  
	AND UNBOUNDED FOLLOWING) AS highest_price_per_group  
FROM products  
INNER JOIN product_groups USING (group_id);
```

The default frame clause is ``RANGE BETWEEN UNBOUNDED PRECEDING`` and ``CURRENT ROW`` unbounded following includes all rows.  

This one is a little unusual – experiment to see what happens if you take out the extra clause.

### <mark style="background: #69E772;">LAG and LEAD – Compare adjacent rows in a group.</mark>

The ``LAG()`` function has the ability to access data from the previous row, while the ``LEAD()`` function can access data from the next row.  

Both <mark style="background: #69E772;">LAG()</mark> and <mark style="background: #69E772;">LEAD()</mark> functions have the same syntax as follows:  
- ``LAG (expression [,offset] [,default]) over_clause;``  
- ``LEAD (expression [,offset] [,default]) over_clause;``  

<mark style="background: #69E772;">In this syntax:</mark>  
- <mark style="background: #69E772;">expression</mark> – a column or expression to compute the returned value.  
- <mark style="background: #69E772;">offset</mark> – the number of rows preceding ( LAG)/ following ( LEAD) the current row. It defaults to 1.  
- <mark style="background: #69E772;">default</mark> – the default returned value if the offset goes beyond the scope of  the window. The default is ``NULL`` if you skip it.

The following statement uses the <mark style="background: #69E772;">LAG()</mark> function to return the prices from the previous row and calculates the difference between the price of the current row and the previous row.  

```SQL
SELECT product_name, group_name, price,  
lag(price, 1) OVER (  
PARTITION BY group_name  
ORDER BY price) "Previous Price",  
price - lag(price, 1) OVER (  
PARTITION BY group_name  
ORDER BY price) "Current - Previous Price"  
FROM products  
JOIN product_groups USING (group_id);
```

The following statement uses the <mark style="background: #69E772;">LEAD()</mark> function to return the prices from the next row and calculates the difference between the price of the current row and the next row.

```SQL
SELECT product_name, group_name, price,  
LEAD (price, 1) OVER ( PARTITION BY group_name  
ORDER BY price  
) AS next_price,  
price - LEAD (price, 1) OVER ( PARTITION BY group_name  
ORDER BY price  
) "Current - Next Price"  
FROM products  
JOIN product_groups USING (group_id);
```

### <mark style="background: #69E772;">Builder schema window functions practice:</mark>

1. Select each supplier name and the ``stock_code`` and ``stock_description`` of each stock item that supplier supplies.  
2. Select each supplier name and average ``unit_price`` of stock that supplier supplies.  
3. Select each supplier name, the ``stock_code``, ``stock_description``, ``unit_price`` and average ``unit_price`` for that supplier for each stock item that supplier supplies.  
4. Select each supplier name, the ``stock_code``, ``stock_description``, ``unit_price`` and rank of that price for that supplier for each stock item that supplier supplies.  
5. As above, but ``dense_rank()``  
6. Use ``lag()`` and ``lead()`` to compare item prices from a supplier.  
7. Use ``first_value()`` and ``last_value()`` to find highest and lowest ``unit_price`` per supplier.

### <mark style="background: #69E772;">Sets:</mark>

UNION, INTERSECT, EXCEPT  

Combining to provide a pattern for solving problems.  

Download and run "Builder SET problems.SQL"  

Fill in the gaps.

![](https://i.imgur.com/qF5u5bJ.png)


### <mark style="background: #69E772;">BUILDER SET QUERIES:</mark>

![](https://i.imgur.com/fXWgW7U.png)

### <mark style="background: #69E772;">Outline:</mark>

Using ‘in’ and ‘not in’  

Using reflexive queries, multiple nesting and other uses  

Use of ``EXISTS`` and ``NOT EXISTS``  

Correlated sub-queries  

Join terminology  

Relational Divide  

Problem abstraction and using a template  

Using views to simplify queries.

### <mark style="background: #69E772;">Staff and customer orders:</mark>

![](https://i.imgur.com/EFEyUWY.png)


### <mark style="background: #69E772;">Expr in (sub-select):</mark>

Return the names of customers who have not collected their orders.

```SQL 
select customer_name  
from b2_customer  
Where Customer_id in  
	(select customer_id  
	from b2_corder  
	where staffissued is null);
```

![](https://i.imgur.com/WoIwDtl.png)

Do we have suppliers in our supplier table who don’t supply any stock?

![](https://i.imgur.com/OlAxuNT.png)

### <mark style="background: #69E772;">Solution:</mark>

```SQL
SELECT supplier_name  
FROM b2_supplier  
WHERE supplier_id NOT IN  
(SELECT supplier_id from b2_STOCK);
```

Run this code from the ExtraExamples.sql file.

### <mark style="background: #69E772;">NULL "problem":</mark>

```SQL
Select staff_no, reports_to  
from b2_staff;
```

![](https://i.imgur.com/hjWoBRC.png)

Get the names and staff numbers of staff who have nobody reporting to them.  

```SQL
select staff_no 
from b2_staff 
where staff_no 
not in (select reports_to from b2_staff);
```  

This query returns an empty set, because ``NOT IN`` cannot evaluate a column that has NULLs.

### <mark style="background: #69E772;">Using aggregates in sub-queries:</mark>

```SQL
SELECT stock_code,stock_description, unit_price 
FROM b2_stock  
WHERE unit_price > (
	SELECT AVG(unit_price) 
	FROM b2_stock);
```

![](https://i.imgur.com/Pqy6U3W.png)

This query returns the stock code, description and price of all stock items that cost more than the average unit price of any stock item.

### <mark style="background: #69E772;">EXISTS condition:</mark>

This returns a Boolean value of true or false.  

The result is true if the sub-query returns a non-empty set of values i.e. it’s true that a row exists.  

The sub-query is generally correlated to the outer query

The ``EXISTS`` condition is met if the sub-query returns at least one row.  

The syntax for the ``EXISTS`` condition is:  
```plSQL
SELECT columns  
FROM tables  
WHERE EXISTS ( subquery );
``` 

The ``EXISTS`` condition can be used in any valid SQL statement - select, insert, update, or delete.

e.g.  
```SQL
select * from b2_stock where exists (select now());  

-- This is the same as  

Select * from b2_stock;  
because “select now()” returns the current date, so a value exists.```

because “``select now()``” returns the current date, so a value exists.

The following query will return no values:  
```SQL
select * from b2_stock where exists (  
select now()  
where 1 = 2);
```  

Because  
```SQL
select now() where 1 = 2
```  

returns no values.

### <mark style="background: #69E772;">CORRELATED SUB-QUERIES:</mark>

This is where the inner select statement refers to data defined in the outer select statement.

<mark style="background: #69E772;">Example 1 - EXISTS:</mark>
This select statement will return all records from the suppliers table where there is at least one record in the supplier order table with the same ``supplier_id``.  

It is a <mark style="background: #69E772;">correlated sub-query</mark>.

```SQL
SELECT *  
FROM b2_supplier s  
WHERE EXISTS  
	(select *  
	from b2_sorder o  
	where s.supplier_id = o.supplier_id);
```

![](https://i.imgur.com/8cGpCOy.png)

<mark style="background: #69E772;">Example #2 - NOT EXISTS:</mark>

The ``EXISTS`` condition can also be combined with the NOT operator.  

For example,  
```SQL
SELECT *  
FROM supplier s  
WHERE not exists (select * from sorder o  
where s.supplier_id = o.supplier_id);
```

<mark style="background: #69E772;">Example #3 - DELETE Statement:</mark> 

The following is an example of a delete statement that utilizes the ``EXISTS`` condition:

```SQL
DELETE FROM supplier s  
WHERE not EXISTS  
	(select *  
	from sorder o  
	where s.supplier_id = o.supplier_id);
```

<mark style="background: #69E772;">Correlated sub-query:</mark>  

```SQL
SELECT stock_code, stock_description, unit_price, supplier_id  
FROM b2_stock st  
WHERE unit_price > (  
SELECT AVG(unit_price) FROM b2_stock WHERE  
supplier_id = st.supplier_id);
```

This returns the stock code, description, price and supplier id of all stock items that cost more than the average stock item supplied by that supplier.

### <mark style="background: #69E772;">RELATIONAL DIVIDE:</mark>

Shows rows in one table that are related to all rows in another ``many:many`` table. e.g. Which students have passed ALL modules?

### <mark style="background: #69E772;">New Model - Student - subject:</mark>

![](https://i.imgur.com/Lp2Eui7.png)

<mark style="background: #69E772;">Table Contents:</mark>
![](https://i.imgur.com/yG2x8If.png)

<mark style="background: #69E772;">Reword the query:</mark> Return names of students where there does not exist a subject they haven't achieved.  

This double negative is part of DeMorgan's theorem.

<mark style="background: #69E772;">Who achieved everything?</mark>
![](https://i.imgur.com/WSgtVTJ.png)

```SQL
select st_name from student a  
where not exists (  
	select * from subject b  
	where not exists (  
		select * from acheivement x  
		where  
		x.st_id = a.st_id and  
		x.sb_id = b.sb_id));
```

### <mark style="background: #69E772;">Abstraction:</mark>

Return a list of occurrences of A related to ONLY n occurrences of B.  

Return a list of occurrences of A that are related to ALL occurrences of B  

Return a list of A relate to ALL B where...  

Return a list of A that have no related occurrences in B.  

Return details of any A that is related to an occurrence in B  

Return a list of occurrences of A that are related to both occurrences B<sub>i</sub> and B<sub>j</sub> where B<sub>i</sub> , Bj<sub>j</sub> B∈  

Return a list of A that are related to Bi but not B<sub>j</sub> where B<sub>i</sub> , B<sub>j</sub> B∈  

Return a list of A that are related to either B<sub>i</sub> or B<sub>j</sub> but not both.

![](https://i.imgur.com/Dte2cWL.png)

### <mark style="background: #69E772;">Helpful hints:</mark>

If you are basing your answer on SET theory, it can be helpful to create views of the sets.  

E.g. List the names of customers who have bought blocks but not bought bricks. Start by creating a view:  
```SQL
create view boughtblock as  
select customer_name from b2_customer  
join b2_corder using (customer_id)  
join b2_corderline using (corderno)  
join b2_stock using (stock_code)  
where lower (stock_description) like  
'%block%'; 
```

What’s next?

![](https://i.imgur.com/gVa3Qsm.png)

<mark style="background: #69E772;">Who bought what?</mark>
To find a list of the customer names and what they bought, I would need:

![](https://i.imgur.com/J2tJWdZ.png)

<mark style="background: #69E772;">How did we do that?</mark>

By tracing a path through the relationships, we could see:  
- Which attributes we wanted to show  
- What tables they were in  
- Which attributes we needed to join the tables  
- Where were the attributes that we were testing in the conditions?

### <mark style="background: #69E772;">Using Views:</mark>

<mark style="background: #69E772;">Generalising the query:</mark> 
- Which customers bought the item with ``stock_description`` 'Phillips screwdriver'?  
- What did customer named ‘John Flaherty’ buy?  

To do that, I can store my query in a view, and query the view.

<mark style="background: #69E772;">Create the view:</mark>
```SQL
Create view custbought as  
Select customer_name, stock_description  
From b2_customer  
Join b2_corder using (customer_id)  
Join b2_corderline using (corderno)  
Join b2_stock using (stock_code);
```

<mark style="background: #69E772;">Query the view:</mark>
```SQL
Select customer_name from custbought where   stock_description = 'Phillips screwdriver';
```

<mark style="background: #69E772;">Build the queries using views:</mark>

![](https://i.imgur.com/tgM2b9o.png)

![](https://i.imgur.com/Y7DYEe6.png)

![](https://i.imgur.com/jYlfK73.png)

### <mark style="background: #69E772;">Using views:</mark>

I’d like to know :  
- Students who passed Maths but not Geography? ``(A – B)``  
- Students who passed Geography but not Maths? ``(B – A)``  
- Students who passed both Geography and Maths? ``(A ∩ B)``  
- Students who passed either Geography or Maths? ``(A U B)``  
- Students who passed either Geography or Maths, but not both? ``A xor B (A U B) - (A ∩ B) `` 
- Students who only passed Maths? ``(A - ¬A)``  
- Use the ``SampleDivide.sql`` file to experiment.  
- Add and delete rows from the achievement table to see what difference it makes.

### <mark style="background: #69E772;">Transferring our skills to the builder schema:</mark>

What about :  
- Customers who bought a workbench but no timber?  ``(A – B)``  
- Customers who bought timber but no workbench? ``(B – A)``  
- Customers who bought both timber and a workbench? ``(A ∩ B)``  
- Customers who bought either timber or a workbench? ``(A U B)``  
- Customers who bought either timber or a workbench, but not both? ``A xor B (A U B) - (A ∩ B)``  
- Customers who only bought a workbench?``(A - ¬A``

### <mark style="background: #69E772;">What is the shape of our tables?</mark>

ERDs start to get complex when there are many:many relationships.  
- Students eating types of crisp  
- Students sitting modules  
- Customers buying stock  

We can use SET theory to form a template for  common queries.

![](https://i.imgur.com/KcZdxHE.png)

<mark style="background: #69E772;">A trivial example:</mark>
![](https://i.imgur.com/dJM8nMi.png)

<mark style="background: #69E772;">Who ate every type of crisp?</mark>
```SQL
SELECT CN_NAME FROM CR_CONSUMER A  
WHERE NOT EXISTS (  
	SELECT * FROM CR_CRISP_TYPE B 
	WHERE NOT EXISTS (  
		SELECT * FROM CR_HAS_EateN X  
		WHERE A.CONSUMERID =  X.CONSUMERID AND B.CRISPKEY = X.CRISPKEY  
	)  
);
```

![](https://i.imgur.com/Z1PXSoQ.png)

<mark style="background: #69E772;">Helping the divide:</mark>
If I want a list of non-key values in A for rows that are  associated with all occurrences of B:

![](https://i.imgur.com/Rp4hHc5.png)

![](https://i.imgur.com/JCqPou0.png)

<mark style="background: #69E772;">Slightly more obscure:</mark>

Who bought all the stock items supplied by Buckleys?  

Where are A, X and B?  
- A must be a table or view with the identifying key to customer name, joined to X.  
- B must be a table or view with the identifying key to the stock items supplied by Buckleys, joined to X.  
- X must be a weak entity, with a many:1 link to A  and to B.

![](https://i.imgur.com/AR93bCU.png)

<mark style="background: #69E772;">The views:</mark>
![](https://i.imgur.com/yFLnT7L.png)

![](https://i.imgur.com/jRGaGAN.png)

<mark style="background: #69E772;">The final query:</mark>
![](https://i.imgur.com/36nQ4lu.png)

![](https://i.imgur.com/CtfBwhN.png)

# <mark style="background: #69E772;">03 Functions and Triggers:</mark>

### <mark style="background: #69E772;">Outline:</mark>

<mark style="background: #69E772;">Where is the database?</mark>
- Where do the programs work?  
- Parameters  
- Declaring variables  
- Verbose syntax IF...THEN...ELSE...END IF;

### <mark style="background: #69E772;">Where is the database?</mark>

The database is at the base of your application  

When you look at a software schematic, the data is almost always at the opposite end to the user.

### <mark style="background: #69E772;">Application layers:</mark>

![](https://i.imgur.com/EKm9CwY.png)

<mark style="background: #69E772;">The presentation layer:</mark> The user sees or interacts with this layer.  

<mark style="background: #69E772;">The business logic layer:</mark> Enforces the business rules  

<mark style="background: #69E772;">The data access layer</mark> enforces rules regarding the storage and access of information.

### <mark style="background: #69E772;">Databases in an application:</mark>

![](https://i.imgur.com/8jcCq0d.png)

### <mark style="background: #69E772;">Over the web:</mark>

![](https://i.imgur.com/tqIK1gW.png)

### <mark style="background: #69E772;">Apps use multiple databases:</mark>

![](https://i.imgur.com/13FTMUP.png)

# <mark style="background: #69E772;">Functions in postgreSQL</mark>

### <mark style="background: #69E772;">Function Skeleton:</mark>

```plSQL
CREATE OR REPLACE FUNCTION <function name> (  
	<parameter-names parameter data types>)  
	RETURNS <return data type>  
	LANGUAGE plpgsql  
AS $function$  
DECLARE  
	< /* local variable names and datatypes */ >;  
BEGIN  
	< /*function logic, including return statement*/ > 
EXCEPTION  
	< /*exeption logic*/ >  
END;  
	$function$;
```

### <mark style="background: #69E772;">Creating and running the function:</mark>

<mark style="background: #69E772;">To create the function, the function code is run in a SQL code window:</mark>
- See next slides for function code  
- This compiles the function and saves it in the schema.  

The function can be run in a SQL code window as  ``SELECT * from <function call with parameters>``

![](https://i.imgur.com/uNXaAbX.png)

### <mark style="background: #69E772;">Parts of a function:</mark>

Name follows naming rules in PostgreSQL.  

Parameters are declared with a name and data type.  

The data type can be a standard data type, or can be inherited from a table column, suffixed with ``'%type'``. This promotes data independence, E.g. ``customer_name b2_customer.customer_name%type;``  
By default, parameters are ‘in out’ or pass by reference  – i.e if you change their values in the function, they retain the changed value in the calling environment.  

<mark style="background: #69E772;">Function logic:</mark> ALWAYS contains at least one SQL statement!

### <mark style="background: #69E772;">Declarations in addcustomer function:</mark>

We want to take in a customer’s name and optional address and add a row to the customer table. We want to return the new customer id.

```plSQL
CREATE OR REPLACE FUNCTION addcustomer(  
p_cname b2_customer.customer_name%type,  
p_caddr b2_customer.customer_address DEFAULT NULL)  
	RETURNS integer  
	LANGUAGE plpgsql  
AS $function$  
DECLARE  
	v_custid INTEGER;
```

### <mark style="background: #69E772;">Local variables and fixed size memory:</mark> 

Functions can only hold data in the declared section.  

<mark style="background: #69E772;">This means:</mark>
- When I SELECT, I must say where the data is going!!!!  
- All data that is SELECTed must be selected INTO a declared variable or area.  

Also, when inserting a row, we can return any part of the new row:  
```SQL
insert into b2_customer (customer_name, customer_address)  
values (p_cname, p_contactno) returning customer_id into v_custid;
``` 

The RETURNING keyword in PostgreSQL gives an opportunity to return from the insert or update statement the values of any columns after the insert or update was run.

### <mark style="background: #69E772;">Add a customer:</mark>

```plSQL
create or replace FUNCTION ADDCUSTOMER(  
	p_cname b2_customer.customer_name%type,  
	p_caddr b2_customer.customer_address%type default NULL)  
	returns INTEGER AS  
$$  
DECLARE  
	v_custid INTEGER;  
BEGIN  
	insert into b2_customer (customer_name, customer_address)  
	values (p_cname, p_caddr) returning customer_id into v_custid;  
	RETURN v_custid;  
END;  
$$ LANGUAGE plpgsql
```

Looking more closely, you can call this function with one parameter.

### <mark style="background: #69E772;">Run the function in SQL:</mark>

```SQL
select addcustomer('Johnny  
Comelately','Hostel'); 
```

This returns the ``customer_id`` of the row that has just been added.

SQL code for ``addcustomer`` is in Brightspace under ``addcustomer.sql``  

It should be run in your BUILDER schema.

### <mark style="background: #69E772;">New model - Student - subject:</mark>

![](https://i.imgur.com/np5YJpu.png)

<mark style="background: #69E772;">Table contents:</mark>
![](https://i.imgur.com/W3E8dvg.png)

<mark style="background: #69E772;">Student passes module:</mark>

You now have 3 tables in your schema, with some data in them (shown on the next two slides).  

Write a function ``AddStudent`` that takes in a student name and returns the serial number that has been allocated as key to that row in the student table.  

A lot of the code is in ``PartAddStudent.sql``

### <mark style="background: #69E772;">Postgres Procedures:</mark>

These are similar to functions, but there is no RETURN.  

Procedures are initiated using CALL.  

<mark style="background: #69E772;">Procedures are used to:</mark>
- Carry out a process.
- Often used to perform maintenance or upgrade tasks.
- Often have iteration.

<mark style="background: #69E772;">Resources on brightspace:</mark>
- Create_tournament.sql  
- Make_matches procedure.sql

### <mark style="background: #69E772;">Example:</mark>

A club runs tournaments for its players. When a new tournament starts, the club must set up matches.  

Let's assume a new knockout tournament is taking place, with 64 players.  
- We want 32 first round matches.  
- 16 second round, 8 third round, 4 fourth round, 2 fifth round and a final (6th round).

![](https://i.imgur.com/uZH0Pah.png)

<mark style="background: #69E772;">We don't know:</mark>  
- what date they'll be  
- Who the players will be  
- What the scores will be  

Write a procedure to take in  
- the tournament key (Tkey)  
- The round number  
- The number of matches  

Add all the matches for that round.

### <mark style="background: #69E772;">Create the Procedure:</mark>

```plSQL
create or replace procedure make_matches(  
p_tkey tournament.tkey%type,  
p_round match.tround%type,  
nomatches integer)  
LANGUAGE plpgsql  
as $$  
	begin  
	for i in 1..nomatches loop  
	insert into match (tkey, tround, matchno)  
	values (p_tkey, p_round, i);  
	END loop;  
	end;  
$$;
```

Procedure, rather than function

Iteration can be done using a loop.

No return statement.

### <mark style="background: #69E772;">Call the procdure:</mark>

```SQL
call make_matches ('Ashe',1,16);  
call make_matches ('Ashe',2,8);  
call make_matches ('Ashe',3,4);  
call make_matches ('Ashe',4,2);  
call make_matches ('Ashe',5,1); 

select * from match;
```

### <mark style="background: #69E772;">Trapping exceptions:</mark>

Raise exceptions in the code, and return the database's own error messages.  

Before the END, insert the following: 

```SQL
exception 
when others then  
RAISE info 'Error Description:%',sqlerrm;  
raise info 'Error Code:%', SQLSTATE;
```

### <mark style="background: #69E772;">Back to theory:</mark>

<mark style="background: #69E772;">The relational database offers the following protection:</mark>
- Primary keys prevent adding duplicates  
- Check and references constraints prevent invalid data from being entered.  

<mark style="background: #69E772;">Other requirements:</mark>
- Further checks on ``INSERT``, ``UPDATE`` and ``DELETE``.  
- Privacy from unauthorised users  
- Atomicity to prevent concurrency issues

# <mark style="background: #69E772;">Triggers:</mark>

### <mark style="background: #69E772;">What is a trigger?</mark>

An action that is taken when some event occurs.  

<mark style="background: #69E772;">The events we will address are Data Manipulation events:</mark>
- ``INSERT``, 
- ``UPDATE`` and 
- ``DELETE`` operations.

### <mark style="background: #69E772;">Piggyback:</mark>

The operation works as normal on the table in the database, but it now has a trigger, piggybacking on it.  

The ``TRIGGER`` can log events or constrain them.  

While the ``INSERT``, ``UPDATE`` or ``DELETE`` manipulate the table as intended.

![](https://i.imgur.com/iiGdqwR.png)

### <mark style="background: #69E772;">Reasons for triggers:</mark>

<mark style="background: #69E772;">Triggers can be used for:</mark>
- Logging user actions  (Who updated a staff member’s salary? When?)  
- Checking constraints (I don’t want to sell stock I do not have. I don’t want a student to register for modules if they are already registered for 60 ECTS  credits worth. )

Other reasons: Automatically generate derived column values

### <mark style="background: #69E772;">Logging actions:</mark>

<mark style="background: #69E772;">These triggers apply to:</mark>
- ``INSERT``  
- ``UPDATE``
- ``DELETE``  

To log these commands we need a log table.

### <mark style="background: #69E772;">To log actions:</mark>

<mark style="background: #69E772;">When logging user actions, in general, we need to know:</mark>
- What table is being changed.  
- What the change is (``INSERT``, ``UPDATE`` or ``DELETE``).  
- Who has made the change.  
- When was the change made.  

This information tells us a little about the transaction. 

For future use we add ``Keyval``, ``oldprice``, ``newprice``.

### <mark style="background: #69E772;">Logging actions:</mark>

<mark style="background: #69E772;">To log these actions, we must</mark>
1. Set up a table into which the ``TRIGGER`` can insert rows.  
2. Attach a ``TRIGGER`` to an ``OPERATION`` on a ``TABLE``.  

<mark style="background: #69E772;">i.e. we attach a trigger to:</mark>
- An ``INSERT`` on ``B2_STOCK`` table.  
- An ``UPDATE`` on ``B2_STOCK`` table.  
- A ``DELETE`` on ``B2_STOCK`` table

<mark style="background: #69E772;">Set up the log table:</mark>
```SQL
create table stock_log(  
stock_code char(5),  
saleprice numeric(10,2),  
costprice numeric(10,2),  
stock_level numeric(7,0),  
username varchar(80),  
changedate date);
```

### <mark style="background: #69E772;">Triggers:</mark>

<mark style="background: #69E772;">We will set up:</mark>
• A row level ``INSERT`` and update audit trigger.  
• A row level ``INSERT`` and ``UPDATE`` constraint trigger.

```plSQL
CREATE or replace FUNCTION audit_stock() RETURNS trigger AS $audit_stock$  
DECLARE  
	uname varchar(80);  
	cdate date;  
BEGIN  
select user into strict uname;  
	select now() into strict cdate;  
	insert into stock_log values (new.stock_code, new.unit_price, new.unitcostprice,  
new.stock_level, uname, cdate);  
return new;  
END;  
$audit_stock$ LANGUAGE plpgsql;  

CREATE or replace TRIGGER audit_stock BEFORE INSERT OR UPDATE ON b2_stock  
	FOR EACH ROW EXECUTE FUNCTION audit_stock();
```

<mark style="background: #69E772;">Execute the trigger:</mark>

```SQL
insert into b2_stock values ('K144','Coat Hooks', 8.99, 5.00, 30,10,1);  
select * from stock_log;
```

Output was: `K144 8.99 5.00 30 G99999999 2023-10-07`

### <mark style="background: #69E772;">Trigger fired by the SQL operation:</mark>

<mark style="background: #69E772;">The operation works as normal on the table in the database, but it now fires a trigger:</mark>
- The ``TRIGGER`` adds a row to the ``logtable``.  
- While the ``INSERT`` adds a row to the ``b2_stock`` table,  

<mark style="background: #69E772;">Other operations:</mark> Triggers can be adapted to work on ``UPDATEs`` or ``DELETEs``.

### <mark style="background: #69E772;">Audit Trails:</mark>

When an ``INSERT ... FOR EACH ROW...`` trigger is active, it has access to the new values that the ``INSERT`` is trying to put into the table.  

These values can be accessed by preceding the attribute name with new:
- E.g. to get the value that the insert is trying to put into the ``stock_code`` column in the table, we can reference ``new.stock_code``

### <mark style="background: #69E772;">Data available to INSERT trigger:</mark>

![](https://i.imgur.com/6g34o78.png)

![](https://i.imgur.com/fnav7AJ.png)


### <mark style="background: #69E772;">Who added rows to the subject table?</mark>

<mark style="background: #69E772;">Create a table to hold the log of changes. Needs to know:</mark>
- username, 
- date, 
- st_name
- st_id.  

<mark style="background: #69E772;">Create a function 'audit_student', when someone performs 'INSERT' on the STUDENT table, record:</mark>
- The student name 'st_name'  
- The generated student id 'st_id'  
- The username  
- The date and time of the operation.  

Make a trigger from the function  

Perform one of the triggering operations and look at the log.

```mySQL
CREATE or replace FUNCTION ... RETURNS trigger AS $...$  
DECLARE  
	uname varchar(80);  
	cdate date;  
BEGIN  
	select user into strict uname;  
	select now() into strict cdate;  

	insert into ... values (..., uname, cdate);  
return new;  
END;  
$...$ LANGUAGE plpgsql;  
CREATE or replace TRIGGER ... BEFORE ... ON ...  
FOR EACH ROW EXECUTE FUNCTION ...();
```

### <mark style="background: #69E772;">Activate the trigger:</mark>

<mark style="background: #69E772;">From the schema that owns 'student':</mark>  
- Insert into student (st_name) values ('Delia');  
- Select from your log table.  

From G99999999:
- ``select "Sample".addstudent('Deirdre');``  

Did it work? What would you need to do to make it work?

## <mark style="background: #69E772;">Constraint Triggers:</mark>

<mark style="background: #69E772;">Declarative Constraints:</mark>

Where possible, the state of the data in the database is guarded by declarative constraints. E.G:

```plSQL
CREATE TABLE B2_SORDER (  
	SORDERNO SERIAL PRIMARY KEY,  
	SORDERDATE DATE  
	DEFAULT CURRENT_DATE NOT NULL,  
	DELIVEREDDATE DATE,  
	SUPPLIER_ID INTEGER  
	REFERENCES B2_SUPPLIER NOT NULL,  
	CONSTRAINT DATECHECK  
	CHECK(DELIVEREDDATE >SORDERDATE));
```

### <mark style="background: #69E772;">Limitations on CHECK constraint:</mark>
  
<mark style="background: #69E772;">The CHECK constraint:</mark>  
- Must be Boolean expression  
- Can only use values in the current row  
- Cannot contain sub-queries, sequences or some functions.  

<mark style="background: #69E772;">We need to be able to:</mark>  
- Check data in other rows or even tables.  
- Cause the operation to fail if it breaks the rules.

### <mark style="background: #69E772;">Triggering failure</mark> 

Constraint trigger  

<mark style="background: #69E772;">In a function:</mark>  
- Use SQL statements to get the data that needs to be checked.  
- Perform the check.  
- If the check fails, raise a user-defined exception.  

Create a trigger to fire before the operation, executing the function.

### <mark style="background: #69E772;">Recalling the builder schema:</mark>

When a customer order line is added, the customer specifies a quantity required.

Is there enough stock? Check the ``stock_level`` in the stock table.

![](https://i.imgur.com/QEOoEDx.png)

<mark style="background: #69E772;">Creating the function and trigger:</mark>

```plSQL
CREATE FUNCTION check_stock() RETURNS trigger AS $check_stock$  
DECLARE  
	QTY INTEGER;  
BEGIN  
	SELECT STOCK_LEVEL INTO QTY FROM B2_STOCK  
		WHERE STOCK_CODE = NEW.STOCK_CODE;  
	IF QTY - NEW.QUANTITYREQUIRED < 0 THEN  
		RAISE exception '% not enough stock for this order', new.corderno;  
	END IF;  
	return new;  
END;  
$check_stock$ LANGUAGE plpgsql;  

CREATE TRIGGER check_stock BEFORE INSERT OR UPDATE ON b2_corderline  
	FOR EACH ROW EXECUTE FUNCTION check_stock();
```

<mark style="background: #69E772;">Testing the trigger:</mark>

![](https://i.imgur.com/kUWCbnk.png)

<mark style="background: #69E772;">Finding the trigger:</mark>

![](https://i.imgur.com/VbnyRkI.png)

<mark style="background: #69E772;">Drop a trigger:</mark>

The syntax for a dropping a Trigger is:  
``DROP TRIGGER trigger_name;``

### <mark style="background: #69E772;">Sample triggers for BUILDER:</mark>

<mark style="background: #69E772;">Insert trigger that could go on corderline:</mark>
- Check there is enough stock before selling.  
- Reject invalid transactions  
- Record reorder requirements  

<mark style="background: #69E772;">Update trigger on supplier order delivery date:</mark>
- Check that date is not already there  
- Check that date is not in the future.

### <mark style="background: #69E772;">Built-in variables available in a trigger:</mark>

<mark style="background: #69E772;">NEW record</mark> - new database row for ``INSERT/UPDATE`` operations in row-level triggers. This variable is null in statement-level triggers and for ``DELETE`` operations.  

<mark style="background: #69E772;">OLD record</mark> - old database row for ``UPDATE/DELETE`` operations in row-level triggers. This variable is null in statement-level triggers and for ``INSERT`` operations.  

<mark style="background: #69E772;">TG_NAME name</mark> - name of the trigger which fired.  

<mark style="background: #69E772;">TG_WHEN text</mark> - ``BEFORE``, ``AFTER``, or ``INSTEAD OF``, depending on the trigger's definition.  

<mark style="background: #69E772;">TG_LEVEL text</mark> - ``ROW`` or ``STATEMENT``, depending on the trigger's definition.  

<mark style="background: #69E772;">TG_OP text</mark> - operation for which the trigger was fired: ``INSERT``, ``UPDATE``, ``DELETE``, or ``TRUNCATE``.  

<mark style="background: #69E772;">TG_TABLE_NAME name</mark> - table that caused the trigger invocation.  

<mark style="background: #69E772;">TG_TABLE_SCHEMA name</mark> - schema of the table that caused the trigger invocation.

### <mark style="background: #69E772;">Transactions and multiple users:</mark>

<mark style="background: #69E772;">Concurrent usage:</mark>
- Enabling  
- Problems arising  
- ACID properties  

Commit and Rollback (Autocommit)  

Transaction modes

### <mark style="background: #69E772;">Concurrent Usage:</mark>

A schema has at least one role with full access.  

Other users can only manipulate data in your schema if you grant them privileges to do so.  

You can ``GRANT`` privileges to specific users, or to PUBLIC (all users).  

You can ``REVOKE`` privileges you have previously granted.  

Note: In PostgreSQL you must first:  
``GRANT USAGE ON SCHEMA <myschema> TO <other_user>;``

### <mark style="background: #69E772;">GRANT and REVOKE:</mark>

You can ``GRANT SELECT`` on ``<mytable>`` TO "G99999999";  

You can ``GRANT SELECT`` on ``<mytable>`` TO PUBLIC;  

You can ``GRANT INSERT`` on ``<mytable>`` to PUBLIC;  

Now everyone can add data!  

You can ``REVOKE INSERT`` on ``<mytable>`` FROM PUBLIC;  

Probably a good idea.  

``GRANT ALL ON`` ``<mytable>`` TO PUBLIC;  

Probably NOT a good idea. Now everyone can ``INSERT``, ``UPDATE``, ``DELETE`` and ``SELECT`` your data.

### <mark style="background: #69E772;">What other privileges?</mark>

<mark style="background: #69E772;">I can grant / revoke:</mark>
- SELECT, INSERT, UPDATE or DELETE on my tables or views to roles.  
- EXECUTE on functions or stored procedures.  

<mark style="background: #69E772;">Note:</mark>
- If the function / procedure does an ``INSERT``, the grantee must be granted ``INSERT`` privileges on the table.  
- If the ``INSERT`` generates a new serial ID, the grantee must be granted ``UPDATE`` on the ``SEQUENCE``.

### <mark style="background: #69E772;">Sample access:</mark>

If I want "G99999999" to be able to run the 'addstudent' function:

```plSQL
Grant usage on schema "Sample" to public;  
grant execute on function addstudent to "G99999999";  
grant insert on table student to "G99999999";  
grant update on table student to "G99999999";
```

### <mark style="background: #69E772;">Principle of least privilege:</mark>

“Only the minimum necessary rights should be assigned to a subject that requests access to a resource and should be in effect for the shortest duration necessary (remember to relinquish privileges).  
Granting permissions to a user beyond the scope of the necessary rights of an action can allow that user to obtain or change information in unwanted ways. Therefore, careful delegation of access rights can limit attackers from damaging a system. ”

https://www.us-cert.gov/bsi/articles/knowledge/principles/least-privilege  - United States Computer Emergency Readiness team.

### <mark style="background: #69E772;">Major weakness in security:</mark>

Granting all privileges on ``CREATE USER``:  

“...I cannot think of any circumstances when ALL PRIVILEGES should be granted to anyone. It is simply unnecessary. Do the job correctly and find out the exact privileges needed for the job in hand and grant those. Granting all privileges is a security risk as it means the user having those privileges can do just about anything in your database.”  - Pete Finnigan, Oracle Security Expert

### <mark style="background: #69E772;">Locking and concurrency:</mark>

How to cope with multiple users conducting simultaneous transactions

### <mark style="background: #69E772;">Transactions:</mark> 

In the Builder Case Study we require transactions to:  

<mark style="background: #69E772;">Add an order:</mark>  
- Maybe add a customer  
- Add an order  
- Add one or more order lines to the order. Each new line means we need to adjust the remaining amount in the stock table.  
- Confirm (commit) or abandon (rollback) the order)  

<mark style="background: #69E772;">Ship an order:</mark>  
- Confirm that the stock has been handed over to the customer.  
- This requires an update of the order table.  

There are more.

### <mark style="background: #69E772;">Concurrent transactions (Builder)</mark>

![](https://i.imgur.com/RLcCe6n.png)

### <mark style="background: #69E772;">If it is a single-user system:</mark>

Fred will put in his order and the stock-level for the bicycle locks will go down to 5.  

Joe will try to order 7 locks and won’t be allowed.  

OR  

Joe will put in his order and stock-level for the locks will go down to 8.  

Fred will try to order 10 locks and won’t be allowed.  

But what if they are both are working at the same time?

### <mark style="background: #69E772;">Problems with Concurrency:</mark>

<mark style="background: #69E772;">Concurrent transaction can cause three kinds of database problems:</mark>
- Lost Update  
- Violation of Integrity Constraints  
- Inconsistent Retrieval

### <mark style="background: #69E772;">Lost update (Builder):</mark>

Apparently successful updates can be overwritten by other transactions.

```plSQL
Initial Balance = 100
```

![](https://i.imgur.com/BvNELAW.png)

![](https://i.imgur.com/PsFC1j5.png)

Either update could go a fraction of a second earlier and overwrite the other.

### <mark style="background: #69E772;">Inconsistent Retrieval (Dirty Reads):</mark>

If transactions are allowed to read the partial results of incomplete transactions, they can obtain an inconsistent view of the DB (dirty or unrepeatable reads).

### <mark style="background: #69E772;">Concurrency Control:</mark>

<mark style="background: #69E772;">Transaction:</mark> the basic unit of work in a RDBMS  

<mark style="background: #69E772;">Properties of a transaction:</mark>  
- ATOMICITY  
- CONSISTENCY  
- ISOLATION  
- DURABILITY

![](https://i.imgur.com/LQEFiBm.png)

### <mark style="background: #69E772;">A.C.I.D properties:</mark>

<mark style="background: #69E772;">Atomicity:</mark> the is the “all or nothing” property ; a transaction is an indivisible unit of work.  

<mark style="background: #69E772;">Consistency:</mark> transactions transform the DB from one consistent state to another consistent state.

<mark style="background: #69E772;">Isolation:</mark> transactions execute in isolation i.e. the partial effect of one transaction is not visible to other transactions.

<mark style="background: #69E772;">Durability (aka Persistence):</mark> the effect of a successfully completed (i.e. committed) transaction are permanently recorded in the DB and cannot be undone.

### <mark style="background: #69E772;">Conflicting Operations:</mark>

If two transactions only read a data item, they do <mark style="background: #69E772;">not</mark> conflict and order is not important.  

If two transactions either read or write completely separate data items, they do not conflict and order is <mark style="background: #69E772;">not</mark> important.  

If one transactions writes a data item and another transaction reads or writes the same data item, the order of execution <mark style="background: #69E772;">is</mark> important.

### <mark style="background: #69E772;">Making changes persist:</mark>

When data is changed, it must be persisted, to ensure that the change takes.  

<mark style="background: #69E772;">E.g. a text editor:</mark>  
- ``SAVE`` will ``COMMIT`` your changes.  
- ``QUIT`` will ``ROLLBACK`` your changes.  

<mark style="background: #69E772;">AUTOCOMMIT:</mark>  
- When this feature is ON, changes are persisted as soon as they happen. Similar to Google Docs.

### <mark style="background: #69E772;">AUTOCOMMIT, COMMIT and ROLLBACK:</mark>

Many modern database clients set ``autocommit`` on by default.

![](https://i.imgur.com/9rpddOY.png)

![](https://i.imgur.com/CEktyAp.png)

### <mark style="background: #69E772;">Transactions:</mark>

A transaction (or logical unit of work) is a sequence of SQL statements that ``postgreSQL`` treats as a single unit.  

<mark style="background: #69E772;">A transaction ends with a</mark>  
- commit,  
- rollback ,  
- any DDL statement which issues an implicit commit.

### <mark style="background: #69E772;">Implicit and explicit transactions:</mark>

<mark style="background: #69E772;">In autocommit mode:</mark>  
- Every SQL statement is considered to be a transaction  
- It has an implicit ``BEGIN`` before it.  
- It has an implicit ``COMMIT`` after it.  

TURN AUTOCOMMIT OFF!!!

![](https://i.imgur.com/3dDi43M.png)

### <mark style="background: #69E772;">Transactions and locking:</mark>

Transactions start with ``BEGIN``  

When an ``INSERT``, ``UPDATE`` or ``DELETE`` takes place:  
- It locks the row that is being ``INSERTed`` / ``UPDATEd`` / ``DELETEd``  
- Other sessions cannot see the changes that are being made.  
- The lock holds until the transaction session is finished by issuing ``COMMIT`` or ``ROLLBACK``

### <mark style="background: #69E772;">The transaction control commands:</mark>

<mark style="background: #69E772;">commit</mark> makes all changes since the beginning of a transaction permanent  

<mark style="background: #69E772;">rollback</mark> rolls back (undoes) all changes since the beginning of a transaction.  

<mark style="background: #69E772;">Other users:</mark>  
- cannot see the results of the transaction until it has been committed.  
- Can see the data as it was before the other user's transaction started!

### <mark style="background: #69E772;">Overview:</mark>

<mark style="background: #69E772;">Locking:</mark>  
- allows a user to take hold of a block for updating.  
- Prevents other users from modifying the same data.  
- Locks can create performance problems.  
- When one process locks, others are shut out.  
- There are several levels of locking.

<mark style="background: #69E772;">When modifying:</mark>  
- The transaction should place a lock until committed or rolled back.
- This is known as data concurrency.

<mark style="background: #69E772;">Read-consistency:</mark>
- All processes can access (read) the original data as they were at the time the query began (uncommitted modification).

### <mark style="background: #69E772;">Row-level Locking (read consistency):</mark>

Each row can be locked individually.  

Locked rows can only be updated by the locking session.  

Other rows can be updated by other sessions.  

Other sessions can still read all rows.  

When other sessions read locked rows, they see the pre-locked values for the row.  

When the lock is released, by ``COMMIT`` or ``ROLLBACK``, the new values are visible to other sessions.

### <mark style="background: #69E772;">Locking rows:</mark>

![](https://i.imgur.com/vPEjbjA.png)

### <mark style="background: #69E772;">Exclusive locks:</mark>

<mark style="background: #69E772;">Exclusive locks occur on ROWS when:</mark>  
- The row is ``INSERTed`` 
- The row is ``DELETEd``
- The row is ``UPDATEd``  
- The row is ``SELECTed``... FOR ``UPDATE``...

### <mark style="background: #69E772;">Deadlocks:</mark>

A deadlock can occur when two or more users are waiting for data locked by each other.  

Deadlocks prevent some transactions from continuing to work.  

The next example illustrates two transactions in a deadlock.

### <mark style="background: #69E772;">Example:</mark>

![](https://i.imgur.com/9CmPlp1.png)

### <mark style="background: #69E772;">Example explanation:</mark>

<mark style="background: #69E772;">At timepoint A:</mark>  
- no problem exists as each transaction has a row lock on the row it attempts to update.  
- Each transaction proceeds without being terminated.  
- However, each tries next to update the row currently held by the other transaction.  

<mark style="background: #69E772;">At timepoint B:</mark>  
- a deadlock results, because neither transaction can obtain the resource it needs to proceed or terminate.  
- It is a deadlock because no matter how long each transaction waits, the conflicting locks are held.

### <mark style="background: #69E772;">How to avoid Deadlocks:</mark>

Application developers can eliminate all risk of deadlocks by ensuring that transactions requiring multiple resources <mark style="background: #69E772;">always lock them in the same order.</mark>  

However, in complex applications, this is easier said than done, particularly if an ad hoc query tool is used.  

To be safe, you should adopt a strict locking order, but you must also <mark style="background: #69E772;">handle locking exceptions</mark>.  

<mark style="background: #69E772;">To handle locking exceptions:</mark>  
- Pause for three seconds, and then retry the statement.  
- Or, roll back the transaction, wait 3 seconds and retry.

# <mark style="background: #69E772;">04 Normalisation and Indexes:</mark>

### <mark style="background: #69E772;">Database Normalisation:</mark>

Normalisation is a process for assigning attributes to entities. It reduces data redundancies and helps eliminate the data anomalies.  

<mark style="background: #69E772;">Normalisation works through a series of stages called normal forms:</mark>
- First normal form (1NF)  
- Second normal form (2NF)  
- Third normal form (3NF)  
- Boyce-Codd NF (BCNF)  

The highest level of normalisation is not always desirable. (we’ll see why...)

### <mark style="background: #69E772;">Scenario:</mark>

![](https://i.imgur.com/Rrtofjw.png)

### <mark style="background: #69E772;">The Need for Normalisation:</mark>

Case of a Construction Company  

Building project - Project number, Name, Employees assigned to the project.  

Employee - Employee number, Name, Job classification  

The company charges its clients by billing the hours spent on each project. The hourly billing rate is dependent on the employee’s position.  

Periodically, a report is generated.  

Employees can work on multiple projects. The hourly rate for each employee position is fixed

### <mark style="background: #69E772;">Sample Form:</mark>

![](https://i.imgur.com/qtmZhhZ.png)

### <mark style="background: #69E772;">Sample Data:</mark>

![](https://i.imgur.com/lTKv9IF.png)

### <mark style="background: #69E772;">Table Structure based on the form:</mark>

![](https://i.imgur.com/0cKhmtL.png)

### <mark style="background: #69E772;">1NF</mark>

<mark style="background: #69E772;">1NF Definition:</mark> The term first normal form (1NF) describes the tabular format in which:  
- All the primary key attributes are defined.  
- All attributes are dependent on the primary key.  

<mark style="background: #69E772;">In a nutshell:</mark> you must have a valid primary key.  

<mark style="background: #69E772;">Terminology:</mark>  
- Candidate key: one or more field that can act as primary key  
- "dependent" on primary key = A depends on B if I can compute the value of B if I know A.

### <mark style="background: #69E772;">Dependency Diagram:</mark>
 
The primary key components are bold, underlined, and shaded in a different colour.  

The arrows above entities indicate all desirable dependencies, i.e., dependencies that are based on  
PK.  

The arrows below the dependency diagram indicate less desirable dependencies - partial dependencies

![](https://i.imgur.com/qFutkN8.png)

### <mark style="background: #69E772;">2NF:</mark>

Conversion to Second Normal Form  

<mark style="background: #69E772;">Definition:</mark> all the non-key attributes are dependent on the full primary key  

Starting with the 1NF format, the database can be converted into the 2NF format by  

Writing each key component on a separate line, and then writing the original key on the last line and  

Writing the dependent attributes after each new key.  

```SQL
PROJECT (PROJ_NUM, PROJ_NAME)  
EMPLOYEE (EMP_NUM, EMP_NAME, JOB_CLASS, CHG_HOUR)  
ASSIGN (PROJ_NUM, EMP_NUM, HOURS)
```

![](https://i.imgur.com/f9gwqCN.png)

<mark style="background: #69E772;">A table is in 2NF if:</mark>  
- It is in 1NF and  
- It includes no partial dependencies; that is, no attribute is dependent on only a portion of the primary key.  
- (It is still possible for a table in 2NF to exhibit <mark style="background: #69E772;">transitive dependency</mark>; that is, one or more attributes may be functionally dependent on a non-key attributes.)

### <mark style="background: #69E772;">3NF:</mark>

Conversion to Third Normal Form: Create a separate table with attributes in a transitive functional dependence relationship.  

```
PROJECT (PROJ_NUM, PROJ_NAME)  
ASSIGN (PROJ_NUM, EMP_NUM, HOURS)  
EMPLOYEE (EMP_NUM, EMP_NAME, JOB_CLASS)  
JOB (JOB_CLASS, CHG_HOUR)
```

<mark style="background: #69E772;">3NF Definition -  A table is in 3NF if:</mark>  
- It is in 2NF and  
- It contains no transitive dependencies.

### <mark style="background: #69E772;">The Completed Database:</mark>

![](https://i.imgur.com/zI4y1N6.png)

### <mark style="background: #69E772;">Boyce-Codd Normal Form (BCNF):</mark>

When a relation has more than one candidate key, anomalies may result even though the relation is in 3NF.  

3NF does not deal satisfactorily with the case of a relation with overlapping candidate keys, i.e. composite candidate keys with at least one attribute in common.  

BCNF is based on the concept of a determinant.  

A determinant is any attribute (simple or composite) on which some other attribute is fully functionally dependent.  

A relation is in BCNF is, and only if, every determinant is a candidate key.

A table is in Boyce-Codd normal form (BCNF) if every determinant in the table is a candidate key.  

(A determinant is any attribute whose value determines other values with a row.)  

If a table contains only one candidate key, the 3NF and the BCNF are equivalent.  

BCNF is a special case of 3NF.  

Figure 5.7 (next slide) illustrates a table that is in 3NF but not in BCNF.  

Figure 5.8 (two slide after this one) shows how the table can be decomposed to conform to the BCNF form.

<mark style="background: #69E772;">A Table in 3NF but not in BCNF: </mark>
![](https://i.imgur.com/CNACcvh.png)

AB = candidate key (and primary composite key)  

C = determinant, since B depends on B (note that B is part of the key and C is a non-key attribute) AC could have been a key as well  

Not in BCNF is C is a determinant but it is not (on its own) a candidate key

<mark style="background: #69E772;">Decomposition of a Table Structure to Meet BCNF Requirements:</mark>

![](https://i.imgur.com/09jjQZv.png)

### <mark style="background: #69E772;">Sample Data for a BCNF conversion:</mark>

![](https://i.imgur.com/51HbN4o.png)

### <mark style="background: #69E772;">Decomposition into BCNF:</mark>

![](https://i.imgur.com/Vxnjjth.png)

### <mark style="background: #69E772;">Denormalisation:</mark>

Normalisation is only one of many database design goals.  

Normalised (decomposed) tables require additional processing, reducing system speed.  

Normalisation purity is often difficult to sustain in the modern database environment. The conflict between design efficiency, information requirements, and processing speed are often resolved through compromises that include de-normalisation.

### <mark style="background: #69E772;">Useful Commands:</mark>

<mark style="background: #69E772;">Move data into a table:</mark>  

```plSQL
INSERT INTO staff( firstName, lastName, address, homePhone, cellPhone, latitude, longitude)  
SELECT firstName, lastName, address, homePhone, cellPhone, latitude, longitude  
FROM gfxContact;
```

<mark style="background: #69E772;">Create a table from another table:</mark>

```plSQL
CREATE TABLE EMP (
	EMPNO NUMBER(4) NOT NULL,  
	ENAME VARCHAR2(10),  
	JOB VARCHAR2(9),  
	MGR NUMBER(4),  
	HIREDATE DATE,  
	SAL NUMBER(7, 2),  
	COMM NUMBER(7, 2),  
	DEPTNO NUMBER(2));

INSERT INTO EMP VALUES (7369, 'SMITH', 'CLERK', 7902, TO_DATE('17-DEC-1980', 'DD-MON-YYYY'), 800, NULL, 20);

INSERT INTO EMP VALUES (7499, 'ALLEN', 'SALESMAN', 7698, TO_DATE('20-FEB-1981', 'DD-MON-YYYY'), 1600, 300, 30);

-- Copying selected columns from another table
CREATE TABLE newTable  
AS (SELECT empno, ename FROM emp);
```

### <mark style="background: #69E772;">Type of File:</mark>

Database tables are saved on a collections of files  

<mark style="background: #69E772;">Type of file:</mark>  
- Unordered  
- Ordered  
- Hashed

### <mark style="background: #69E772;">Unordered:</mark>

Also called a <mark style="background: #69E772;">heap</mark> or a <mark style="background: #69E772;">pile</mark> file.  

New records are inserted at the end of the file.  

A <mark style="background: #69E772;">linear search</mark> through the file records is necessary to search for a record.  

This requires reading and searching half the file blocks on the average, and is hence quite expensive.  

Record insertion is quite efficient.  

Reading the records in order of a particular field requires sorting the file records.

### <mark style="background: #69E772;">Ordered Files:</mark>

Also called a <mark style="background: #69E772;">sequential</mark> file.  

File records are kept sorted by the values of an <mark style="background: #69E772;">ordering field</mark>.  

<mark style="background: #69E772;">Insertion is expensive:</mark> records must be inserted in the correct order.  

It is common to keep a separate unordered overflow (or transaction) file for new records to improve insertion efficiency; this is periodically merged with the main ordered file.  

A <mark style="background: #69E772;">binary search</mark> can be used to search for a record on its ordering field value.  

This requires reading and searching log2 of the file blocks on the average, an improvement over linear search.  

Reading the records in order of the ordering field is quite efficient.

![](https://i.imgur.com/6pHF81B.png)

### <mark style="background: #69E772;">Average Access Times:</mark>

The following table shows the average access time to access a specific record for a given type of file

![](https://i.imgur.com/Dh43K7t.png)

### <mark style="background: #69E772;">Hashed Files:</mark>

The file blocks are divided into M equal-sized <mark style="background: #69E772;">buckets</mark>, numbered ``bucket0, bucket1, ..., bucketM-1.``

Typically, a bucket corresponds to one (or a fixed number of) disk block.  

One of the file fields is designated to be the <mark style="background: #69E772;">hash key</mark> of the file.  

The record with hash key value K is stored in bucket i, where i=h(K), and h is the <mark style="background: #69E772;">hashing function</mark>.  

Search is very efficient on the hash key.  

Collisions occur when a new record hashes to a bucket that is already full.  

An overflow file is kept for storing such records.  

Overflow records that hash to each bucket can be linked together.
  
<mark style="background: #69E772;">There are numerous methods for collision resolution, including the following:</mark>
- <mark style="background: #69E772;">Open addressing:</mark> Proceeding from the occupied position specified by the hash address, the program checks the subsequent positions in order until an unused (empty) position is found.  
- <mark style="background: #69E772;">Chaining:</mark> For this method, various overflow locations are kept, usually by extending the array with a number of overflow positions. In addition, a pointer field is added to each record location. A collision is resolved by placing the new record in an unused overflow location and setting the pointer of the occupied hash address location to the address of that overflow location.  
- <mark style="background: #69E772;">Multiple hashing:</mark> The program applies a second hash function if the first results in a collision. If another collision results, the program uses open addressing or applies a third hash function and then uses open addressing if necessary.

### <mark style="background: #69E772;">Hashed Files - Chaining:</mark>

![](https://i.imgur.com/J3BJuEb.png)

To reduce overflow records, a hash file is typically kept 70-80% full.  

The hash function h should distribute the records uniformly among the buckets  

Otherwise, search time will be increased because many overflow records will exist.  

<mark style="background: #69E772;">Main disadvantages of static external hashing:</mark>  
- Fixed number of buckets M is a problem if the number  of records in the file grows or shrinks.  
- Ordered access on the hash key is quite inefficient (requires sorting the records)

### <mark style="background: #69E772;">Dynamic and Extendible Hashed Files:</mark>

<mark style="background: #69E772;">Dynamic and Extendible Hashing Techniques</mark>
- Hashing techniques are adapted to allow the dynamic growth and shrinking of the number of file records.  
- These techniques include the following: <mark style="background: #69E772;">dynamic</mark> <mark style="background: #69E772;">hashing</mark>, <mark style="background: #69E772;">extendible hashing</mark>, and <mark style="background: #69E772;">linear hashing</mark>.  

Both dynamic and extendible hashing use the <mark style="background: #69E772;">binary representation</mark> of the hash value h(K) in order to access a directory.  
- In dynamic hashing the directory is a binary tree. 
- In extendible hashing the directory is an array of size 2d where d is called the <mark style="background: #69E772;">global depth</mark>.

The directories can be stored on disk, and they expand or shrink dynamically.  

Directory entries point to the disk blocks that contain the stored records.  

An insertion in a disk block that is full causes the block to split into two blocks and the records are redistributed among the two blocks. The directory is updated appropriately.  

Dynamic and extendible hashing do not require an overflow area.

### <mark style="background: #69E772;">Dynamic Hashing:</mark>

![](https://i.imgur.com/Uv3pEtD.png)

![](https://i.imgur.com/pJFqO3U.png)

### <mark style="background: #69E772;">Indexes:</mark>

<mark style="background: #69E772;">Indexes</mark> are additional auxiliary access structures with typically provide <mark style="background: #69E772;">either</mark> faster access to data or secondary access paths without effecting the physical storage of the data.

They are based on <mark style="background: #69E772;">indexing field(s)</mark> that are used to construct the <mark style="background: #69E772;">index</mark>.  

Indexes can be <mark style="background: #69E772;">sparse or dense</mark>. A dense index has an entry for each record.

### <mark style="background: #69E772;">Types of Indexes:</mark>

<mark style="background: #69E772;">Single-Level Indexes:</mark>
- Primary (Clustered or not)  
- Secondary  
- Bitmap  

<mark style="background: #69E772;">Multi-Level Indexes:</mark>  
- Binary Trees  
- B-Trees

### <mark style="background: #69E772;">Single Level Indexes:</mark>

<mark style="background: #69E772;">Single Level</mark> = there is only 1 level of indirection. The entries in the index are pointing to the data in the table.

<mark style="background: #69E772;">Multiple-Index</mark> = entries in the index might point to other entries in the index , that eventually point to the data.

A <mark style="background: #69E772;">Primary Index</mark> is specified on the <mark style="background: #69E772;">ordering key field</mark> where each tuple has a <mark style="background: #69E772;">unique</mark> value.

A <mark style="background: #69E772;">Secondary Index</mark> is specified on a ``NON-ORDERING`` <mark style="background: #69E772;">Field</mark> of the file.

### <mark style="background: #69E772;">Primary Indexes:</mark>

A Primary Index is constructed of two parts: The first field is the same data type of the primary key of a file block of the data file and the second field is file block pointer.  

If the primary index is clustered, the file is physically sorted using the indexing field. If this is the case:  

The Anchor Record or Block anchor is the first record in a file block. This is where the value for the first field of the primary index come from along with the respective address of that block.

![](https://i.imgur.com/2mB3NoV.png)

# <mark style="background: #69E772;">Primary Indexes (clustered):</mark>

<mark style="background: #69E772;">The primary index file is usually smaller than the data file it’s indexing because:</mark>
- There are usually fewer index entries than records in the data file (because a block holds more than one record)  
- The individual index records are smaller than data file records  

Binary <mark style="background: #69E772;">search</mark> on index file is faster than binary search on the database  

<mark style="background: #69E772;">But slow for insertion and deletion:</mark>  
- records have to be kept in order in the data file 
- AND index file has to be kept in order too

We have shown a primary sparse index, where the “big” file (=table) is physically sorted by the key and the index structure indexes each block. This is usually called a clustered index, since each entry in the index points to a “cluster” or values  

<mark style="background: #69E772;">Some DBs (latest Oracle versions) implement primary index like secondary index:</mark>
- The table is left unordered like a heap  
- The index structure has an entry for each record (not each block) and it is a dense index

### <mark style="background: #69E772;">Secondary Indexes:</mark>  

An index file that uses a non primary field as an index e.g. Job field in the employee table  

They improve the performance of queries that use attributes <mark style="background: #69E772;">other</mark> than the primary key  

You can use a separate index for every attribute you wish to use in the ``WHERE`` clause of your select query  

But there is the overhead of maintaining a large number of these indexes

A <mark style="background: #69E772;">Secondary Index</mark> is an <mark style="background: #69E772;">ordered file</mark> with two fields. The first is of the same data type as some <mark style="background: #69E772;">non-ordering field</mark> and the second is either a block or a record pointer.  

If the <mark style="background: #69E772;">entries</mark> in this non-ordering field must be unique this field is sometime referred to as a <mark style="background: #69E772;">Secondary Key</mark>. This results in a dense index.  

For a secondary index, an external index file has a list of pointers to the various values of the indexed column (i.e. It’s a logical index, not physical) so you can have many secondary indexes  
- What would a secondary index to a telephone directory look like? E.g. Road Name?  
- WHY would you use a secondary index?

### <mark style="background: #69E772;">Primary Indexes (not clustered):</mark>

A <mark style="background: #69E772;">Primary Index</mark> can also be not clustered. In this case, the file (table) is not physically sorted by the index key.  

For each entry in the table, there is an entry in the index, so a primary index not clustered is a dense index.

![](https://i.imgur.com/pXemiJa.png)

### <mark style="background: #69E772;">Secondary Index on Non-Key Field:</mark>

A secondary index is an index defined on a non-key field. It can be implemented as a primary index (not clustered) but since there is <mark style="background: #69E772;">no guarantee</mark> that the value will be <mark style="background: #69E772;">unique</mark> the previous index method will not work in all the case.  
- <mark style="background: #69E772;">Option 1:</mark> Include index entries for each record. This results in multiple entries of the same value.  
- <mark style="background: #69E772;">Option 2:</mark> Use variable length records with a pointer to each block/record with that value. 
- <mark style="background: #69E772;">Option 3:</mark> Have the pointer; point to a block or chain of blocks that contain pointers to all the blocks/records that contain the field value. Example of multi-level index

![](https://i.imgur.com/P64lk9Y.png)

### <mark style="background: #69E772;">Bitmap Index:</mark>

An index implemented as a map of bits  

Each unique entry in the index is a string of bits  

Usually used on fields that are not (or rarely) modified  

Fields with low cardinality  

Used in read-only environment like data warehouses  

Typical example: day of the week, gender,...  

<mark style="background: #69E772;">How many bytes is a bitmap index on:</mark>  
- Day of the week for 10 millions records  
- Gender for 1 billion records

![](https://i.imgur.com/mvwwy86.png)

### <mark style="background: #69E772;">Multilevel Indexes:</mark>

A <mark style="background: #69E772;">Multilevel Index</mark> is where you construct an <mark style="background: #69E772;">Second-Level</mark> index on a <mark style="background: #69E772;">First-Level</mark> Index.  

Continue this process until the <mark style="background: #69E772;">entire</mark> index can be contained in a <mark style="background: #69E772;">Single File Block</mark>.  

This allows much faster access than binary search because at each level the size of the index is reduced by the fan out factor. Rather just by 2 as in binary search.

![](https://i.imgur.com/mTTZaFW.png)

In databases, multi-level indexes are implemented using a tree structure  

A tree is a data structure with specific rules, which ones?

### <mark style="background: #69E772;">Multilevel Indexes Using Search Trees, B-Trees & B+ Trees:</mark>

A <mark style="background: #69E772;">Search Tree</mark> of order <mark style="background: #69E772;">p</mark> differs from a <mark style="background: #69E772;">Multilevel Index</mark> in that each node contains a most <mark style="background: #69E772;">p - 1</mark> search values and <mark style="background: #69E772;">p</mark> pointers.  

There is <mark style="background: #69E772;">no</mark> requirement that the Search Tree be Balanced.

![](https://i.imgur.com/opp7EEA.png)

### <mark style="background: #69E772;">B-trees:</mark>

<mark style="background: #69E772;">B-Trees</mark> address the problems with Search Trees in that they have the <mark style="background: #69E772;">additional</mark> constraint that they be <mark style="background: #69E772;">balanced</mark> and they contain pointers to data records.  

Each B-Tree is made up of at most P tree pointers and P-1 field values K and data pointers Pr.

![](https://i.imgur.com/sqXTxK4.png)


### <mark style="background: #69E772;">Query executions in Postgres:</mark>

<mark style="background: #69E772;">1. Seq Scan:</mark> the Seq Scan operation scans the entire relation (table) as stored on disk  

<mark style="background: #69E772;">2. Index Scan:</mark> the Index Scan performs a B-tree traversal, walks through the leaf nodes to find all matching entries, and fetches the corresponding table data. The so-called index filter predicates often cause performance problems for an Index Scan.  

<mark style="background: #69E772;">3. Index Only Scan:</mark> The Index Only Scan performs a B-tree traversal and walks through the leaf nodes to find all matching entries. There is no table access needed because the index has all columns to satisfy the query  

<mark style="background: #69E772;">4. Bitmap Index Scan / Bitmap Heap Scan / Recheck Cond:</mark> A plain Index Scan fetches one tuple-pointer at a time from the index, and immediately visits that tuple in the table. A bitmap scan fetches all the tuple-pointers from the index in one go, sorts them using an in-memory “bitmap” data structure, and then visits the table tuples in physical tuple-location order.

Generally join operations process only two tables at a time. In case a query has more joins, they are executed sequentially: first two tables, then the intermediate result with the next table. In the context of joins, the term “table” could therefore also mean “intermediate result”.  

<mark style="background: #69E772;">1. Nested Loops:</mark> Joins two tables by fetching the result from one table and querying the other table for each row from the first.  

<mark style="background: #69E772;">2. Hash Join / Hash:</mark> The hash join loads the candidate records from one side of the join into a hash table (marked with Hash in the plan) which is then probed for each record from the other side of the join. 

<mark style="background: #69E772;">3. Merge Join:</mark> The (sort) merge join combines two sorted lists like a zipper. Both sides of the join must be pre-sorted.

<mark style="background: #69E772;">1. Sort / Sort Key:</mark> Sorts the set on the columns mentioned in Sort Key. The Sort operation needs large amounts of memory to materialise the intermediate result.  

<mark style="background: #69E772;">2. GroupAggregate:</mark> Aggregates a pre-sorted set according to the group by clause. This operation does not buffer large amounts of data  

<mark style="background: #69E772;">3. HashAggregate:</mark> Uses a temporary hash table to group records. The ``HashAggregate`` operation does not require a pre-sorted data set, instead it uses large amounts of memory to materialize the intermediate result. The output is not ordered in any meaningful way.  

<mark style="background: #69E772;">4. Limit:</mark> Aborts the underlying operations when the desired number of rows has been fetched. The efficiency of the top-N query depends on the execution mode of the underlying operations. It is very inefficient with operations such as Sort.  

<mark style="background: #69E772;">5. WindowAgg:</mark> Indicates the use of window functions.

# <mark style="background: #69E772;">05 Indexes and Queries Optimisation:</mark>

### <mark style="background: #69E772;">Type of File:</mark>

Database tables are saved on a collections of files

<mark style="background: #69E772;">Type of file:</mark>
- Unordered
- Ordered
- Hashed

### <mark style="background: #69E772;">Type of File: Unordered</mark>

Also called a <mark style="background: #69E772;">heap</mark> or a <mark style="background: #69E772;">pile</mark> file.

New records are inserted at the end of the file.

A <mark style="background: #69E772;">linear search</mark> through the file records is necessary to search for a record. This requires reading and searching half the file blocks on the average, and is hence quite expensive.

Record insertion is quite efficient.

Reading the records in order of a particular field requires sorting the file records. 

### <mark style="background: #69E772;">Ordered Files:</mark>

Also called a <mark style="background: #69E772;">sequential</mark> file.

File records are kept sorted by the values of an <mark style="background: #69E772;">ordering field</mark>.

<mark style="background: #69E772;">Insertion is expensive:</mark> records must be inserted in the correct order.

It is common to keep a separate unordered <mark style="background: #69E772;">overflow</mark> (or <mark style="background: #69E772;">transaction</mark>) file for new records to improve insertion efficiency; this is periodically merged with the main ordered file.

A <mark style="background: #69E772;">binary search</mark> can be used to search for a record on its <mark style="background: #69E772;">ordering field</mark> value.

This requires reading and searching log2 of the file blocks on the average, an improvement over linear search.

Reading the records in order of the ordering field is quite efficient.

![](https://i.imgur.com/c5Ndqu0.png)

### <mark style="background: #69E772;">Explain Analyse in Postgres:</mark>

It gives information on query execution time, cost and steps need to compute the output of each query

![](https://i.imgur.com/f6Pk6Ic.png)


### <mark style="background: #69E772;">Query Cost:</mark>

Cost: arbitrary units, 1 unit = cost to read a page (of data) sequentially. They make sense only to compare queries.

Sort  (cost=66.83..69.33 rows=1000 width=17) 

<mark style="background: #69E772;">Two costs:</mark>
- <mark style="background: #69E772;">Start-up cost:</mark> This is an estimate of how long it will take to fetch the first row
- <mark style="background: #69E772;">Total cost:</mark> how long will it take to return all the rows the query requires

Rows = number of rows (estimated) and width = estimated size in bytes

Using ``EXPLAIN ANALYZE`` you can also see the actual time spent executing the query dividing in “planning time” and “execution time”. 

```plSQL
explain analyze select * from persons;

Seq Scan on persons  (cost=0.00..214.00 rows=10000 width=60) (actual time=0.015..0.358 rows=10000 loops=1)

-- Planning Time: 0.063 ms
-- Execution Time: 0.526 ms
```

### <mark style="background: #69E772;">How is cost computed?</mark>

```plSQL
explain analyze select * from persons; 
Seq Scan on persons  (cost=0.00..214.00 rows=10000 width=60)
```

<mark style="background: #69E772;">Why total cost of 214?</mark>
- The cost parameters ``seq_page_cost``, ``cpu_tuple_cost``  have the following defaults values:
- ``seq_page_cost  = 1``, 
- ``cpu_tuple_cost  = 0.01`` (time to process each tuple, see https://postgresqlco.nf/doc/en/param/cpu_tuple_cost/)

Total cost of Seq Scan = (estimated sequential page reads * ``seq_page_cost``) + (estimated rows returned * ``cpu_tuple_cost``)

How do I know how many pages were read?

```plSQL
explain (analyze, buffers) select * from persons; 
Seq Scan on persons  (cost=0.00..214.00 rows=10000 width=60)
Buffers: shared hit=114
```

We need to execute the explain with the keyword buffers as well

```
Total cost of Seq Scan = (estimated sequential page reads * seq_page_cost) + (estimated rows returned * cpu_tuple_cost)
= (114 * 1) + (10000 * 0.01) = 114 + 100.00 = 214.00
```

<mark style="background: #69E772;">Some other parameters (default value):</mark>
- ``random_page_cost``  (4) = estimate of the cost of a non-sequentially fetched disk page
- ``cpu_operator_cost`` (0.025) = estimate of the cost of processing each operator or function call
- ``cpu_index_tuple_cost``  (0.005) =  estimate of the cost of processing each index entry during an index scan

```plSQL
explain analyze select * from persons; 

Index Scan Backward using per_index on persons  (cost=0.29..387.29 rows=10000 width=60)
  Buffers: shared hit=171
```

<mark style="background: #69E772;">Total cost:</mark>
- 171 pages read => 171 * 1 = 171 (cost for scan the table)
- 10000 rows in the index => 10000 * 0.05 = 500
- 32 * 1 + 200 * 0.05 + 2000 * 0.01 =32+20+10 = 62

### <mark style="background: #69E772;">Cost of Query:</mark>

![](https://i.imgur.com/IsiVKhD.png)

There is an index on the ``unique1`` field

The second query has a higher cost even if it filters the row, why?

The third query creates a bitmap index, more info next slide…

### <mark style="background: #69E772;">Bitmap Index:</mark>

In order to improve query performance, Postgres might decide to create a bitmap index in memory.

The bitmap of pages is created dynamically for each query. It is not cached or re-used, and it is discarded at the end of the bitmap index scan.

For every row, a set of bit is added to store the location of the data

What is "Recheck condition" and why is it needed?

If the bitmap gets too large we convert it to "lossy" style, in which we only remember which pages contain matching tuples instead of remembering each tuple individually (the index is no more by row but by page). When that happens, the table-visiting phase has to examine each tuple on the page and recheck the scan condition to see which tuples to return.  (Tom Lane)

A bitmap index scan becomes lossy if ``work_mem`` is not big enough to contain a bitmap that contains one bit per table row. 

# <mark style="background: #69E772;">06 Transactions and Concurrency:</mark>

### <mark style="background: #69E772;">Introduction to Transaction Processing:</mark>

<mark style="background: #69E772;">Single-User System:</mark> At most, one user at a time can use the system. 

<mark style="background: #69E772;">Multi-user System:</mark> Many users can access the system concurrently.

<mark style="background: #69E772;">Concurrency:</mark>
- <mark style="background: #69E772;">Interleaved processing:</mark> concurrent execution of processes is interleaved in a single CPU
- <mark style="background: #69E772;">Parallel processing:</mark> processes are concurrently executed in multiple CPUs. 

### <mark style="background: #69E772;">Transactions:</mark>

A transaction (or logical unit of work) is a sequence of SQL statements that postgreSQL treats as a single unit.
 
<mark style="background: #69E772;">A transaction ends with a</mark> 
- commit, 
- rollback , 
- any DDL statement which issues an implicit commit. 

### <mark style="background: #69E772;">More on Transaction Processing:</mark>

A <mark style="background: #69E772;">Transaction</mark> includes one or more access operations (read -retrieval, write - insert or update, delete).

A <mark style="background: #69E772;">transaction (set of operations)</mark> may be stand-alone specified in a high level language like SQL submitted interactively, or may be embedded within a program.

<mark style="background: #69E772;">Transaction boundaries:</mark> Begin and End transaction.

An <mark style="background: #69E772;">application program</mark> may contain several transactions  separated by the Begin and End transaction boundaries. 

<mark style="background: #69E772;">SIMPLE MODEL OF A DATABASE (for purposes of discussing transactions):</mark>

<mark style="background: #69E772;">A database</mark> - collection of named data items

<mark style="background: #69E772;">Granularity of data</mark> - a field, a record , or a whole disk block (Concepts are independent of granularity)

<mark style="background: #69E772;">Basic operations are read and write</mark>
- <mark style="background: #69E772;">read_item(X):</mark> Reads a database item named X into a program variable. To simplify our notation, we assume that the program variable is also named X.
- <mark style="background: #69E772;">write_item(X):</mark> Writes the value of program variable X into the database item named X.

### <mark style="background: #69E772;">Two sample transactions T1 and T2:</mark>

![](https://i.imgur.com/0JXmWkI.png)

### <mark style="background: #69E772;">Why Concurrency Control is needed:</mark>

<mark style="background: #69E772;">The Lost Update Problem:</mark> This occurs when two transactions that access the same database items have their operations interleaved in a way that makes the value of some database item incorrect.

<mark style="background: #69E772;">The Temporary Update (or Dirty Read) Problem:</mark> This occurs when one transaction updates a database item and then the transaction fails for some reason. The updated item is accessed by another transaction before it is changed back to its original value.

<mark style="background: #69E772;">The Incorrect Summary Problem:</mark> If one transaction is calculating an aggregate summary function on a number of records while other transactions are updating some of these records, the aggregate function may calculate some values before they are updated and others after they are updated. 

### <mark style="background: #69E772;">Lost Update problem:</mark>

![](https://i.imgur.com/vDkdKlg.png)

### <mark style="background: #69E772;">The temporary update problem:</mark>

![](https://i.imgur.com/UOGe6tZ.png)

### <mark style="background: #69E772;">The incorrect summary problem:</mark>

![](https://i.imgur.com/YL4QSUy.png)

### <mark style="background: #69E772;">Concurrency Control:</mark>

<mark style="background: #69E772;">Properties of a transaction:</mark>
- ATOMICITY
- CONSISTENCY
- ISOLATION
- DURABILITY

![](https://i.imgur.com/51LGvh4.png)

### <mark style="background: #69E772;">A.C.I.D. properties:</mark>

<mark style="background: #69E772;">Atomicity:</mark> the is the “all or nothing” property ; a transaction is an indivisible unit of work

<mark style="background: #69E772;">Consistency:</mark> transactions transform the DB from one consistent state to another consistent state

<mark style="background: #69E772;">Isolation:</mark> transactions execute in isolation i.e. the partial effect of one transaction is not visible to other transactions.

<mark style="background: #69E772;">Durability (aka Persistence):</mark> the effect of a successfully completed (i.e. committed) transaction are permanently recorded in the DB and cannot be undone. 

### <mark style="background: #69E772;">Transactions Manager:</mark>

The transaction manager enforces the ACID properties 
- It schedules the operations of transactions • COMMIT and ROLLBACK are used to ensure atomicity 
- Locks or timestamps are used to ensure consistency and isolation for concurrent transactions 
- A log is kept to ensure durability in the event of system failure and make the system recoverable

### <mark style="background: #69E772;">Transaction and System Concepts:</mark>

A <mark style="background: #69E772;">transaction</mark> is an atomic unit of work that is either completed in its entirety or not done at all. For recovery purposes, the system needs to keep track of when the transaction starts, terminates, and commits or aborts.

<mark style="background: #69E772;">Transaction states:</mark>
- Active state
- Partially committed state
- Committed state
- Failed state
- Terminated State 

### <mark style="background: #69E772;">State diagram illustrating the states for transaction execution.</mark>

![](https://i.imgur.com/FRiGcps.png)

### <mark style="background: #69E772;">Making changes persist:</mark>

When data is changed, it must be persisted, to ensure that the change takes.

<mark style="background: #69E772;">E.g. a text editor:</mark>
- ``SAVE`` will ``COMMIT`` your changes.
- ``QUIT`` will ``ROLLBACK`` your changes.

<mark style="background: #69E772;">AUTOCOMMIT:</mark>
- When this feature is ON, changes are persisted as soon as they happen.
- Similar to Google Docs.

### <mark style="background: #69E772;">The transaction control commands:</mark>

<mark style="background: #69E772;">commit</mark> makes all changes since the beginning of a transaction permanent 

<mark style="background: #69E772;">rollback</mark> rolls back (undoes) all changes since the beginning of a transaction.

<mark style="background: #69E772;">Other users:</mark> 
- cannot see the results of the transaction until it has been committed.
- Can see the data as it was before the other user's transaction started!

### <mark style="background: #69E772;">AUTOCOMMIT, COMMIT and ROLLBACK:</mark>

Many modern database clients set autocommit on by default.

![](https://i.imgur.com/ufIuzwk.png)

### <mark style="background: #69E772;">Implicit and explicit transactions:</mark>

<mark style="background: #69E772;">In autocommit mode:</mark>
- Every SQL statement is considered to be a transaction
- It has an implicit ``BEGIN`` before it.
- It has an implicit ``COMMIT`` after it.

![](https://i.imgur.com/Fgzm0n8.png)

### <mark style="background: #69E772;">Why recovery is needed:</mark> 

<mark style="background: #69E772;">What causes a Transaction to fail:</mark>
1. <mark style="background: #69E772;">A computer failure (system crash):</mark> A hardware or  software error occurs in the computer system during transaction execution. If the hardware crashes, the contents of the computer’s internal memory may be lost.
2. <mark style="background: #69E772;">A transaction or system error:</mark> Some operation in the transaction may cause it to fail, such as integer overflow or division by zero. Transaction failure may also occur because of erroneous parameter values or because of a logical programming error. In addition, the user may interrupt the transaction during its execution.
3. <mark style="background: #69E772;">Local errors or exception conditions</mark> detected by the transaction: 
	- certain conditions necessitate cancellation of the transaction. For example, data for the transaction may not be found. A condition, such as insufficient account balance in a banking database, may cause a transaction, such as a fund withdrawal from that account, to be cancelled. 
	- a programmed abort in the transaction causes it to fail.
4. <mark style="background: #69E772;">Concurrency control enforcement:</mark> The concurrency control method may decide to abort the transaction, to be restarted later, because it violates serializability or because several transactions are in a state of deadlock
5. <mark style="background: #69E772;">Disk failure:</mark> Some disk blocks may lose their data because of a read or write malfunction or because of a disk read/write head crash. This may happen during a read or a write operation of the transaction. 
6. <mark style="background: #69E772;">Physical problems and catastrophes:</mark> This refers to an endless list of problems that includes power or air-conditioning failure, fire, theft, sabotage, overwriting disks or tapes by mistake, and mounting of a wrong tape by the operator. 

<mark style="background: #69E772;">Recovery techniques use the following operators:</mark>
- <mark style="background: #69E772;">undo:</mark> Similar to rollback except that it applies to a single operation rather than to a whole transaction.
- <mark style="background: #69E772;">redo:</mark> This specifies that certain <mark style="background: #69E772;">transaction operations</mark> must be <mark style="background: #69E772;">redone</mark> to ensure that all the operations of a committed transaction have been applied successfully to the database. 

### <mark style="background: #69E772;">The System Log:</mark>

<mark style="background: #69E772;">Log or Journal:</mark> The log keeps track of all transaction operations that affect the values of database items. This information may be needed to permit recovery from transaction failures. The log is kept on disk, so it is not affected by any type of failure except for disk or catastrophic failure. In addition, the log is periodically backed up to archival storage (tape) to guard against such catastrophic failures.  

T in the following discussion refers to a unique <mark style="background: #69E772;">transaction-id</mark> that is generated automatically by the system and is used to identify each transaction: 

<mark style="background: #69E772;">Types of log record:</mark> 
- ``[start_transaction,T]:`` Records that transaction T has started execution.
- ``[write_item,T,X,old_value,new_value]:`` Records that transaction T has changed the value of database item X from ``old_value`` to ``new_value``.
- ``[read_item,T,X]:`` Records that transaction T  has read the value of database item X.
- ``[commit,T]:`` Records that transaction T has completed successfully, and affirms that its effect can be committed (recorded permanently) to the database.
- ``[abort,T]:`` Records that transaction T has been aborted. 

### <mark style="background: #69E772;">Recovery using log records:</mark>

If the system crashes, we can recover to a consistent database state by examining the log

Because the log contains a record of every write operation that changes the value of some database item, it is possible to <mark style="background: #69E772;">undo</mark> the effect of these write operations of a transaction T by tracing backward through the log and resetting all items changed by a write operation of T to their ``old_values``.

We can also <mark style="background: #69E772;">redo</mark> the effect of the write operations of a transaction T by tracing forward through the log and setting all items changed by a write operation of T (that did not get done permanently) to their ``new_values``.   

### <mark style="background: #69E772;">Logs: the Transaction Schedule:</mark>

<mark style="background: #69E772;">Transaction schedule:</mark> When transactions are executing concurrently in an interleaved fashion, the order of execution of operations from the various transactions forms a transaction schedule. 

A <mark style="background: #69E772;">schedule</mark> (or <mark style="background: #69E772;">history</mark>) S of n transactions T1, T2, ..., Tn: It is an ordering of the operations of the transactions subject to the constraint that, for each transaction Ti that participates in S, the operations of T1 in S must appear in the same order in which they occur in T1. Note, however, that operations from other transactions Tj can be interleaved with the operations of Ti in S. 

Two operations are <mark style="background: #69E772;">conflicting</mark> if the belongs to 2 active transactions and at least one of the 2 is a write and they use the same data item.

![](https://i.imgur.com/iYAteB5.png)

### <mark style="background: #69E772;">Characterising Schedules based on recoverability:</mark>

<mark style="background: #69E772;">Recoverable schedule:</mark> One where no transaction needs to be rolled back. 
 
 A schedule S is <mark style="background: #69E772;">recoverable</mark> if no transaction T in S commits until all transactions T’ that have written an item that T reads have committed. Still cascading rollback of uncommitted transactions possible!

<mark style="background: #69E772;">Cascadeless schedule:</mark> One where every transaction reads only  the items that are written by committed transactions.

<mark style="background: #69E772;">Schedules requiring cascaded rollback:</mark> A schedule in which uncommitted transactions that read an item from a failed transaction must be rolled back. 

<mark style="background: #69E772;">Strict Schedules:</mark> A schedule in which a transaction can neither read or write an item X until the last transaction that wrote X has committed. 

<mark style="background: #69E772;">Serial schedule:</mark> A schedule S is <mark style="background: #69E772;">serial</mark> if, for every transaction T participating in the schedule, all the operations of T are executed consecutively in the schedule. Otherwise, the schedule is called non-serial schedule.

<mark style="background: #69E772;">Serialisable schedule:</mark> A schedule S is <mark style="background: #69E772;">serialisable</mark> if it is equivalent to some serial schedule of the same n transactions
 
<mark style="background: #69E772;">Being serialisable implies that the schedule is a correct schedule:</mark>
- It will leave the database in a consistent state. 
- The interleaving is appropriate and will result in a state as if the transactions were serially executed, yet will achieve efficiency due to concurrent execution. 

Being serialisable is not the same as being serial

<mark style="background: #69E772;">conflict – serialisable:</mark> A schedule is conflict – serialisable if by swapping non conflicting operations a serial schedule can be obtained

### <mark style="background: #69E772;">Schedule examples:</mark>

![](https://i.imgur.com/nh5kQ4p.png)

### <mark style="background: #69E772;">Database Concurrency Control:</mark>

<mark style="background: #69E772;">Why Concurrency Control is needed:</mark>
- The Lost Update Problem.
- The Temporary Update (or Dirty Read) Problem.
- The Incorrect Summary Problem.

<mark style="background: #69E772;">Purpose of Concurrency Control:</mark>
- To enforce Isolation (through mutual exclusion) among conflicting transactions. 
- To preserve database consistency through consistency preserving execution of transactions.
- To resolve read-write and write-write conflicts.

<mark style="background: #69E772;">Example:</mark>  In concurrent execution environment if T1 conflicts with T2 over a data item A, then the existing concurrency control decides if T1 or T2 should get the A and if the other transaction should wait.

### <mark style="background: #69E772;">Concurrency control is based on locks:</mark>

<mark style="background: #69E772;">Locking:</mark> 
- allows a user to take hold of a block for updating.
- Prevents other users from modifying the same data. 
- Locks can create performance problems.
- When one process locks, others are shut out. 
- There are several levels of locking.

<mark style="background: #69E772;">When modifying:</mark> 
- The transaction should place a lock until committed or rolled back. 
- This is known as data concurrency.

### <mark style="background: #69E772;">Transactions and Locking:</mark>

<mark style="background: #69E772;">Transactions start with BEGIN</mark>
- When an ``INSERT``, ``UPDATE`` or ``DELETE``  takes place:
- It locks the row that is being ``INSERTed`` / ``UPDATEd`` / ``DELETEd``. Other sessions cannot see the changes that are being made.

<mark style="background: #69E772;">The lock holds until the transaction session is finished by issuing:</mark>
- ``COMMIT`` or
- ``ROLLBACK``

### <mark style="background: #69E772;">Exclusive locks:</mark>

<mark style="background: #69E772;">Exclusive locks occur on ROWS when:</mark>
- The row is ``INSERTed``
- The row is ``DELETEd``
- The row is ``UPDATEd``
- The row is ``SELECTed``... FOR UPDATE...

### <mark style="background: #69E772;">Locking rows:</mark>

![](https://i.imgur.com/YITpjM5.png)


### <mark style="background: #69E772;">Locking Techniques: Binary Locking Scheme</mark>

A binary lock can have two states or values: locked (1) or unlocked (0)

If the value of the lock on item X is 1, item X cannot be accessed by a database operation that requests X.

If the value of the lock on item X is 0, item X can be accessed when requested.

The current value of the lock on item X is referred to as LOCK(X).

Binary locks are kept in a lock table which contains records where each record contains three fields:

``<DB Item, LOCK, Locking Transaction>``

Only items that are locked are kept in the table. Items that are not in the table are considered to be unlocked.

<mark style="background: #69E772;">The following code performs the lock operation:</mark>
```
lock-item(X):
B:	if LOCK (X) = 0 (*item is unlocked*)
	then LOCK (X)  1 (*lock the item*)
	else begin
		wait (until lock (X) = 0 and the lock manager 		wakes up the transaction);
	goto B
	end;
```

<mark style="background: #69E772;">The following code performs the unlock operation:</mark>
```
unlock-item(X):
LOCK (X)  0 (*unlock the item*)
if any transactions are waiting then wake up one of the waiting the transactions;
```

### <mark style="background: #69E772;">Locking Techniques: Essential components</mark>

<mark style="background: #69E772;">To use the binary locking scheme, every transaction must obey the following rules:</mark>
- A transaction T must issue the operation ``lock_item(X)`` before any ``read_item(X)`` or ``write_item(X)`` operations are performed in T.
- A transaction T must issue the operation ``unlock_item(X)`` after all ``read_item(X)`` or ``write_item(X)`` operations are completed in T.
- A transaction T will not issue a lock_item(X) operation if it already holds the lock on item X.
- A transaction T will not issue a unlock_item(X) unless it already holds the lock on item X.

### <mark style="background: #69E772;">Shared/Exclusive Locking Scheme:</mark>

<mark style="background: #69E772;">Two locks modes (a) shared (read) and (b) exclusive (write).</mark>
- <mark style="background: #69E772;">Shared mode:</mark> shared lock (X).  More than one transaction can apply shared lock on X for reading its value but no write lock can be applied on X by any other transaction.
- <mark style="background: #69E772;">Exclusive mode:</mark> Write lock (X).  Only one write lock on X can exist at any time and no shared lock can be applied by any other transaction on X.

``LOCK(X)`` has now 3 states: “``read_locked``”, “``write_locked``” or “``unlocked``”.

<mark style="background: #69E772;">Conflict matrix:</mark>
![](https://i.imgur.com/zX7YS7T.png)

<mark style="background: #69E772;">Locking Techniques:</mark> Shared/Exclusive Lock Operations

<mark style="background: #69E772;">The following code performs the read lock operation:</mark>
```
read_lock(X):
	B: if LOCK (X) = “unlocked” then
begin LOCK (X)  “read-locked”;
	no_of_reads (X)  1;
end
else if LOCK (X)  “read-locked” then
	      no_of_reads (X)  no_of_reads (X) +1
	  else begin wait (until LOCK (X) = “unlocked” and
		   the lock manager wakes up the transaction);
		   go to B
end;
```

<mark style="background: #69E772;">The following code performs the write lock operation:</mark>
```
write_lock(X):
    B: if LOCK (X) = “unlocked” then
LOCK (X)  “write-locked”;
else  begin 
         wait (until LOCK (X) = “unlocked” and
		   the lock manager wakes up the transaction);
        go to B
end;
```

<mark style="background: #69E772;">The following code performs the unlock operation:</mark>
```
unlock(X):
	if LOCK (X) = “write-locked” then
begin LOCK (X)  “unlocked”;
	 wakeup one of the transactions, if any
end
else if LOCK (X)  “read-locked” then
	begin
	      no_of_reads (X)  no_of_reads (X) -1
	      if  no_of_reads (X) = 0 then 		  
	      begin
		 LOCK (X) = “unlocked”;
		wakeup one of the transactions, if any
	      end
	end;
```

### <mark style="background: #69E772;">Lock conversion:</mark>

<mark style="background: #69E772;">Lock upgrade: existing read lock to write lock</mark>
```
if Ti has a read-lock (X) and Tj has no read-lock (X) (i  j) then
	     convert read-lock (X) to write-lock (X)
    else
	    force Ti to wait until Tj unlocks X

```

<mark style="background: #69E772;">Lock downgrade: existing write lock to read lock</mark>
```
Ti has a write-lock (X)    (*no transaction can have any lock on X*)
	     convert write-lock (X) to read-lock (X)

```

![](https://i.imgur.com/4XkR0Ax.png)

![](https://i.imgur.com/SALmRZg.png)

### <mark style="background: #69E772;">Two-Phase Locking Techniques - The algorithm:</mark>

<mark style="background: #69E772;">Two Phases:  (a) Locking (Growing) (b) Unlocking (Shrinking).</mark>
- <mark style="background: #69E772;">Locking (Growing) Phase:</mark> A transaction applies locks (read or write) on desired data items one at a time.
- <mark style="background: #69E772;">Unlocking (Shrinking) Phase:</mark> A transaction unlocks its locked data items one at a time.
- <mark style="background: #69E772;">Requirement:</mark> For a transaction these two phases must be mutually exclusively, that is, during locking phase unlocking phase must not start and during unlocking phase locking phase must not begin.

![](https://i.imgur.com/mqTwdGi.png)

### <mark style="background: #69E772;">Deadlock:</mark>

A deadlock can occur when two or more users are waiting for data locked by each other. 

Deadlocks prevent some transactions from continuing to work. 

The next example illustrates two transactions in a deadlock.

### <mark style="background: #69E772;">Dealing with Deadlock and Starvation:</mark>
![](https://i.imgur.com/2k66wP7.png)

### <mark style="background: #69E772;">A second Example:</mark>
![](https://i.imgur.com/VbWwxRt.png)

### <mark style="background: #69E772;">Example Explanation:</mark>

<mark style="background: #69E772;">At timepoint A:</mark>
- no problem exists as each transaction has a row lock on the row it attempts to update.
- Each transaction proceeds without being terminated.
- However, each tries next to update the row currently held by the other transaction. 

<mark style="background: #69E772;">At timepoint B:</mark>
- a deadlock results, because neither transaction can obtain the resource it needs to proceed or terminate. 
- It is a deadlock because no matter how long each transaction waits, the conflicting locks are held.

### <mark style="background: #69E772;">Deadlock Prevention:</mark>

A transaction locks all data items it refers to before it begins execution. This way of locking prevents deadlock since a transaction never waits for a data item. The conservative two-phase locking uses this approach.

Other deadlock prevention algorithms use the concept of a timestamp TS(T) which is a unique identifier assigned to transactions based on the order in which they start. If T1 starts before T2, then TS(T1) < TS(T2) (older transaction has the smaller timestamp value)  

<mark style="background: #69E772;">Examples of such algorithms are:</mark>       
- <mark style="background: #69E772;">Wait-die:</mark> If TS(Ti) < TS(Tj), then (Ti is older than Tj) Ti is allowed to wait; otherwise (Ti younger than Tj) abort Ti (Ti dies) and restart it later with the same timestamp.
- <mark style="background: #69E772;">Wound-wait:</mark> If TS(Ti) < TS(Tj), then (Ti is older than Tj) abort Tj (Ti wounds Tj) and restart it later with the same timestamp; otherwise (Ti younger than Tj) Ti is allowed to wait.

### <mark style="background: #69E772;">Deadlock Detection and Resolution:</mark>

In this approach, deadlocks are allowed to happen. The scheduler maintains a wait-for-graph for detecting cycle. If a cycle exists, then one transaction involved in the cycle is selected (victim) and rolled-back.

Another approach to deal with deadlock is the use of timeouts. In this method, if a transaction waits for a period of time longer than a system-defined timeout period, the system assumes that a transaction maybe in s state of deadlock and aborts it regardless of whether a deadlock actually exists or not.

### <mark style="background: #69E772;">Starvation:</mark>

Starvation occurs when a particular transaction consistently waits or restarted and never gets a chance to proceed further. 

In a deadlock resolution it is possible that the same transaction may consistently be selected as victim and aborted. 

This limitation is inherent in all priority based scheduling mechanisms.  

In Wound-Wait scheme a younger transaction may always be wounded (aborted) by a long running older transaction which may create starvation.

# <mark style="background: #69E772;">07 NoSQL:</mark>

### <mark style="background: #69E772;">SQL Characteristics:</mark>
- Data stored in columns and tables  
- Relationships represented by data  
- Data Manipulation Language  
- Data Definition Language  
- Transactions (ACID)  
- Abstraction from physical layer

### <mark style="background: #69E772;">Data Manipulation Language (DML):</mark>

Data manipulated with Select, Insert, Update, & Delete statements  
```SQL
Select T1.Column1, T2.Column2 ...  
From Table1, Table2 ...  
Where T1.Column1 = T2.Column1 ... 
``` 

Data Aggregation  

Functions and Procedures  

Explicit transaction control

### <mark style="background: #69E772;">Data Definition Language (DDL):</mark>

Schema defined at the start  

```SQL
Create Table (Column1 Datatype1, Column2 Datatype 2, ...)
```  

<mark style="background: #69E772;">Constraints to define and enforce relationships:</mark>
- Primary Key  
- Foreign Key  
- Etc.  

Triggers to respond to Insert, Update , & Delete  

Stored Modules  

Alter ...  

Drop ...  

Security and Access Control

### <mark style="background: #69E772;">NO SQL.. Why?</mark>

Web-based applications caused spikes. Especially true for public-facing e-Commerce sites  

Internet, distributed data, big data...  

Developers begin to front RDBMS with memcache or integrate other caching mechanisms within the application

### <mark style="background: #69E772;">Scaling up:</mark>

Issues with scaling up when the dataset is just too big  

RDBMS were not designed to be distributed  

Began to look at multi-node database solutions  

Known as ‘scaling out’ or ‘horizontal scaling’  

<mark style="background: #69E772;">Different approaches include:</mark>
- Master-slave  
- Sharding

### <mark style="background: #69E772;">Master/Slave</mark>

All writes are written to the master. All reads performed against the replicated slave databases  

Critical reads may be incorrect as writes may not have been propagated down  

Large data sets can pose problems as master needs to duplicate data to slaves

### <mark style="background: #69E772;">Partition or sharding:</mark>

Scales well for both reads and writes  

Not transparent, application needs to be partition-aware  

Can no longer have relationships/joins across partitions  

Loss of referential integrity across shards

### <mark style="background: #69E772;">Other ways to scale RDBMS:</mark>

No JOINs, thereby reducing query time. This involves de-normalizing data.  

In-memory databases  

NO SQL started with the aim to address the scaling problem

### <mark style="background: #69E772;">NoSQL Definition:</mark>

A Generation of Databases mostly addressing some of the points: being <mark style="background: #69E772;">non-relational</mark>, <mark style="background: #69E772;">distributed</mark>, <mark style="background: #69E772;">open-source</mark> and <mark style="background: #69E772;">horizontal scalable</mark>. 

The original intention has been <mark style="background: #69E772;">modern web-scale databases</mark>.

The movement began early 2009 and is growing rapidly.

<mark style="background: #69E772;">Often more characteristics apply as:</mark> 
- schema-free, 
- easy replication support, 
- simple API, 
- eventually consistent / BASE (not ACID), 
- a huge data amount, and more.

### <mark style="background: #69E772;">What is NoSQL?</mark>

Stands for <mark style="background: #69E772;">Not Only SQL</mark>  

Class of non-relational data storage systems  

<mark style="background: #69E772;">Class of data management systems inherently:</mark>
- Non-relational  
- Distributed  
- Horizontally scalable  
- With optional schemas  
- Providing simple APIs  

All NoSQL relax one or more of the ACID properties. But some of them can also do ACID!

### <mark style="background: #69E772;">NoSQL distinguishing characteristics:</mark> 
- Large data volumes - “big data”  
- Scalable replication and distribution, Potentially thousands of machines, Potentially distributed around the world  
- Queries need to return answers quickly  
- Mostly query, few updates  
- Asynchronous Inserts & Updates  
- Schema-less  
- ACID transaction properties are not needed – BASE  
- CAP Theorem
- Open source development

### <mark style="background: #69E772;">CAP THEOREM:</mark>

![](https://i.imgur.com/ixQfptR.png)

<mark style="background: #69E772;">C - Consistency:</mark>
- This is a given in a relational database
- If a RDBMS is not in a consistent state, it is not available.
- Remember what happens when two sessions are accessing the same data - only the consistent data is available to both.
- all nodes should see the same data at the same time

<mark style="background: #69E772;">A - Availability:</mark>
- A MongoDB database will always have data available because it has replicas of every piece of data and it only promises "eventual consistency"
- node failures do not prevent survivors continuing to operate

<mark style="background: #69E772;">P - Partition tolerance (tolerating network breaks):</mark>
- In a distributed situation, RDBMS will not allow a transaction to go through unless all nodes involved are in a consistent state.
- In a distributed situation, MongoDB will go ahead with transactions for available nodes and let the others catch up later.
- the system continues to operate despite arbitrary message loss, No set of failures less than total network failure is allowed to cause the system to respond incorrectly.

<mark style="background: #69E772;">It is impossible for a distributed systems to provide all of the above features</mark>

### <mark style="background: #69E772;">2 Out of 3: BASE vs ACID:</mark>

<mark style="background: #69E772;">C+A:</mark>  
- Always available and consistent  
- Single site databases  
- Cluster Databases (why?)  

<mark style="background: #69E772;">C+P:</mark>  
- Distributed Databases  
- Minority Locking  
- System is unavailable for a while..  

<mark style="background: #69E772;">A+P:</mark>  
- DNS  

### <mark style="background: #69E772;">ACID properties of transactions:</mark>

<mark style="background: #69E772;">Basic (ACID) properties of a transaction are:</mark>  
1. <mark style="background: #69E772;">Atomicity</mark> ‘All or nothing’ property.  
2. <mark style="background: #69E772;">Consistency</mark> Must transform database from one consistent state to another.  
3. <mark style="background: #69E772;">Isolation</mark> Partial effects of incomplete transactions should not be visible to other transactions.  
4. <mark style="background: #69E772;">Durability</mark> Effects of a committed transaction are permanent and must not be lost because of later failure.

### <mark style="background: #69E772;">BASE Transactions:</mark>

<mark style="background: #69E772;">Acronym contrived to be the opposite of ACID</mark>  
- <mark style="background: #69E772;">B</mark>asically <mark style="background: #69E772;">A</mark>vailable,  
- <mark style="background: #69E772;">S</mark>oft state,  
- <mark style="background: #69E772;">E</mark>ventually consistent  

<mark style="background: #69E772;">Characteristics:</mark>  
- Weak consistency – stale data OK  
- Availability first  
- Best effort  
- Approximate answers OK  
- Simpler and faster

### <mark style="background: #69E772;">BASE:</mark>

When no updates occur for a long period of time, eventually all updates will propagate through the system and all the nodes will be consistent  

For a given accepted update and a given node, eventually either the update reaches the node or the node is removed from service  

Known as <mark style="background: #69E772;">BASE</mark> (Basically Available, Soft state, Eventual consistency), as opposed to ACID

### <mark style="background: #69E772;">What am I giving up using NoSQL?</mark>
- joins  
- group by  
- order by  
- ACID transactions  
- SQL as a sometimes frustrating but still powerful query language  
- easy integration with other applications that support SQL

### <mark style="background: #69E772;">Advantages of NoSQL:</mark>
- Cheap, easy to implement  
- Data are replicated and can be partitioned  
- Easy to distribute  
- Don't require a schema  
- Can scale up and down  
- Quickly process large amounts of data  
- Relax the data consistency requirement (CAP)  
- Can handle web-scale data, whereas Relational DBs cannot
- Simple APIs  
- Java Example: Document.save(myObject)  
- Good integration  
- Designed to be horizontally scalable (elastic)  
- Flexible data model  
- Majority free and/or Open Source 
- Free and Commercial production support

### <mark style="background: #69E772;">RDBMS Advantages:</mark>
- Proven  
- Available talent / Well-known  
- AD-Hoc querying  
- Scalable (limits?)  
- Free and Commercial production support

### <mark style="background: #69E772;">Disadvantages of NoSQL:</mark>

Data is generally duplicated, potential for inconsistency  

<mark style="background: #69E772;">No standard:</mark>
- schema  
- format for queries  
- language  

Difficult to impose complicated structures  

Depend on the application layer to enforce data integrity  

No guarantee of support  

Too many options, which one, or ones to pick

### <mark style="background: #69E772;">Where would I use a NoSQL database?</mark>

Do you have somewhere a large set of uncontrolled, unstructured, data that you are trying to fit into a RDBMS?  
- Log Analysis  
- Social Networking Feeds  
- Data that is not easily analysed in a RDBMS such as time-based data  
- Large data feeds that need to be massaged before entry into an RDBMS  
- Data that are is relational (like graph-like data?)

### <mark style="background: #69E772;">Hybrid approach: Polyglot Persistence</mark>

Using different DB technologies for different storage requirements

![](https://i.imgur.com/3zR6pbY.png)

![](https://i.imgur.com/jXQpu3J.png)

### <mark style="background: #69E772;">Schemaless data with Postgres:</mark>

Explore the boundaries between SQL and NoSQL databases  

Know a little bit more about postgres

<mark style="background: #69E772;">SQL:</mark>  
- Relational model  
- Normalise data as much as possible  
- Row in a table have the same schema

<mark style="background: #69E772;">NoSQL:</mark>  
- Document-oriented database  
- Data semi structured  
- No schema enforced over documents  
- Metadata attached to documents

### <mark style="background: #69E772;">First schemaless data: Hstore:</mark>

Key-Value data structure  

GiST and GIN index support for some operators  

Used in rows with many attributes that are rarely examined

```
"name"=>"michele"  
"surname"=>"capra"  
"age"=> 18  
"city"=>"Brescia"  
"state"=>"Italy"
```

[HStore Demo](https://github.com/piccoloaiutante/schemaless-postgres/hstore)

### <mark style="background: #69E772;">JSON data:</mark>

Javascript Object Notation  

Two type of field json/jsonb  

<mark style="background: #69E772;">More flexible than hstore:</mark> 
- nesting, 
- data validation

Store the exact copy of the input  

Spaces and keys (even duplicated) order are preserved  

Reparse on each processing

### <mark style="background: #69E772;">JSONB:</mark>

Json parsed on insert and stored in binary format  

Keys order and spaces are lost  

When duplicated keys, only last value is saved  

Supports indexing

[JSON Demo](https://github.com/piccoloaiutante/schemaless-postgres/tree/master/json)

[Modelling Demo](https://github.com/piccoloaiutante/schemaless-postgres/blob/master/json/model.md)

### <mark style="background: #69E772;">Solution:</mark>

Leave data that we use for join into value type field.  

All the rest should go to ``jsonb`` data.

### <mark style="background: #69E772;">GIS:</mark>

Geographic information system  

Storing, manipulate, analyze location information.  

x,y,z axis -> longitude, latitude, elevation

### <mark style="background: #69E772;">Postgis:</mark>

Spatial database extender for postgres  

Add support for geographic object  

Support for location queries in SQL

### <mark style="background: #69E772;">Desktop tool</mark>

pgAdmin supports spatial data but not rendering  

QGIS favourite cross platform client  

You can get it from here http://qgis.org/en/site/

<mark style="background: #69E772;">OpenGIS Consortium for 2D data:</mark>  
- Two data format representation:  
- Well-Known Text (WKT)  
- Well-Known Binary (WKB)

### <mark style="background: #69E772;">Data type - Point:</mark>

A point in a Cartesian plane.

![](https://i.imgur.com/DJ7HHJR.png)

### <mark style="background: #69E772;">Data type - LineString:</mark>

A polygonal chain is a connected series of line segments

![](https://i.imgur.com/KWH1x93.png)

### <mark style="background: #69E772;">Data type - Polygon:</mark>

A plane figure that is bounded by a finite chain of straight line segments closing in a loop to form a closed polygonal chain or circuit

![](https://i.imgur.com/grkkgw0.png)

![](https://i.imgur.com/011n8bI.png)

![](https://i.imgur.com/zuUQUqK.png)

### <mark style="background: #69E772;">Data type - Multipoint:</mark>

A series of points

![](https://i.imgur.com/IC9ibKJ.png)

### <mark style="background: #69E772;">Data type – Multiline string:</mark>

A series of line strings

![](https://i.imgur.com/8h8NlFF.png)

### <mark style="background: #69E772;">Data type – Multi polygon:</mark>

A collection of polygon

![](https://i.imgur.com/Zfe28Ec.png)

### <mark style="background: #69E772;">Postgis data type:</mark>

<mark style="background: #69E772;">Geography:</mark>  
- ellipsoidal spatial data type (latitutde + longitude)  
- unit measure is meter  

<mark style="background: #69E772;">Geometry:</mark>  
- euclidean coordinate system  
- planar spatial data type

### <mark style="background: #69E772;">Dataset examples 1:</mark>

New York subway stations (point)
![](https://i.imgur.com/CAD4cvC.png)

New York streets (multiline)
![](https://i.imgur.com/ltYhqb3.png)

New York neighborhood (polygon)
![](https://i.imgur.com/7Fvb1f4.png)

### <mark style="background: #69E772;">POSTGIS:</mark>

[POSTGIS documentation](https://postgis.net/docs/reference.html#idm11151)

[POSTGIS demo](https://github.com/piccoloaiutante/schemaless-postgres/postgis)

### <mark style="background: #69E772;">Ltree data:</mark>

Labels of data stored in a hierarchical tree-like structure  

Support indexing

<mark style="background: #69E772;">Label:</mark> sequence of alphanumeric characters and underscores  

<mark style="background: #69E772;">Path:</mark> sequence of zero or more labels separated by dots  
Operators to manipulate labels and paths

[Ltree demo](https://github.com/piccoloaiutante/schemaless-postgres/ltree)

### <mark style="background: #69E772;">Example:</mark>

![](https://i.imgur.com/qaogNLk.png)

### <mark style="background: #69E772;">Recap:</mark>

<mark style="background: #69E772;">Schemaless data in postgres:</mark> 
- Hstore  
- Json/jsonb  
- Geography/geometry  
- Ltree  

<mark style="background: #69E772;">Old data type:</mark> array

# <mark style="background: #69E772;">08 MongoDB:</mark>

### <mark style="background: #69E772;">MongoDB profile:</mark>

Document-oriented NoSQL database.  

Schema-free.  

Based on Binary JSON; BSON.  

Organized in Group of Documents and Collections  

Auto-Sharding in order to scale horizontally.  

Simple query language. Rich, document-based queries.  

Map/Reduce support  

Open Source (GNU AGPL v3.0.)

### <mark style="background: #69E772;">Motivations:</mark>

<mark style="background: #69E772;">Problems with SQL:</mark>  
- Rigid schema  
- Not easily scalable (designed for 90’s technology or worse)  
- Requires unintuitive joins

<mark style="background: #69E772;">Benefits of mongoDB:</mark>  
- Easy interface with common languages (Java,   Javascript, PHP, etc.)  
- DB tech should run anywhere (VM’s, cloud, etc.)  
- Keeps essential features of RDBMS’s while learning from key-value noSQL systems

### <mark style="background: #69E772;">Data Model:</mark>

Document-Based  

Documents are in BSON format, consisting of field-value pairs  

Each document stored in a collection  

<mark style="background: #69E772;">Collections;</mark>  
- Have index set in common  
- Like tables of relational dbs.  
- Documents do not have to have uniform structure

### <mark style="background: #69E772;">JSON:</mark>

“JavaScript Object Notation”  

Easy for humans to write/read, easy for computers to parse/generate  

Objects can be nested  

<mark style="background: #69E772;">Built on:</mark>
- name/value pairs  
- Ordered list of values

### <mark style="background: #69E772;">BSON:</mark>

“Binary JSON”  

Binary-encoded serialization of JSON-like docs  

Also allows “referencing”  

Embedded structure reduces need for joins  

<mark style="background: #69E772;">Goals:</mark>  
- Lightweight  
- Traversable  
- Efficient (decoding and encoding

### <mark style="background: #69E772;">BSON Example:</mark>

```JSON
{  
	"_id" : "37010"  
	"city" : "ADAMS",  
	"pop" : 2660,  
	"state" : "TN",  
	"councilman" : {  
		name: "John Smith"  
		address: "13 Scenic Way"  
	}  
}
```

### <mark style="background: #69E772;">The _id Field:</mark>

By default, each document contains an ``_id`` field.  

<mark style="background: #69E772;">This field has a number of special  characteristics:</mark>  
- Value serves as primary key for collection.  
- Value is unique, immutable, and may be any non-array type.  
- Default data type is ``ObjectId``, which is “small, unique, fast to generate, and ordered.” Sorting on an ``ObjectId`` value is roughly equivalent to sorting on creation time.

``_id`` is a 12 bytes hexadecimal number which assures the uniqueness of every document.  

You can provide ``_id`` while inserting the document. If you don’t provide then MongoDB provides a unique id for every document.  

These 12 bytes first 4 bytes for the current timestamp, next 3 bytes for machine id, next 2 bytes for process id of MongoDB server and remaining 3 bytes are simple incremental VALUE.

### <mark style="background: #69E772;">mongoDB vs. SQL:</mark>

![](https://i.imgur.com/gaJmrf5.png)

### <mark style="background: #69E772;">Data type:</mark>

<mark style="background: #69E772;">String</mark> − This is the most commonly used datatype to store the data. String in MongoDB must be UTF-8 valid.  

<mark style="background: #69E772;">Integer</mark> − This type is used to store a numerical value. Integer can be 32 bit or 64 bit depending upon your server.  

<mark style="background: #69E772;">Boolean</mark> − This type is used to store a boolean (true/ false) value.  

<mark style="background: #69E772;">Double</mark> − This type is used to store floating point values.  

<mark style="background: #69E772;">Arrays</mark> − This type is used to store arrays or list or multiple values into one key.  

<mark style="background: #69E772;">Timestamp</mark> − ``ctimestamp``. This can be handy for recording when a document has been modified or added.  

<mark style="background: #69E772;">Object</mark> − This datatype is used for embedded documents.

### <mark style="background: #69E772;">Data Type</mark>

<mark style="background: #69E772;">Null</mark> − This type is used to store a Null value.  

<mark style="background: #69E772;">Symbol</mark> − This datatype is used identically to a string; however, it's generally reserved for languages that use a specific symbol type.  

<mark style="background: #69E772;">Date</mark> − This datatype is used to store the current date or time in UNIX time format. You can specify your own date time by creating object of Date and passing day, month, year into it.  

<mark style="background: #69E772;">Object ID</mark> − This datatype is used to store the document’s ID.  

<mark style="background: #69E772;">Binary data</mark> − This datatype is used to store binary data.  

<mark style="background: #69E772;">Code</mark> − This datatype is used to store JavaScript code into the document.  

<mark style="background: #69E772;">Regular expression</mark> − This datatype is used to store regular expression.

### <mark style="background: #69E772;">Basic operations:</mark>

![](https://i.imgur.com/t6iBn4u.png)

### <mark style="background: #69E772;">CRUD operations - create:</mark>

![](https://i.imgur.com/gsnczTa.png)

![](https://i.imgur.com/CaGLwYa.png)

![](https://i.imgur.com/dOPMsK1.png)

### <mark style="background: #69E772;">CRUD operations - read:</mark>

![](https://i.imgur.com/Aep3rKq.png)

### <mark style="background: #69E772;">Logical tests:</mark>

![](https://i.imgur.com/SbYXPkY.png)

### <mark style="background: #69E772;">Querying:</mark>

```SQL
db.<collection>.find({ $or: [  
<field>:<value1>  
<field>:<value2> ]  
})  
SELECT *  
FROM <table>  
WHERE <field> = <value1> OR <field> = <value2>;  
Alternative: checking for multiple values of same field  
db.<collection>.find({<field>: {$in [<value>, <value>]}})
```

### <mark style="background: #69E772;">CRUD operations - update:</mark>

![](https://i.imgur.com/IOe0L80.png)

### <mark style="background: #69E772;">CRUD operations - delete:</mark>

![](https://i.imgur.com/Rzx0TTw.png)

### <mark style="background: #69E772;">Schema Design:</mark>

<mark style="background: #69E772;">SQL vs Mongo Concepts:</mark>
![](https://i.imgur.com/rfgAdYs.png)

### <mark style="background: #69E772;">Mongo is basically schema-free:</mark>

The purpose of schema in SQL is for meeting the requirements of tables and SQL implementation.

Every “row” in a database “table” is a data structure, much like a “struct” in C, or a “class” in Java. A table is then an array (or list) of such data structures.

So what we design in mongoDB is basically same way how we design a compound data type binding in JSON.

### <mark style="background: #69E772;">There are some patterns:</mark>

<mark style="background: #69E772;">Embedding:</mark> 
- Embed the document into the other document  
- Similar to denormalised joins

<mark style="background: #69E772;">Linking (also known as reference):</mark>  
- Use the id of a document as a field in another document  
- similar to a FK in SQL

### <mark style="background: #69E772;">One to One relationship - embedding:</mark>

![](https://i.imgur.com/uXnJ4UF.png)

![](https://i.imgur.com/8u1uw9a.png)

### <mark style="background: #69E772;">One to many relationship –  Linking</mark>

![](https://i.imgur.com/gEJqwEc.png)

### <mark style="background: #69E772;">Linking vs. Embedding:</mark>

Embedding is a bit like pre-joining data  

Document level operations are easy for the server to handle  

Embed when the “many” objects always appear with (viewed in the context of) their parents.  

Linking when you need more flexibility, less redundancy. It is not the MongoDB way.

### <mark style="background: #69E772;">Modeling Checkouts:</mark>

```JSON
student = {  
	_id: "joe"  
	name: "Joe Bookreader",  
	join_date: ISODate("2011-10-15"),  
	address: { ... }  
}  
book = {  
	_id: "123456789"  
	title: "MongoDB: The Definitive Guide",  
	authors: [ "Kristina Chodorow", "Mike Dirolf" ],
	...
}
```

```JSON
student = {  
	_id: "joe"  
	name: "Joe Bookreader",  
	join_date: ISODate("2011-10-15"),  
	address: { ... },  
	checked_out: [  
	{ _id: "123456789", checked_out: "2012-10-15" },  
	{ _id: "987654321", checked_out: "2012-09-12" },  
	...  
	]  
}
```

### <mark style="background: #69E772;">Model Tree Structure:</mark>

![](https://i.imgur.com/ss0Y4JD.png)

```SQL
db.categories.insert( { _id: "MongoDB", parent: "Databases" } )  
db.categories.insert( { _id: "dbm", parent: "Databases" } )  
db.categories.insert( { _id: "Databases", parent: "Programming" } )  
db.categories.insert( { _id: "Languages", parent: "Programming" } )  
db.categories.insert( { _id: "Programming", parent: "Books" } )  
db.categories.insert( { _id: "Books", parent: null } )  
db.categories.findOne( { _id: "MongoDB" } ).parent  
db.categories.ensureIndex( { parent: 1 } )  
db.categories.find( { parent: "Databases" } )
```

### <mark style="background: #69E772;">Another Example:</mark>

Suppose a client needs a database design for his blog/website and see the differences between RDBMS and MongoDB schema design.  

<mark style="background: #69E772;">Website has the following requirements:</mark>  
- Every post has the unique title, description and url.  
- Every post can have one or more tags.  
- Every post has the name of its publisher and total number of likes.  
- Every post has comments given by users along with their name, message, data-time and likes.  
- On each post, there can be zero or more comments.

![](https://i.imgur.com/4AYsQHw.png)

### <mark style="background: #69E772;">MongoDB Document:</mark>

```JSON
{  
	_id: POST_ID  
	title: TITLE_OF_POST,  
	description: POST_DESCRIPTION,  
	by: POST_BY,  
	url: URL_OF_POST,  
	tags: [TAG1, TAG2, TAG3],  
	likes: TOTAL_LIKES,  
	comments: [  
		{  
			user:'COMMENT_BY',  
			message: TEXT,  
			dateCreated: DATE_TIME,  
			like: LIKES  
		},  
		{  
			user:'COMMENT_BY',  
			message: TEXT,  
			dateCreated: DATE_TIME,  
			like: LIKES  
		}  
	]  
}
```

### <mark style="background: #69E772;">Some considerations while designing Schema in MongoDB</mark>

Design your schema according to user requirements.  

Combine objects into one document if you will use them together. Otherwise separate them (but make sure there should not be need of joins).  

Duplicate the data (but limited) because disk space is cheap as compare to compute time.  

Do joins while write, not on read.  

Optimise your schema for most frequent use cases.  

Do complex aggregation in the schema.

### <mark style="background: #69E772;">Before Index:</mark>
 
 <mark style="background: #69E772;">What does a database normally do when we query?</mark>  
- MongoDB must scan <mark style="background: #69E772;">every</mark> document.  
- Inefficient because process <mark style="background: #69E772;">large volume</mark> of data

![](https://i.imgur.com/P1PL932.png)

### <mark style="background: #69E772;">Definition of Index:</mark>

Indexes are special data structures that store a small portion of the <mark style="background: #69E772;">collection’s</mark> data set in an easy to traverse form.

![](https://i.imgur.com/CJ9T74i.png)

### <mark style="background: #69E772;">Index in MongoDB:</mark>  

<mark style="background: #69E772;">Creation index:</mark>  ``db.users.createIndex( { score: 1 } )``  

<mark style="background: #69E772;">Show existing indexes:</mark> ``db.users.getIndexes()``  

<mark style="background: #69E772;">Drop index:</mark>  ``db.users.dropIndex( {score: 1}``

<mark style="background: #69E772;">Types:</mark>    
- Single Field Indexes
- Compound Field Indexes
- Multikey Indexes

<mark style="background: #69E772;">Single Field Indexes:</mark>  ``db.users. createIndex( { score: 1 } )``

![](https://i.imgur.com/885a68a.png)

<mark style="background: #69E772;">Compound Field Indexes:</mark>   ``db.users. createIndex( { userid:1, score: -1 } )``

![](https://i.imgur.com/SRzjtb7.png)

<mark style="background: #69E772;">Multikey Indexes:</mark>  ``db.users.createIndex( { addr.zip:1} )``

![](https://i.imgur.com/YItYx1r.png)

### <mark style="background: #69E772;">Aggregation:</mark>  

Operations that process data records and return computed results.  

MongoDB provides aggregation operations  

Running data aggregation on the mongod instance simplifies application code and limits resource requirements.  

<mark style="background: #69E772;">Aggregation can be done with:</mark>  
- Pipeline ($group operator)  
- ``Map_reduce``

### <mark style="background: #69E772;">Pipelines:</mark>

MongoDB’s <mark style="background: #69E772;">aggregation framework</mark> is modelled on the concept of data processing pipelines. Documents enter a multi-stage pipeline that transforms the documents into an aggregated result.  

The most basic pipeline stages provide <mark style="background: #69E772;">filters</mark> that operate like queries and <mark style="background: #69E772;">document transformations</mark> that modify the form of the output document.  

Other pipeline operations provide tools for grouping and sorting documents by specific field or fields as well as tools for aggregating the contents of arrays  

Pipeline stages can use <mark style="background: #69E772;">operators</mark> for tasks such as calculating the average or concatenating a string.  

Pipeline is the preferred method for data aggregation in MongoDB.

### <mark style="background: #69E772;">Aggregation using pipeline:</mark>

![](https://i.imgur.com/lmKakx0.png)

### <mark style="background: #69E772;">Some Aggregator Operators:</mark>

![](https://i.imgur.com/cPzxwN3.png)

### <mark style="background: #69E772;">$count // example</mark> 

```JSON
{ "_id" : 1, "subject" : "History", "score" : 88 }  
{ "_id" : 2, "subject" : "History", "score" : 92 }  
{ "_id" : 3, "subject" : "History", "score" : 97 }  
{ "_id" : 4, "subject" : "History", "score" : 71 }  
{ "_id" : 5, "subject" : "History", "score" : 79 }  
{ "_id" : 6, "subject" : "History", "score" : 83 }
``` 

```SQL
db.scores.aggregate(  
[  
{ $match: { score: { $gt: 80} } },  
{ $count: "passing_scores“ }  
])  
Output:  
{ "passing_scores" : 4 }
```

```SQL
db.test_db.find({gender: 'f'});  
db.test_db.find({gender: 'm'});  
db.test_db.find({gender: 'm', $or: [{nationality: 'english'}, {nationality:'american'}]});  
db.test_db.find({gender: 'm', $or: [{nationality: 'english'},{nationality: 'american'}]}).sort({nationality: -1});  
db.test_db.find({gender: 'm', $or: [{nationality: 'english'},{nationality: 'american'}]}).sort({nationality: -1, first: 1});  
db.test_db.find({gender: 'm', $or: [{nationality: 'english'},{nationality: 'american'}]}).limit(2);  
db.test_db.update({first: 'james', last: 'caan'}, {$set:{hair_colour: 'brown'}});  
db.test_db.update({ nationality: "american" },{ $inc: { age: 2} })  
db.test_db.aggregate( [ { $match: { 'age' : { '$gte' : 37 }}}, {$group: { _id: '$nationality', total : { $sum : 1} }}] );  
db.test_db.aggregate( [ { $match: { 'age' : { '$gte' : 37 }}}, {$group: { _id: '$gender', total : { $sum : 1} }}] );  
db.test_db.aggregate( [ {$group: { _id: '$gender', avg_age : { $avg : '$age'} }}] );
```

### <mark style="background: #69E772;">Documents Update:</mark>

MongoDB does not allow to update a field by using an expression containing other fields of the collection  

Therefore, you cannot write ``$field = $field + 1`` or something similar (as we did for SQL)  

For numeric update, use the ``$inc`` operator with update function  

Or.. JavaScript always an option!  

Example:  
```JSON
{ _id: 1, item: "abc123", quantity: 10, metrics: { orders: 2, ratings: 3.5 } }  

db.products.update( { item: "abc123" }, { $inc: { quantity: -2, "metrics.orders": 1 }})
```

### <mark style="background: #69E772;">Multiple Updates:</mark>

Add {multi: true). It controls the ability of mongoDB to update more than one field in a single query  

Try:  
```JSON
> db.pierpaolo.update({first: { $ne: "aa"} }, { $inc: {age : 2}})  

WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })  

db.pierpaolo.update({first: { $ne: "aa"} }, { $inc: {age : 2}},{multi: true})  
WriteResult({ "nMatched" : 7, "nUpserted" : 0,"nModified" : 7 })
```

### <mark style="background: #69E772;">Mongo & JavaScript:</mark>

You can store your commands in a js script and execute them with ``mongo js_file.js``

### <mark style="background: #69E772;">Shell – Script Commands:</mark>

![](https://i.imgur.com/uOutnWV.png)

### <mark style="background: #69E772;">Cursors:</mark>

```JavaScript
var myCursor = db.inventory.find( { type: 'food' } );  

while (myCursor.hasNext()) {  
	print(tojson(myCursor.next())); }  

myCursor.forEach(printjson);  

var documentArray = myCursor.toArray();  

var myDocument = documentArray[3];  
var myDocument = myCursor[3];
```

### <mark style="background: #69E772;">Map Reduce:</mark>

Algorithm (“template”) to perform distributed parallel computation  

Used in MongoDB for performing distributed queries, for instance aggregated queries  

MongoDB provides the function map-reduce  

Map reduce is a concept from functional programming

```JavaScript
map even [3,4,5,6,7,9] = [4,6]
```

<mark style="background: #69E772;">Has two phases:</mark>  
- A <mark style="background: #69E772;">map</mark> stage that processes each document and emits one or more objects for each input document  
- A <mark style="background: #69E772;">reduce</mark> phase that combines the output of the map operation. 
- An <mark style="background: #69E772;">optional</mark> finalise stage for final modifications to the result  

Uses Custom JavaScript functions which provides greater flexibility but is less efficient and more complex than the aggregation pipeline  

Can have output sets that exceed the 16 megabyte output limitation of the aggregation pipeline.

```JSON
db.collection( {  
	mapReduce: <collection>,  
	map: <function>,  
	reduce: <function>,  
	{  
		out: <output>,  
		query: <document>,  
		sort: <document>,  
		limit: <number>,  
	}  
	finalize: <function>,  
	verbose: <boolean> 
} )
```

![](https://i.imgur.com/1Glbnb6.png)

<mark style="background: #69E772;">Map Reduce example:</mark>
![](https://i.imgur.com/Ufvc0K6.png)
![](https://i.imgur.com/qwK1NBZ.png)
![](https://i.imgur.com/hF2J8nF.png)

In MongoDB, map-reduce operations use custom JavaScript functions to <mark style="background: #69E772;">map</mark>, or associate, values to a key. If a key has multiple values mapped to it, the operation <mark style="background: #69E772;">reduces</mark> the values for the key to a single object.

### <mark style="background: #69E772;">The Map and Emit Function:</mark>

In MongoDB, the emit function is used within the MapReduce framework to output key-value pairs during the mapping phase. When you define a MapReduce operation, the map function iterates over each document in a collection, and emit allows you to specify a key and value to pass to the reduce function for further processing.  

The map function is applied to each document in a collection. For each document, you use emit(key, value) to emit a key-value pair. These emitted pairs are then grouped by key.

```JavaScript
function() { ... emit(key, value); }
```

<mark style="background: #69E772;">The map function has the following requirements:</mark>  
- In the map function, reference the current document as <mark style="background: #69E772;">this</mark> within the function.  
- The map function should <mark style="background: #69E772;">not</mark> access the database for any reason.  
- The map function should be pure, or have <mark style="background: #69E772;">no</mark> impact outside of the function (i.e. side effects.)  
- The map function may optionally call ``emit(key,value)`` any number of times to create an output document associating key with value.

<mark style="background: #69E772;">Reduce Function:</mark> The reduce function takes each unique key and an array of all values associated with that key (from the map phase).  

The reduce function processes these values and reduces them to a single result for each unique key.  

The reduce function performs an "aggregation".