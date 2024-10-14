## TYPES OF DATABASES

- Hierarchical databases
- Network databases
- Object-oriented databases
- Relational databases
- Cloud Database
- Centralized Database
- Operational Database
- NoSQL databases

### Hierarchial database

As in any hierarchy, this database follows the progression of data being categorized in ranks or levels, wherein data is categorized based on a common linkage.

As a result, two entities of data will be lower in rank and the commonality will assume a higher rank. 

### Network databases

In Layman’s terms, a network database is a hierarchical database, but with a major tweak. 

The child records are given the freedom to associate with multiple parent records. 

As a result, a network or net of database files linked with multiple threads is observed.

### Object-oriented databases

Information stored in a database is capable of being represented as an object that responds as an instance of the database model. 

Therefore, the object can be referenced and called without any difficulty. 

### Relational databases
  
A relational database organizes data into tables (or relations) that are linked to each other based on data relationships.

Each table consists of rows and columns where:

**Columns** represent the attributes or fields.

**Rows** represent records.

**Tables:** They store data in rows and columns.

**Primary Key:** A unique identifier for each record in a table. For example, a user_id in a Users table.

**Foreign Key:** A field in one table that uniquely identifies a row of another table, establishing a relationship between the two tables.

**Relationships:** These define how data in one table relates to data in another. Common types include:

One-to-One: Each row in Table A is linked to one row in Table B.

One-to-Many: Each row in Table A can link to multiple rows in Table B.

Many-to-Many: Each row in Table A can link to many rows in Table B and vice versa.

### cloud databases

A cloud database is used where data requires a virtual environment for storing and executing over the cloud platforms and there are so many cloud computing services for accessing the data from the databases (like SaaS, Paas, etc).

There are some names of cloud platforms are-

- Amazon Web Services (AWS)
- Google Cloud Platform (GCP)
- Microsoft Azure
- ScienceSoft, etc.

### Centralized Database

A centralized database is a type of database that is stored, located as well as maintained at a single location and it is more secure when the user wants to fetch the data from the Centralized Database.

### personal databases

Collecting and Storing the data on its System and this type of databases is basically designed for the single user.

A personal database is a small, single-user database designed to manage data for individual use, typically on a personal computer or mobile device. 

It is often used for managing personal information like contacts, budgets, or notes.

They are ideal for individuals or small tasks where only one user interacts with the data, as opposed to multi-user or enterprise databases.

**Examples** include Microsoft Access and SQLite.

### operational databases

It is used for creating, updating, and deleting the database in real-time and it is designed for executing and handling the daily data operation in organizations and businesses purposes.

### Nosql databases

NoSQL databases are non-relational databases designed to store and retrieve data in ways other than the tabular relations used in relational databases.

They are built to handle large volumes of unstructured or semi-structured data and can scale horizontally across multiple servers.

**Example**

Document Stores

Key-Value Stores

Column-Family Stores

Graph Databases



| Relational Database	|  NoSQL |
--------------------- | -------| 
|It is used to handle data coming in low velocity.|	It is used to handle data coming in high velocity.|
|It gives only read scalability.	                |It gives both read and write scalability.|
| It manages structured data.	|  It manages all type of data.|
|Data arrives from one or few locations.	|Data arrives from many locations.|
|It supports complex transactions.	|It supports simple transactions.
|It has single point of failure.|	No single point of failure.
It handles data in less volume.|	It handles data in high volume.
Transactions written in one location.|	Transactions written in many locations.
support ACID properties compliance	|doesn’t support ACID properties
Its difficult to make changes in database once it is defined	| Enables easy and frequent changes to database
schema  is mandatory to store the data	|schema design is not required
Deployed in vertical fashion.	|Deployed in Horizontal fashion

