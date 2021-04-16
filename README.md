105
```sql
Select Software.PName, Institute
from Software LEFT OUTER JOIN Studies
on Software.PName = Studies.PName;
```
