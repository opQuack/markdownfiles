TABLE CREATION
```sql
CREATE TABLE Book(
	BookId int PRIMARY KEY,
	Title varchar(50),
	Pub_Name varchar(50)
);

CREATE TABLE Book_Authors(
	BookId int,
	Author_name varchar(50),
	PRIMARY KEY(BookId, Author_name)
);

CREATE TABLE Publisher(
	Pub_name varchar(50) PRIMARY KEY,
	Addrs varchar(50),
	Phone varchar(50)
);

CREATE TABLE Book_Copies(
	BookId int,
	BranchId int,
	No_of_copies int,
	PRIMARY KEY(BookId, BranchId)
);

CREATE TABLE Book_Loans(
	BookId int,
	BranchId int,
	CardNo int,
	DateOut date,
	DueDate date,
	PRIMARY KEY(BookId, BranchId, CardNo)
);

CREATE TABLE Library_Branch(
	BranchId int PRIMARY KEY,
	BranchName varchar(50),
	Addre varchar(50)
);

CREATE TABLE Borrower(
	CardNo int PRIMARY KEY,
	Name varchar(50),
	Addrs varchar(50),
	Phone varchar(50)
);
```
