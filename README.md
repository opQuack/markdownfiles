# DBMS Assignment 5

### Table Creation Commands
```sql
Create table student(
    id INTEGER PRIMARY KEY,
    first_name varchar(15),
    last_name varchar(15),
    street varchar(25),
    city varchar(25),
    state varchar(10),
    zipcode INTEGER
);

Insert into student values( 1 ,' Jaymee ',' Hawtry ',' Green Ridge ',' Hartford ',' CT ', 06140 );
Insert into student values( 2 ,' Idelle ',' Klehn ',' Novick ',' Miami ',' FL ', 33261 );
Insert into student values( 3 ,' Annemarie ',' Mowsdell ',' Rowland ',' Utica ',' NY ', 13505 );
Insert into student values( 4 ,' Edlin ',' O Brogan ',' Crownhardt ',' Punta Gorda ',' FL ', 33982 );
Insert into student values( 5 ,' Andy ',' Please ',' Oxford ',' El Paso ',' TX ', 88563 );
Insert into student values( 6 ,' Jeanette ',' Shank ',' Kinsman ',' Boca Raton ',' FL ', 33487 );
Insert into student values( 7 ,' Beatrice ',' Christall ',' Hanson ',' Detroit ',' MI ', 48224 );
Insert into student values( 8 ,' Ilyse ',' Vernalls ',' Sommers ',' Tulsa ',' OK ', 74193 );
Insert into student values( 9 ,' Dorothy ',' Bickardike ',' Rieder ',' Nashville ',' TN ', 37215 );
Insert into student values( 10 ,' Mathew ',' Cotelard ',' Kennedy ',' Wichita Falls ',' TX ', 76310 );

Create table instructor(
    id INTEGER,
    first_name varchar(10),
    last_name varchar(10),
    sections INTEGER
);

Insert into instructor values( 1 ,' Lu ',' Oman ',' 2 ' );
Insert into instructor values( 2 ,' Bronnie ',' Vanezis ',' 3 ' );
Insert into instructor values( 3 ,' Thacher ',' Page ',' 3 ' );
Insert into instructor values( 4 ,' Susi ',' Jiroutka ',' 2 ' );
```

## Queries

### Question 1
```sql
create or replace package school_api is
    procedure get_address(table_name IN varchar, lookup student.id%type);
    procedure instructor_status;
end school_api;
/

create or replace package body school_api is
    procedure get_address(table_name IN varchar, lookup student.id%type) is
    begin
        for person in (Select * from student where id = lookup)
        loop
            dbms_output.put_line(person.first_name || ' ' || person.last_name || ' ' || person.street || ' ' || person.city || ' ' || person.state || ' ' || person.zipcode);
        end loop;
    end get_address;
    procedure instructor_status is
    begin
        for person in (Select * from instructor)
        loop
            if (person.sections > 2) then
                dbms_output.put_line('Instructor ' || person.id || ' needs a vacation');
            else
                dbms_output.put_line('Instructor ' || person.id || ' teaches ' || person.sections);
            end if;
        end loop;
    end instructor_status;
end school_api;
/

BEGIN
    school_api.get_address('student', 2);
    school_api.instructor_status;
END;
/
```

## Question2
```sql
create or replace package school_api is
    count_helper NUMBER;
    procedure get_address(table_name IN varchar, lookup student.id%type);
    procedure instructor_status;
    procedure remove_student(lookup student.id%type);
end school_api;
/

create or replace package body school_api is
    procedure get_address(table_name IN varchar, lookup student.id%type) is
    begin
        for person in (Select * from student where id = lookup)
        loop
            dbms_output.put_line(person.first_name || ' ' || person.last_name || ' ' || person.street || ' ' || person.city || ' ' || person.state || ' ' || person.zipcode);
        end loop;
    end get_address;
    procedure instructor_status is
    begin
        for person in (Select * from instructor)
        loop
            if (person.sections > 2) then
                dbms_output.put_line('Instructor ' || person.id || ' needs a vacation');
            else
                dbms_output.put_line('Instructor ' || person.id || ' teaches ' || person.sections);
            end if;
        end loop;
    end instructor_status;
    procedure remove_student(lookup student.id%type) is
    begin
        Select count(*) into count_helper from student where id = lookup;
        if count_helper > 0 then
            Delete from student where id = lookup;
        else
            dbms_output.put_line('Student not found');
        end if;
    end remove_student;
end school_api;
/
Begin
    school_api.remove_student(10);
End;
/
```

