```sql

CREATE OR REPLACE TRIGGER row_inserted
BEFORE INSERT ON Employee
FOR EACH ROW

BEGIN
    dbms_output.put_line('ROW INSERTION TRIGGER FIRED');
END;

INSERT INTO Employee values(21, 'Mick', 'Assistant', 40, '', 1200, '01-MAY-2021');
INSERT INTO Employee values(22, 'Daniel', 'Manager', 10, '', 1700, '01-JUN-2021');
INSERT INTO Employee values(23, 'Lewis', 'Senior President', 20, '', 1200, '01-DEC-2021');


```
