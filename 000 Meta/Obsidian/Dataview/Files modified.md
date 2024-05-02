List of N most recently modified files

```dataview
table dateformat(file.mtime, "dd-MMM-yy - HH:mm") as "Modified", tags
from ""
SORT file.mtime DESC
limit 25
```