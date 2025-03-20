---
icon: RiLandscapeLine
---

## Island


```dataviewjs

dv.table(["Name", "City", "Faction Presence"], 
	dv.pages("#Island")
		.where(i => i.Island_Name)
		.map(i => [i.Island_Name, i.Island_City, i.Island_Faction_Presence]))
```
