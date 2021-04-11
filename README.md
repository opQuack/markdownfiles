# markdownfiles

```sql
DECLARE
    CURSOR items
    IS
    Select Name, Salary, Salary * 0.12 as Bonus
    From Employee;
BEGIN
    FOR i in items
    LOOP
        dbms_output.put_line(i.Name || ' ' || i.Salary || ' ' || i.Bonus);
    END LOOP;
END;
/

```
