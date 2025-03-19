---
F_Island: 
icon: RiBuildingLine
---
## Cities
>[!info] Current Filters: F_Island = `$= dv.current().F_Island`

```dataviewjs
var filterFile = dv.current()
var activeFilters = []
if(filterFile.F_Island != null) activeFilters.push("F_Island")

 
if(activeFilters.length == 0) {
dv.table(["Name", "Island", "Faction Rulers", "Faction  Presence", "Renown"], 
	dv.pages("#City")
		.where(c => c.City_Name)
		.map(c => [c.City_Name, c.City_Island, c.City_Faction_Rulers, c.City_Faction_Presence, c.City_Renown]))
} else if(activeFilters.includes("F_Island") && activeFilters.length == 1) {
dv.table(["Name", "Island", "Faction_Rulers", "Faction_Presence", "Renown"],
	dv.pages("#City")
		.where(c => c.City_Name && c.City_Island && c.City_Island.toString() == filterFile.F_Island.toString())
		.map(c => [c.City_Name, c.City_Island, c.City_Faction_Rulers, c.City_Faction_Presence, c.City_Renown]))
}
```
