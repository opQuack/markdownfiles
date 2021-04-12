```sql

CREATE OR REPLACE TRIGGER date_entry
BEFORE INSERT OR UPDATE ON Employee
FOR EACH ROW
DECLARE
    date_error EXCEPTION;
BEGIN
    if(:NEW.DOJ < current_date()) then
        RAISE date_error;
    end if;
EXCEPTION
    WHEN date_error THEN
        dbms_output.put_line('ERROR IN DATE');
END;
/

```
