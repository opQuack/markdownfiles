```sql

CREATE OR REPLACE TRIGGER redundant_entry
BEFORE INSERT OR UPDATE ON Employee
FOR EACH ROW
DECLARE
    z Employee.DeptName%TYPE;
BEGIN
if( :NEW.Deptno = 10 ) then
        z := 'Accounts';
    elsif( :NEW.Deptno = 20  ) then
        z := 'R&D';
    elsif( :NEW.Deptno = 30 ) then
        z := 'HR';
    elsif( :NEW.Deptno = 40 ) then
        z := 'Engineering';
    end if;
    :NEW.DeptName := z;
END;

```
