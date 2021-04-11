```sql

DECLARE
    x number;
    y number;
    z number;
    FUNCTION powerFind(x IN number, y IN number)
    RETURN number 
    IS
        z number;
    BEGIN
        z := POWER(x, y);
        RETURN z;
    END;
BEGIN
    x := 2;
    y := 3;
    z := powerFind(x, y);
    dbms_output.put_line(x || '^' || y || ' = ' || z);
END;
/
```
