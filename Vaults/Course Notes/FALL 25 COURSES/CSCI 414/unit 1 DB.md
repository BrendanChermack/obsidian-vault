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
			-- EXAMPLE CODE FROM SCRIPT FILE
			-------------------- PART 1 ----------------------------------------

CREATE TABLE countries (

  country_code char(2) PRIMARY KEY,

  country_name text UNIQUE

  );

  

INSERT INTO countries (country_code, country_name)

VALUES ('us', 'United States'),

       ('mx', 'Mexico'),

       ('au', 'Australia'),

       ('gb', 'United Kingdom'),

       ('de', 'Germany');

  

select * from countries

  

insert into countries VALUES ('us', 'United States')

  

delete from countries

where country_code = 'de';

  

------------------------------------------------------------------------------------------

  

CREATE TABLE cities (

  name text NOT NULL, 

  postal_code varchar(9) CHECK (postal_code <> ''),

  country_code char(2) REFERENCES countries, -- reference table this city belongs to what country

  PRIMARY KEY (country_code, postal_code) -- if we added an id column as the only primary key. country code will act as a foriegn key. The idea is to use 2 primary keys to save space and 2 are needed because a country may have the same postal code as another country

  );

  

INSERT INTO cities

VALUES ('Toronto', 'M4C1B5', 'ca');

  

insert into countries VALUES ('ca', 'Canada')

  

insert into cities

VALUES ('Portland', '97206', 'us');

  

SELECT cities.*, country_name

FROM cities INNER JOIN countries /* or just FROM cities JOIN countries */

ON cities.country_code = countries.country_code;

  

------------------------------------------------------------------------------------------

  

CREATE TABLE venues (

  venue_id SERIAL PRIMARY KEY,

  name varchar(255),

  street_address text,

  type char(7) CHECK ( type in ('public', 'private') ) DEFAULT 'public',

  postal_code varchar(9),

  country_code char(2),

  FOREIGN KEY (country_code, postal_code) -- connection, needs to be this 2 to match

  REFERENCES cities (country_code, postal_code) MATCH FULL
-- exactly needs to match
  );

  

INSERT INTO venues (name, postal_code, country_code)

VALUES ('Crystal Ballroom', '97206', 'us');

  

INSERT INTO venues (name, postal_code, country_code)

VALUES ('Voodoo Donuts', '97206', 'us') RETURNING venue_id;

  

------------------------------------------------------------------------------------------

  

CREATE TABLE events (

  event_id SERIAL PRIMARY KEY,

  title text NOT NULL,

  starts timestamp,

  ends timestamp,

  venue_id integer,

  FOREIGN KEY (venue_id) REFERENCES venues --venue id is option as per the design therefore it is not connected to one. used as a connector when the venue id is given

  );

  

INSERT INTO events (title, starts, ends, venue_id)

VALUES ('LARP Club', '2012-02-15 17:30:00', '2012-02-15 19:30:00', 1);

  

INSERT INTO events (title, starts, ends)

VALUES ('April Fools Day', '2012-04-01 00:00:00', '2012-04-01 23:59:00'),

       ('Christmas Day', '2012-12-25 00:00:00', '2012-02-25 23:59:00');

  

SELECT e.title, v.name

FROM events e JOIN venues v -- 'INNER' is not required

ON e.venue_id = v.venue_id;

  

SELECT e.title, v.name

FROM events e LEFT JOIN venues v -- Retrieving all events with/without a venue

ON e.venue_id = v.venue_id;

  

------------------------------------------------------------------------------------------

  

CREATE INDEX events_title ON events USING hash (title);

CREATE INDEX events_starts ON events USING btree (starts);

  

-------------------- PART 2 ----------------------------------------

  

-- Delete data from "events" table

DELETE FROM events;

  

-- Delete data from "venues" table

DELETE FROM venues;

  

-- Delete data from "cities" table

DELETE FROM cities;

  

-- Delete data from "countries" table

DELETE FROM countries;

  
  

-- Insert countries

INSERT INTO countries (country_code, country_name) VALUES

  ('US', 'United States');

  

-- Insert cities

INSERT INTO cities (name, postal_code, country_code) VALUES

  ('Cityville', '12345', 'US'),

  ('Artland', '23456', 'US'),

  ('Conftown', '34567', 'US'),

  ('Foodville', '45678', 'US'),

  ('Music City', '56789', 'US'),

  ('Booktown', '67890', 'US'),

  ('Photoville', '78901', 'US'),

  ('Fashionville', '89012', 'US'),

  ('Communitytown', '90123', 'US'),

  ('Cinemacity', '01234', 'US');

  
  

-- Venue 1

INSERT INTO venues (venue_id, name, street_address, type, postal_code, country_code)

VALUES (1, 'Fitness Center', '123 Main St', 'public', '12345', 'US');

  

-- Venue 2

INSERT INTO venues (venue_id, name, street_address, type, postal_code, country_code)

VALUES (2, 'Art Gallery', '456 Art Ave', 'public', '23456', 'US');

  

-- Venue 3

INSERT INTO venues (venue_id, name, street_address, type, postal_code, country_code)

VALUES (3, 'Conference Center', '789 Conference Rd', 'public', '34567', 'US');

  

-- Venue 4

INSERT INTO venues (venue_id, name, street_address, type, postal_code, country_code)

VALUES (4, 'Tasting Hall', '101 Flavor St', 'public', '45678', 'US');

  

-- Venue 5

INSERT INTO venues (venue_id, name, street_address, type, postal_code, country_code)

VALUES (5, 'Music Park', '555 Melody Ln', 'public', '56789', 'US');

  

-- Venue 6

INSERT INTO venues (venue_id, name, street_address, type, postal_code, country_code)

VALUES (6, 'Bookstore', '222 Literary St', 'public', '67890', 'US');

  

-- Venue 7

INSERT INTO venues (venue_id, name, street_address, type, postal_code, country_code)

VALUES (7, 'Photography Studio', '777 Shutter Rd', 'public', '78901', 'US');

  

-- Venue 8

INSERT INTO venues (venue_id, name, street_address, type, postal_code, country_code)

VALUES (8, 'Fashion Mall', '888 Style Blvd', 'public', '89012', 'US');

  

-- Venue 9

INSERT INTO venues (venue_id, name, street_address, type, postal_code, country_code)

VALUES (9, 'Community Center', '333 Charity Ave', 'public', '90123', 'US');

  

-- Venue 10

INSERT INTO venues (venue_id, name, street_address, type, postal_code, country_code)

VALUES (10, 'Cinema Complex', '444 Film St', 'public', '01234', 'US');

  
  

-- Event 1

INSERT INTO events (title, starts, ends, venue_id) VALUES ('Tech Conference', '2023-08-27 09:00:00', '2023-08-27 17:00:00', 1);

  

-- Event 2

INSERT INTO events (title, starts, ends, venue_id) VALUES ('Art Exhibition', '2023-09-10 10:30:00', '2023-09-10 18:00:00', 1);

  

-- Event 3

INSERT INTO events (title, starts, ends, venue_id) VALUES ('Music Festival', '2023-09-15 14:00:00', '2023-09-17 23:59:00', 2);

  

-- Event 4

INSERT INTO events (title, starts, ends, venue_id) VALUES ('Fitness Workshop', '2023-09-02 08:30:00', '2023-09-02 11:00:00', 2);

  

-- Event 5

INSERT INTO events (title, starts, ends, venue_id) VALUES ('Food Tasting', '2023-09-08 18:00:00', '2023-09-08 20:30:00', 3);

  

-- Event 6

INSERT INTO events (title, starts, ends, venue_id) VALUES ('Book Launch', '2023-09-12 16:00:00', '2023-09-12 18:00:00', 3);

  

-- Event 7

INSERT INTO events (title, starts, ends, venue_id) VALUES ('Fashion Show', '2023-09-20 19:30:00', '2023-09-20 21:30:00', 3);

  

-- Event 8

INSERT INTO events (title, starts, ends, venue_id) VALUES ('Workshop: Photography Basics', '2023-09-05 11:00:00', '2023-09-05 13:30:00', 4);

  

-- Event 9

INSERT INTO events (title, starts, ends, venue_id) VALUES ('Charity Gala', '2023-09-18 18:30:00', '2023-09-18 23:00:00', 5);

  

-- Event 10

INSERT INTO events (title, starts, ends, venue_id) VALUES ('Film Screening', '2023-09-25 20:00:00', '2023-09-25 22:30:00', 6);

  

INSERT INTO events (title, starts, ends) VALUES ('No venue', '2023-09-25 20:00:00', '2023-09-25 22:30:00');

  

INSERT INTO events (title, starts, ends) VALUES ('Day 1 holiday', '2023-09-25 20:00:00', '2023-09-25 22:30:00');
		  ```
	- primary and foreign keys
		- can be one or more columns
	- crud
	- join
		- inner and outer
	- fast lookup with indexing
	- 
- grouping
	- ![[{8D2246F7-1D8F-4CA6-A6BC-7FB831C7E57C}.png]]
	- specify what type of aggregation we want
```SQL
-- Aggregate Functions

SELECT COUNT(*) AS total_events FROM events;

  

SELECT AVG(ends - starts) AS average_duration FROM events;

  

SELECT MIN(starts) AS earliest_start, MAX(starts) AS latest_start FROM events;

  

SELECT SUM(ends - starts) AS total_duration FROM events;

  

SELECT venue_id, COUNT(*) AS event_count

FROM events

GROUP BY venue_id

ORDER BY event_count DESC

LIMIT 1;

  

-- Grouping

select venue_id, count(*) from events

group by venue_id

  

-- Group Events by Venue and Count the Number of Events at Each Venue

SELECT venue_id, COUNT(*) AS event_count

FROM events

GROUP BY venue_id

ORDER BY event_count DESC;

  

-- Group Events by Year and Count the Number of Events in Each Year

SELECT EXTRACT(YEAR FROM starts) AS event_year, COUNT(*) AS event_count

FROM events

GROUP BY event_year

ORDER BY event_year;

  

-- Group Events by Month and Count the Number of Events in Each Month

SELECT EXTRACT(MONTH FROM starts) AS event_month, COUNT(*) AS event_count

FROM events

GROUP BY event_month

ORDER BY event_month;

  

-- Group Events by Venue and Calculate the Total Duration of Events at Each Venue:**

SELECT venue_id, SUM(ends - starts) AS total_duration

FROM events

GROUP BY venue_id

ORDER BY total_duration DESC;

  

-- Window functions

SELECT venue_id, starts, ends, COUNT(*) OVER (PARTITION BY venue_id)

FROM events

  

--Transaction

-- Begin a transaction

-- BEGIN;

  

-- Attempt to delete events

DELETE FROM events WHERE venue_id = 1;

  

-- Check the deleted rows

SELECT * FROM events WHERE venue_id = 1;

  

-- Rollback the transaction

-- ROLLBACK;

-- COMMIT

  

-- Stored Procedures

CREATE OR REPLACE PROCEDURE insert_events(num_records INTEGER)

LANGUAGE plpgsql

AS $$

BEGIN

    FOR i IN 1..num_records LOOP

        INSERT INTO events (title, starts, ends, venue_id)

        VALUES (

            CONCAT('Event Title ', i, ' - ', md5(random()::text)),

            NOW() + (random() * INTERVAL '30 days'),

            NOW() + (random() * INTERVAL '60 days'),

            (SELECT venue_id FROM venues ORDER BY random() LIMIT 1)

        );

    END LOOP;

END $$;

  

-- NOW(): This function returns the current timestamp (the date and time when the query is executed).

-- random(): This function generates a random value between 0 and 1.

-- INTERVAL '30 days': This defines a time duration of 30 days. You can specify different types of intervals (e.g., days, hours, minutes). The format inside the quotes can be 'n units', where n is a number, and units is a time unit (such as seconds, minutes, hours, days, months, etc.).

-- random() * INTERVAL '30 days': This multiplies the random number (between 0 and 1) by the interval of 30 days, resulting in a random number of days between 0 and 30.

-- NOW() + (random() * INTERVAL '30 days'): This adds the random time interval (up to 30 days) to the current timestamp returned by NOW(), meaning the starts timestamp will be sometime between now and 30 days in the future.

  

CALL insert_events(1000); -- Inserts 1000 records

  

-- Functions

CREATE OR REPLACE FUNCTION add_event(

  title text,

  starts timestamp,

  ends timestamp,

  venue text,

  postal varchar(9),

  country char(2))

RETURNS boolean AS $$

DECLARE

  did_insert boolean := false;

  found_count integer;

  the_venue_id integer;

BEGIN

  SELECT venue_id INTO the_venue_id

  FROM venues v

  WHERE v.postal_code=postal AND v.country_code=country AND v.name ILIKE venue

  LIMIT 1;

  

  IF the_venue_id IS NULL THEN

    INSERT INTO venues (name, postal_code, country_code)

    VALUES (venue, postal, country)

    RETURNING venue_id INTO the_venue_id;

  

    did_insert := true;

  END IF;

  

  -- Note: this is a notice, not an error as in some programming languages

  RAISE NOTICE 'Venue found %', the_venue_id;

  

  INSERT INTO events (title, starts, ends, venue_id)

  VALUES (title, starts, ends, the_venue_id);

  

  RETURN did_insert;

END;

$$ LANGUAGE plpgsql;

  

select add_event('House Party', '2018-05-03 23:00', '2018-05-04 02:00', 'Run''s House', '12345', 'US');

--------------------------

  

CREATE OR REPLACE FUNCTION calculate_duration_avg(

  ven_id integer

  )

RETURNS interval AS $$

DECLARE

    duration interval;

BEGIN

SELECT AVG(ends - starts) into duration

FROM events

WHERE venue_id = ven_id;

return duration;

END;

$$ LANGUAGE plpgsql;

  

select calculate_duration_avg(1)

  

-- compare the result of the above function to the below script when venue_id = 1

SELECT AVG(ends - starts)

FROM events

WHERE venue_id = 1

  

-- Triggers

CREATE TABLE logs (

  event_id integer,

  old_title varchar(255),

  old_starts timestamp,

  old_ends timestamp,

  logged_at timestamp DEFAULT current_timestamp

  );

  

CREATE OR REPLACE FUNCTION log_event() RETURNS trigger AS $$

DECLARE

BEGIN

  INSERT INTO logs (event_id, old_title, old_starts, old_ends)

  VALUES (OLD.event_id, OLD.title, OLD.starts, OLD.ends);

  RAISE NOTICE 'Someone just changed event #%', OLD.event_id;

  RETURN NEW;

END;

$$ LANGUAGE plpgsql;

  

CREATE TRIGGER log_events

 AFTER UPDATE ON events

FOR EACH ROW EXECUTE PROCEDURE log_event();

  

UPDATE events SET ends = '2012-05-04 01:00:00' WHERE title = 'House Party';

  

--Views

CREATE VIEW upcoming_events AS

SELECT event_id, title, starts

FROM events

WHERE starts > NOW();

  

select * from upcoming_events

  

CREATE VIEW holidays AS

  SELECT event_id AS holiday_id, title AS name, starts AS date

  FROM events

  WHERE title LIKE '%Day%' AND venue_id IS NULL;
  -- This is an example of VIEW. This make it easier to work with multiple tables at once to view it. real data is saved in the tables. it is read only 

  

select * from holidays

  

UPDATE holidays SET name ='Holiday 2' where name = 'Day 1 holiday'; -- Error because holidays is a view not a table. Check Rules next.

  

--Rules

--holidays is a view, to enable update, we define a rule

CREATE RULE update_holidays AS ON UPDATE TO holidays DO INSTEAD

  UPDATE events

  SET title = NEW.name,

      starts = NEW.date,

  WHERE title = OLD.name;
  -- used to change query behavior. data valiidation for example. Time being set over 24hrs. withdrawing more money when ur bank acc is 0. For above this rule will allow it to modify the actual table the view is created from. niche usecase not used a ton.
```
Friday  sept 12th missed class

- when you want to view a lot of data instead of making a huge sql query we can make a view that can be used just to call that will have all those joins.
- db are for a ton of records
- indexing is for db speed
- hash index
	- a column is needed to be index
	- can be any column it just depends on what needs to be searched
		- like name if u are looking up names
	- indexes for everything will cause slow downs
		- storage increases
		- every time new records are added new indexing happens
			- string -> hash function -> number for bucket location
	- hash index is a hash table
	- ![[{3935E4FF-EF9F-42B0-9D23-9FF991D5430C}.png]]
- full text and multidimensions
	- many to many
	- ![[{484654BE-1486-44D6-AD5A-DC5061396006}.png]]
	- 

| movieId | actorId |
| ------- | ------- |
| 1       | 1       |
| 1       | 2       |
| 1       | 2       |
| 2       | 1       |
| 2       | 2       |
- ilike is case insensitive
- % after the string will get u anything after those character that match the ones before john% -> john smith
- [regex](regex101.com)
	- ![[{6BE35254-00CC-4886-A358-EA451E84322D}.png]]
- Levenshtein distance between kitten and sitting
	- how many characters are needed to be changed for them to be the same
	- find similarities 
	- SELECT 'kitten', 'sitting', LEVENSHTEIN('kitten', 'sitting')
	- usually used for example finding a movie title where the movie title is a distance of less than 3
	- used a lot
	- useful when there is typos
- Full text and multi-dimensions
	- allows you to search natural language text efficiently
		- Unlike ILIKE or LIKE which looks for exact substrings
	- SELECT title from movies where title @@ 'night & day';
	- converts title to a tsvector and 'night & day' to a tsquery
	- tsvector
		- datatype that splits a string into an array of tokens which are searched against the given query
			- token could be one character, vector of characters hello = ['h', 'e', 'l', 'l', 'o']
		- location of words kind of acts like an index
	- tsquery: specifies the terms and conditions for a search
		- select title, to_tsvector(title) from movies;
		- SELECT title from movies @@ 'day & night';
- cube package
	- handles multi-dimensional data and perform various operations 
	- for example for our movies db we can have a cube for the genres of a movie
	- cube is like a vector/array
	- genres table will have name and position
	- ![[{27CF5E39-FC7A-4EBB-9D70-4E5DFC0D05A7}.png]]
	- the number in the vector here is the position (not zero) and the value from 1 to 10 is the strength of the genre
	- so star wars belongs to those 3 genres and the strength of how likely they are in the movie
	- not only looking for the genre but also the rank of the genre thats why its multi-dimensional
	- cube_ur_coord
	- ```sql
	  -------------------- PART 3 ----------------------------------------

-- Run the movies scripts first:

-- -- movies_schema.sql

-- -- movies_data.sql

  

--Install pacakges

create extension if not exists tablefunc

create extension if not exists fuzzystrmatch

create extension if not exists cube

  

select * from pg_extension where extname = 'tablefunc'

-- Like and ILIKE

select title from movies where title ilike 'stardust%'

select title from movies where title ilike 'star%'

select title from movies where title ilike 'stard___'

  

--regex

SELECT COUNT(*) FROM movies WHERE title !~* '^the.*';

  

--LEVENSHTEIN

SELECT 'kitten', 'sitting', LEVENSHTEIN('kitten', 'sitting')

SELECT movie_id, title FROM movies WHERE levenshtein(lower(title), 'a hard day nght') < 3;

  
  

-- Full Text and multidimensions

select title, to_tsvector(title) from movies;

  

Select title

from movies

where title @@ 'night & day';

  

--cube

select name, cube_ur_coord('(0,7,0,0,0,0,0,0,0,7,0,0,0,0,10,0,0,0)', position) as score

from genres G

where cube_ur_coord('(0,7,0,0,0,0,0,0,0,7,0,0,0,0,10,0,0,0)', position) > 0;

  

select *, cube_distance(genre, '(0,7,0,0,0,0,0,0,0,7,0,0,0,0,10,0,0,0)') dist

from movies

order by dist;

  

CREATE TABLE spatial_data (

    id serial PRIMARY KEY,

    point_data cube

);

  

INSERT INTO spatial_data (point_data) VALUES ('(1, 2, 3)');

INSERT INTO spatial_data (point_data) VALUES ('(4, 5, 6)');

-- You can insert more data as needed

  

-- Calculate the distance between two 3D points

-- the <-> operator calculates the distance between the stored 3D points and the specified point (2, 3, 4).

SELECT point_data <-> '(2, 3, 4)' AS distance

FROM spatial_data;

  
  

-- 1. Size of the Table Including All Indexes

SELECT pg_size_pretty(pg_total_relation_size('your_table_name')) AS total_size;

-- 2. Size of the Table Alone (Excluding Indexes)

SELECT pg_size_pretty(pg_relation_size('your_table_name')) AS table_size;

-- 3. Size of the Indexes Only

SELECT pg_size_pretty(pg_indexes_size('your_table_name')) AS indexes_size;

-- 4. Size of All Tables in the Database

SELECT

    table_name,

    pg_size_pretty(pg_total_relation_size(table_name)) AS total_size

FROM

    information_schema.tables

WHERE

    table_schema = 'public'  -- Adjust schema name if needed

ORDER BY

    pg_total_relation_size(table_name) DESC;

-- 5. Detailed Breakdown by Table and Index

SELECT

    table_name,

    pg_size_pretty(pg_relation_size(table_name)) AS table_size,

    pg_size_pretty(pg_total_relation_size(table_name) - pg_relation_size(table_name)) AS indexes_size

FROM

    information_schema.tables

WHERE

    table_schema = 'public'  -- Adjust schema name if needed

ORDER BY

    pg_total_relation_size(table_name) DESC;
	  ```
	  If this is wanted to be ran u need to run movies scheme and movie data
  - cube_distance
	  - ![[{5CA2B45E-9C32-4ED5-A637-90E2F7DCEAD3}.png]]
	  - 