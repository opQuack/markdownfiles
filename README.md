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

INSERTION
```sql
INSERT INTO Book VALUES(1,'The Lost Tribe','Panda');
INSERT INTO Book VALUES(2,'The Shining','Penguin');
INSERT INTO Book VALUES(3,'Harry Potter and the Philosophers Stone','Panda');
INSERT INTO Book VALUES(4,'Percy Jackson','Archimis');
INSERT INTO Book VALUES(5,'And Then There Were None','Hindustan Publishers');
INSERT INTO Book VALUES(6,'Murder in Attic','Penguin');

INSERT INTO Book_Authors VALUES(1,'Harry Soldwik');
INSERT INTO Book_Authors VALUES(2,'Stephen King');
INSERT INTO Book_Authors VALUES(3,'J.K Rowling');
INSERT INTO Book_Authors VALUES(4,'Monty Hall');
INSERT INTO Book_Authors VALUES(5,'Harry Soldwik');

INSERT INTO Publisher VALUES('Penguin','Mumbai','28195067');
INSERT INTO Publisher VALUES('Panda','Bangalore','28193467');
INSERT INTO Publisher VALUES('Archimis','Pune','28192869');
INSERT INTO Publisher VALUES('Hindustan Publishers','London','24167217');

INSERT INTO Book_Copies VALUES(1,1,23);
INSERT INTO Book_Copies VALUES(1,2,5);
INSERT INTO Book_Copies VALUES(1,3,2);
INSERT INTO Book_Copies VALUES(2,1,12);
INSERT INTO Book_Copies VALUES(2,3,6);
INSERT INTO Book_Copies VALUES(3,1,8);
INSERT INTO Book_Copies VALUES(3,2,1);
INSERT INTO Book_Copies VALUES(5,1,10);

INSERT INTO Book_Loans VALUES(1,1,1,'02-MAY-1985','04-JAN-1985');
INSERT INTO Book_Loans VALUES(1,2,1,'03-JUNE-1987','04-JAN-1987');
INSERT INTO Book_Loans VALUES(1,3,2,'04-JAN-1987','06-JAN-1987');
INSERT INTO Book_Loans VALUES(2,2,3,'04-FEB-1987','12-JUNE-1987');
INSERT INTO Book_Loans VALUES(2,1,2,'12-JAN-1986','04-FEB-1986');
INSERT INTO Book_Loans VALUES(3,1,1,'10-DEC-1985','04-JAN-1986');
INSERT INTO Book_Loans VALUES(2,1,4,'06-NOV-1987','12-NOV-1987');

INSERT INTO Library_Branch VALUES(1,'A1Town','Mumbai');
INSERT INTO Library_Branch VALUES(2,'Central','Delhi');
INSERT INTO Library_Branch VALUES(3,'Housing','Bangalore');
INSERT INTO Library_Branch VALUES(4,'Shivaji','Mumbai');
INSERT INTO Library_Branch VALUES(5,'Maintly','Pune');

INSERT INTO Borrower VALUES(1,'Manish','Mumbai','28192876');
INSERT INTO Borrower VALUES(2,'Shashank','Delhi','28192812');
INSERT INTO Borrower VALUES(3,'Sanket','Pune','28192875');
INSERT INTO Borrower VALUES(4,'Jeet','Mumbai','28192129');
INSERT INTO Borrower VALUES(5,'Priya','Delhi','2819273');
INSERT INTO Borrower VALUES(6,'Geeta','Mumbai','28192871');

```
