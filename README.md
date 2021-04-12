```sql

Create TABLE Employee(
    ID int,
    Name varchar(25),
    Job varchar(25),
    DeptNo int,
    DeptName varchar(25),
    Salary decimal(7,2),
    primary key (ID)
);

DECLARE
    FUNCTION dept_name(x IN number)
    RETURN employee.DeptName%TYPE
    IS
        z employee.DeptName%TYPE;
    BEGIN
        if( x = 10 ) then
            z := 'Accounts';
        elsif( x = 20  ) then
            z := 'R&D';
        elsif( x = 30 ) then
            z := 'HR';
        elsif( x = 40 ) then
            z := 'Engineering';
        end if;
        RETURN z;
    END;
BEGIN
    dbms_output.put_line('Function Created');
END;
/

```
