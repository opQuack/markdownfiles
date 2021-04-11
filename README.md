```sql
DECLARE
    department employee.dept%TYPE;
    max_salary number;
    PROCEDURE display_dept(x IN employee.dept%TYPE, y OUT number) IS
    BEGIN
        y := 0;
        FOR items in (SELECT Name, Salary FROM Employee WHERE dept = x)
        LOOP
            y := y + items.Salary;
            dbms_output.put_line(items.Name || ' ' || items.Salary);
        END LOOP;
    END;
BEGIN
    department := 'Accounts';
    display_dept(department, max_salary);
    dbms_output.put_line('Total Salary in ' || department || ' = ' || max_salary);
END;
/


```
