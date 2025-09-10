![[{A8B7578B-89EC-403C-8910-A01B321F6799}.png]]
find answers to 
what type of db is this
what was the driving force
how to communicate with
what makes it unique
how does it perform
how does it scale

Compare db
- performance
- scale
- problem domain
- api
- support
- extensions

Relational DB
- tables
- rows
- columns
- good
	- structure and well-defined schema
	- ACID
		- Atomicity
			- transactions are treated as a single, indivisible unit
			- combing SQL commands into one transaction separate SQL commands can be transactions
			- ```sql
				  update users
				  set name = "john"
				  where id = 1
				  update users
				  set age = 5
				  where id = 1
			  ```
		- consistency
			- remains consistent state before and after a transaction
			- as long as name was changed to john it will remain as so
		- isolation
			- many users can execute transactions
		- durability
			- once a transaction happens changes persist
	- data integrity
- bad
	- scalability challenges with large datasets
	- complex joins can impact performance
- bad performance
	- heavy writes can lead to contention
	- overuse indexes can slow operations
- fixes
- optimized queries
- caching
- SQL - w3schools
	- quiz that is due next Friday

Watch video of wed notes

POSTGRESQL
- ACID compliant
	- data consistency and reliability
- scalable
	- supports large datasets and high concurrency
- Highly extensible
	- offers support for various programming languages
	- addon or plugs available for the db
- open source
- data model
	- supports data types like arrays, json, geometric shapes
- use cases
	- web apps
	- geospatial apps
	- data warehousing
- PostgreSQL Ecosystem
	- pgAdmin
		- web admin tool for managing the db
	- psql
		- cli for interacting with the db
	- extensions
- advantages
	- robust, reliable and well-tested
	- excellent support for complex queries and transactions
- entity relationship model
	- ERM
	- framework used in db design
	- allows the visual and representation of entities, attributes and relationships with a db
	  - ![[{5C514D45-D4E8-4049-B769-A0CAE94B00B2}.png]]
- Key concepts
	- entity sets
		- objects or concepts that exist independetly and are represented by rectangles in the ERM
	- attributes
		- columns are ovals
	- So ovals are columns and rectangles are tables
- LUCID CHARTS
- Relationships
	- columns between the tables
	- how are enties are related to each other and are represented by diamond shapes
	- connecting it with IDs not names really
	- relationships can be 
		- one to one
			- 
		- one to many
			- 1 employee works in one department and one department has many employees
			- ![[{382C96B1-7F87-407E-88D1-98C1B0AB80A6}.png]]
			- ![[{B1321C9C-894E-44EF-BB1F-9E3D9C0272EB}.png]]
		- many to many
			- 1 employee can work in many departments and one department has many employees
			- ![[{C95CF2C5-DF93-4BAA-AE77-5EC3BA7E5E1C}.png]]
			- ![[{627E579F-63D4-4AED-A93A-5F81BACBB799}.png]]
- working with postgreSQL
	- create tables
		- ex. one country as at least one city but has to have one
		- one venue must have 0 to many events
		- ![[{79B86966-88E8-4FF4-B41C-70CF2DDF00C7}.png]]
		- ```SQL
			  CREATE TABLE countries (
				  country_code char(2) PRIMARY KEY,
				  country_name text UNIQUE
			  );
			  INSERT INTO countries (country_code, 
			  country_name)
			  VALUES ('us', 'United States'),
					('ca', 'Canada');
			SELECT * from countries;
			--Inserting us will error out since it is unique and already exists
			---highlight then run the specific query
			--Since we have 1 single transaction and if we are trying to add us for example it would error out
			INSERT INTO  countries VALUES ('us', 'United 
			States');
			--REFERENCES to connect columns of both tables
		  ```
	- primary and foreign keys
		- can be one or more columns
	- crud
	- join
		- inner and outer
	- fast lookup with indexing
