---
created: 2025-02-11T11:16
updated: 2025-04-24T22:04
---

```dataview
table related-links
from ""
where !related-links or related-links = []
```

## Not tagged notes
```dataview
list
from [[tG not-tagged]]
```


## all ***newBorn*** are here:

```dataview
table status, created, updated
from ""
where status = "newBorn"
sort file.mtime desc
```


## all ***teenager*** are here:
```dataview
table status, created, updated
from ""
where status = "teenager"
sort file.mtime desc
```


## all ***adult*** notes are here:

```dataview
table status, created, updated
from ""
where status = "adult"
sort file.mtime desc
```


## all ***postponed*** notes are here:

```dataview
table status, created, updated
from ""
where status = "postponed"
sort file.mtime desc
```

## Recently edited notes
```dataview
TABLE updated AS "Last Updated"  
FROM ""  
WHERE !contains(file.folder, "97 - templates") AND !contains(file.folder, "96 - tags")  
SORT date DESC
LIMIT 5
```


## Most connected notes
```dataview
TABLE length(file.outlinks) + length(file.inlinks) as "Total Links", length(file.outlinks) as Outgoing, length(file.inlinks) as Backlinks
FROM ""
SORT length(file.outlinks) + length(file.inlinks) desc
LIMIT 50
```
