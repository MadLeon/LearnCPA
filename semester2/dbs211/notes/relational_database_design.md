# Relational Database Design

## Relational Model

### Data Model

A method of describing data or information, which include:

- structure and format
- operations - selection (queries) and modification (insertion, updating and deleting)
- limitations - defined constraints or enforced rules

### Relational Model

- define relationships between various data points and separates data
- eliminate inefficiencies and non-functional dependencies

### The Basics of the Relational Model

- Every row - a single instance of the entity in the table
- every column - an attribute (or property) of that entity
- one value (atomic) for each column and each row

### Schema Notation

`DEPARTMENT ( department_id, department_name, manager_id, location_id )`



## Keys

> There **must** be a single attribute or a combination of attributes that will **uniquely identify** a specific instance, or row, in a table.

#### Type of Keys

| Keys          | Description                                                  |
| ------------- | ------------------------------------------------------------ |
| Candidate Key | an attribute, or a combination of them, that could potentially be used to apply uniqueness |
| Primary Key   | an attribute, or a combination of them, that has been chosen to apply uniqueness |
| Composite Key | the unique combination of values                             |
| Surrogate Key | an artificially added field to replace the existing fields from being the primary key |
| Foreign Key   | a constraint applied to a table defining the relationship between two tables |

#### Usage of Surrogate Key

- simplify the interaction with the DB if multiple composite fields are chosen
- when there is not a field available to be a Primary Key

#### The Fundamental rule of relational database design

> Every table must have one, and only one, primary key. Remember that a composite key is a single key made up of more than one field.



## Relationships

### Relationship Types

#### One to Many (1-∞)

- the most common
    - one direction - only one value per row of the child table
    - the other direction - many rows in the child table that reference a single row in parent

#### One to One (1 - 1)

- different attributes have varying level of completeness

#### Many to Many (∞ - ∞)

- also noted M:M or M:N
- more than one reference to each row of the other table, in both directions
- can not physically be created in a database directly between 2 tables



## Referential Integrity

- ensure values entered into child table attributes already exist in the parent table
- prevents records in a parent table to be deleted if it is currently being referenced from a child table

### Cascading

#### Cascade Updates

- If the primary key of the parent record changes for any reason, then the child records that reference the parent value would be automatically updated to match the change.
- in cases of a composite primary key, the uniqueness comes only from the combination of values and therefore it is possible that records could overlap and mixed together where they should not be.

#### Cascade Deletes

- dangerous
- if a parent record is deleted, then all child records that refer to the parent record will also be deleted
- if there are multiple relationships in a database, one relationship can not override another
- different results could happen whether cascade deletes is allowed for the relationship



## Table Types

### Data Table

- store raw data for later
- the major type

### Lookup Table

- centralize data to avoid repeated data groups
- dropdown list

### Junction / Bridge Table

- created between two tables to simulate a many to many relationship
- through two opposite one to many relationship
- can contain data

### Temporary Table

- has limited lifetime
- often lack referential integrity
- not manually manipulated
- has distinct purpose
    - moving / import data
    - database migration
    - the static storage of query results to minimize repeated processing required for complex calculations