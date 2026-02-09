# SQL
# SUMMARY
- [ ] Simple Explanation
- [x] Primitive types
- [x] Softwares and Databases
- [x] Language Categories
- [ ] Language Categories Examples
- [ ] All Examples


# SOFTWARES AND DATABASES

- XAMPP (APACHE + SQL + PHP)
  - APACHE - SERVICES
  - SQL - DATABASE
  - PHP - INTERPRETER
  -  X - ANY PLATFORM (Windowns, Linux, Mac)

- DBEAVER - DATABASE MANAGER
- DATABASES USED: MySQL, MariaDB, Sqlite, FireBird

# LANGUAGE CATEGORIES
SQL is divided into several sublanguages, each responsible for a specific aspect of database management. Understanding these categories helps clarify what kind of operation is being performed and its impact on the database. 

## DDL – Data Definition Language

**Purpose:** Defines and modifies the structure of database objects.
DDL commands are used to create, alter, and remove database objects such as databases, tables, columns, indexes, and constraints. These commands affect the schema, not the data itself.

**Key Characteristics:**

1. Defines what the database looks like
1. Changes are usually auto-committed
1. Affects structure, not records

**Examples:** create, alter, drop

## DML – Data Manipulation Language

**Purpose:** Manipulates the data stored inside tables. DML commands are used to insert, update, and delete records. These operations change the content of the database but not its structure.

**Key Characteristics:**

1. Works with table data (rows)
1. Can be rolled back if inside a transaction
1. Requires careful use of conditions

**Examples:** 

## DQL – Data Query Language

**Purpose:** Retrieves data from the database. DQL is primarily concerned with reading data without modifying it. Although it is often grouped under DML, it is conceptually separated because it does not change database state.

**Key Characteristics:**
1. Read-only operations
1. Does not affect data integrity
1. Can be combined with filtering, sorting, and aggregation

**Examples:** select

## DCL – Data Control Language

**Purpose:** Controls access and permissions within the database. DCL commands define who can access the database and what operations they are allowed to perform. This is critical for security and user management.

**Key Characteristics:**

1. Manages user privileges
1. Enforces security policies
1. Works at database, table, or column level

**Examples:** revoke, grant

## DTL – Data Transaction Language

**Purpose:** Manages transactions to ensure data integrity. This category controls how groups of SQL statements are executed as a single logical unit. It ensures that the database follows the **ACID** principles:

**ACID Properties:**
- **Atomicity** – All operations succeed or none are applied
- **Consistency** – The database moves from one valid state to another
- **Isolation** – Concurrent transactions do not interfere with each other
- **Durability** – Once committed, changes persist even after failures

**Key Characteristics:**
1. Ensures reliability in multi-user environments
1. Prevents partial updates
1. Critical for financial and critical systems





# PRIMITIVE TYPES

## Numerical:

### Integer: 
TinyInt(3bytes), SmallInt, Int(11bytes), MediumInt, BigInt: They store more or less information.
### Real: 
Decimal, Float, Double, Real
### Logic: 
Bit and Boolean (yes/no) (1/0)


## Date and Time:
Date, DateTime, TimeStamp, Time, Year


## Literal
### Characters: 
Char and VarChar; Char will store the full characters even the empty ones, what is diferent from
VarChar. Char(30) would store the name Maria and 25 empty spaces.
### Text: 
TinyText, Text, MediumText, LongText. (Used to prepare texts similar, they can store more or less info.)


### Binary: 
TinyBlob, Blob, MediumBlob and LongBlob (They can store even pictures, it's not something that DBs
usually do.


### Collection:
Enum, Set (They set variables that can be used)


## Spacial
Geometry,Point Polygon, MultiPo (They are not the focus now)



