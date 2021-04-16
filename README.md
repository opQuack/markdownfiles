105
```sql
Select Software.PName, Institute
from Software LEFT OUTER JOIN Studies
on Software.PName = Studies.PName;
```

104
```sql
Select count(*)
from Software
where PName = (Select PNAme
from Programmer
where DOJ = (Select min(DOJ) from Programmer NATURAL JOIN Studies where Institute = 'BDPS'))
GROUP BY PName;
```

103
```sql
Select count(*)
from Programmer NATURAL JOIN Software
where Salary > (Select max(Salary) from Programmer where Sex = 'M') and Sex = 'F';
```
