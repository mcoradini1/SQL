# Summary
- [ ] Simple Explanation
- [x] Primitive types
- [x] Softwares and Databases
- [x] Language Categories
- [ ] Relational DataBase (RDBMS)
- [ ] Damp (Saving)
- [ ] All Examples


# Softwares and Databases

- **XAMPP (APACHE + SQL + PHP)**
  - APACHE - SERVICES
  - SQL - DATABASE
  - PHP - INTERPRETER
  -  X - ANY PLATFORM (Windowns, Linux, Mac)

- **DBEAVER** - DATABASE MANAGER
- **DATABASES:**
From this set of database the only one not used was SQL Server due to it's complex install.

Database|Type|Use|Strenghts|Limitation|
---|---|---|---|---|
Sqlite|File-based|Small apps and mobile|Easy install, no server, lighther|fewer advanced features|
Firebird|Relational(Client server)|Small to Medium apps|Light with more funcionalities|Requires an easy setup|
MySql/MariaDB|Relational(Server-based)|Scalable systems|Fast, widely supported easy to manage with more features|Requires a considered setup|
SQL Server| Relational(Enterprise)|Large Systems|Advanced security analitics and more features|Requires a heavy and complex setup and licensing.


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


---

# Primitive Types

---
## Numerical:


### Integer:
TinyInt(3bytes), SmallInt, Int(11bytes), MediumInt, BigInt: They store more or less information.
### Real: 
Decimal, Float, Double, Real
### Logic: 
Bit and Boolean (yes/no) (1/0)

---
## Date and Time:
Date, DateTime, TimeStamp, Time, Year

---
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

---

## Spacial
Geometry,Point Polygon, MultiPo (They are not the focus now)


---
# Relational DataBase (RDBMS)
In databases, relationships between tables are created through a structured model. The classic approach is the 
**Entity–Relationship Diagram (ERD)** , although newer paradigms like **object‑oriented modelling (OOP)** also exist, 
even if they’re not as widely used for database design yet.

The **ERD** is used to define relationships between tables in a database. Entities like Courses or Workers contain 
attributes such as **name or date_of_birth**, which store the actual data. Each record (tuple) must have a primary key to 
uniquely identify it. These keys are essential because they allow entities to connect and form meaningful relationships 
within the database.

## Cardinality:

Cardinality describes how many records in one table relate to records in another table. It defines the type of relationship between entities.
The main types are:

- **1:1 (one‑to‑one)** – one record matches exactly one record.
- **1:n (one‑to‑many)** – one record connects to many records.
- **n:m (many‑to‑many)** – many records connect to many records (usually via a junction table).

Other types not vastly considered yet:
- **Null cardinality** -
A relationship that is optional, the entity can exist without a related record. 
- **Minimum cardinality (min)** - 
The minimum number of relationships required (usually 0 or 1).
- **Maximum cardinality (max)** -
The maximum number of relationships allowed (1, N, or M).
- **Strong cardinality** -
A relationship where the child depends on the parent (like strong/identifying).
The parent’s key becomes part of the child’s key.
- **Weak cardinality** -
A relationship where the child does not depend on the parent.
The child has its own primary key.

## Examples:
### 1:1 (one-to-one)
It is important to check if it is possible to have everything in one table in (this case do not need to relate to them) in case it's still 
necessary to have them separated, we follow:
1. Choose one to be the dominant (the example considers the man)
2. We transfer the woman's primary key (PK) as a Foreign Key (FK) in Men.
3. It is important to always leave the dominant to the left side of the diagram.

<img width="564" height="397" alt="1 to 1" src="https://github.com/user-attachments/assets/b8e450d6-dfe6-4bd8-bb65-3c902f325dba" />

### 1:n (one-to-many)
In this case, let's consider the Workers and Course databases used in the examples. Our assumption for this is that each worker can only Watch one movie. 
1.  We take the PK for the **side one** and transfer as FK to the **many side**


<img width="564" height="397" alt="1 TO N" src="https://github.com/user-attachments/assets/5e95b9b0-70b7-4407-b0c2-42c9a0da053f" />

### n:m (many-to-many)
We follow the same example above, but in a more realistic way: each worker can watch as many courses as they want. To that work its important to:
1. Dismember to 1:1 on both sides
2. where the central relationship between them will become an entity
3. Entity-Relationship will receive both PK as FK.
4. Acts like 1:n case then


<img width="564" height="397" alt="M to N" src="https://github.com/user-attachments/assets/c223e966-9f12-4474-9ebd-12363ba98333" />



