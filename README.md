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
