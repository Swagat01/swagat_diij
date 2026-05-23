# Library Loan Management System

Mini project for an end-to-end JDBC application using Apache Derby.

## Package Name

```java
com.dbms.project.registration_no_2341018110
```

## Requirements

- Java JDK
- Apache Derby `derby.jar` added in IntelliJ Project Structure

## How To Run In IntelliJ

1. Open the `ShivamSourav` project in IntelliJ.
2. Make sure `derby.jar` is added in Project Structure.
3. Run `Main.java` or `MainApp.java`.

## Main Classes

- `MainApp`: menu-driven CLI
- `ConnectionManager`: Derby connection, persistent table creation, seed data, reset, shutdown
- `TransactionService`: commit and rollback helper
- `BusinessLogic`: member, book, loan and return operations
- `PerformanceEvaluator`: JDBC benchmark tests
- `Book`, `Member`, `Loan`: simple model classes

## Database Tables

- `Members`
- `Books`
- `Loans`

Indexes are created on:

- `Books.ISBN`
- `Loans.MemberID`
- `Loans.ReturnDate`

## Menu Options

```text
1. Register Member
2. Add Book
3. View Members
4. View Books
5. Process Loan
6. Return Book
7. Active Loans by Member
8. Overdue Loans
9. Run Performance Benchmarks
10. Demonstrate Rollback
11. Demonstrate Savepoint
12. Reset Database
0. Exit
```

## Data Persistence

The Derby database is stored in the project folder as `lab10db/`. The program now creates tables only if they do not already exist. Seed data is inserted only when the `Members` and `Books` tables are empty.

Because of this, members, books, loans and returns remain saved after closing and reopening the application. Use menu option 12 only when you want to delete saved data and recreate the starting seed data.

## Benchmarks Included

- Individual insert vs batch insert
- Full-table scan vs indexed lookup
- Statement vs PreparedStatement
- Per-operation commit vs one commit for 100 operations

The benchmark report is printed on the console with average time, standard deviation and throughput.
