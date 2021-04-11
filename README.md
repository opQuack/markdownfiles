```sql
DECLARE
    empno employee.ID%TYPE;
    increment_salary number;
    PROCEDURE raise_sal(x IN employee.ID%TYPE, y IN number) IS
    BEGIN
        Update Employee
        set Salary = Salary + y
        WHERE ID = x;
    END;
BEGIN
    empno := 2;
    increment_salary := 500;
    raise_sal(empno, increment_salary);
END;
/
Select * from Employee;

```
