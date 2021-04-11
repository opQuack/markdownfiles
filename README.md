```sql
DECLARE
    table_of number;
    table_till number;
    PROCEDURE multi_table(x IN number, y IN number) IS
    BEGIN
        FOR i in 1..y
        LOOP
            dbms_output.put_line(x || ' x ' || i || ' = ' || x*i);
        END LOOP;
    END;
BEGIN
    table_of := 2;
    table_till := 8;
    multi_table(table_of, table_till);
END;
/
```
