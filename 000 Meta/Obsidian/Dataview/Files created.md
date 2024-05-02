List of 50 most recently created files

```dataview
table dateformat(file.ctime, "dd-MM-yy - HH:mm") as "Created", dateformat(file.mtime, "dd-MM-yy - HH:mm") as Modified, tags
SORT file.ctime DESC
limit 50
```
