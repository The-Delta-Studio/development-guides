# The Delta Studio Backend SQL Style Guide

## Table of contents

1. [General Notes](#general-notes)
2. [Table naming conventions](#table-naming-conventions)
3. [Field naming conventions](#field-naming-conventions)
4. [Query conventions](#query-conventions)
5. [Column data types](#column-data-types)
5. [Resources](#resources-and-additional-information)

## General notes 

-[1.1](#general-notes--dos) **Do's**
- Use consistent, descriptive names. 
- Make names as generalizable as possible to allow for changes in the future (users instead of buyers).
-Use C-style /*  */ to enclose comments or precede inline comments with -- 
- Use UPPERCASE for queries and lowercase/snake_case for identifiers
- Keep an identifier name length <30 characters
- Names should begin with a letter and end with a letter or number, never underscore
- Store ISO 8601 compliant time and date information (YYYY-MM-DD HH:MM:SS.SSSSS).


-[1.2](#general-notes--dos) **Don'ts**
- Avoid CamelCase as it is difficult to scan quickly
- Avoid non-alphabet characters/numerics
- Avoid redundant suffixes such as \_table or sp\_
- Avoid Hungarian notation such as tbl
- Avoid abbreviations that are not standard
- Avoid multiple consecutive underscores


## Table naming conventions

- Table names should always be plural (users not user)
- Plural should be natural (people not persons)
- An underscore in a table name indicates that the table is a relational connection table between two other tables (user_account)



## Field naming conventions
- Field names should always be singular
- All tables should have an auto-increment, integer primary key named id
- When the id of a table becomes a foreign key in another table, it is referred to as the singular form of the first table, followed by underscore id (e.g. id field of users table becomes user_id when referenced in another table)
- Do not give a field the same name as the table or mention the table name in it's own fields
- Be consequent in suffixes e.g. do not use _tally in one table and _count in others
- This is an example of table named "users" with a primary key of "id", two other fields and a foreign key linking to the field, "id", of another table named "accounts":

| users     |
| ----------- |
| id     | 
| first_name   | 
| last_name   | 
| account_id   | 


## Query conventions
- Use UPPERCASE for commands
- As a general rule, commands should come on a new line except for AS, IN, BETWEEN .. AND, THEN


```SQL
SELECT CASE postcode
       WHEN 'BN1' THEN 'Brighton'
       WHEN 'EH1' THEN 'Edinburgh'
       END AS city
  FROM office_locations
 WHERE country = 'United Kingdom'
   AND opening_time BETWEEN 8 AND 9
   AND postcode IN ('EH1', 'BN1', 'NN1', 'KW1');


```

## Resources and additional information

1. [Simon Holywell SQL conventions](<https://www.sqlstyle.guide/>)
2. [Centizen Nationwide](<https://medium.com/@centizennationwide/mysql-naming-conventions-e3a6f6219efe>)

**[back to top](#table-of-contents)**
