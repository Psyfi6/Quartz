---
icon: RiShoppingBagLine
---
## Items

```dataviewjs
dv.table(["Name"], 
	dv.pages("#Item")
		.where(i => i.Item_Name)
		.map(i => [i.Item_Name]))
```