---
F_Island: 
F_City: 
F_Exists: true
icon: TiBuilding
---
## POIs

>[!info] Current Filters: F_Island = `$= dv.current().F_Island` | F_City = `$= dv.current().F_City` | F_Exists= `$= dv.current().F_Exists`

```dataviewjs
var filterFile = dv.current()
var activeFilters = []
if(filterFile.F_Island != null) activeFilters.push("F_Island")
if(filterFile.F_City != null) activeFilters.push("F_City")


if(activeFilters.length == 0) {
dv.table(["Name", "Island", "Faction", "City", "Exists"], 
	dv.pages("#POI")
		.where(p => p.POI_Name && p.POI_Exists == filterFile.F_Exists)
		.map(p => [p.POI_Name, p.POI_Island, p.POI_Faction, p.POI_City, p.POI_Exists]))
} else if(activeFilters.includes("F_Island") && activeFilters.length == 1) {
dv.table(["Name", "Island", "Faction", "City", "Exists"],
	dv.pages("#POI")
		.where(p => p.POI_Name && p.POI_Exists == filterFile.F_Exists && p.POI_Island && p.POI_Island.toString() == filterFile.F_Island.toString())
		.map(p => [p.POI_Name, p.POI_Island, p.POI_Faction, p.POI_City, p.POI_Exists]))
} else if(activeFilters.includes("F_City") && activeFilters.length == 1) {
dv.table(["Name", "Island", "Faction", "City", "Exists"],
	dv.pages("#POI")
		.where(p => p.POI_Name && p.POI_Exists == filterFile.F_Exists && p.POI_City && p.POI_City.toString() == filterFile.F_City.toString())
		.map(p => [p.POI_Name, p.POI_Island, p.POI_Faction, p.POI_City, p.POI_Exists]))
} else if(activeFilters.includes("F_Island") && activeFilters.includes("F_City") && activeFilters.length == 2) {
dv.table(["Name", "Island", "Faction", "City", "Exists"],
	dv.pages("#POI")
		.where(p => p.POI_Name && p.POI_Exists == filterFile.F_Exists && p.POI_Island && p.POI_Island.toString() == filterFile.F_Island.toString() && p.POI_City && p.POI_City.toString() == filterFile.F_City.toString())
		.map(p => [p.POI_Name, p.POI_Island, p.POI_Faction, p.POI_City, p.POI_Exists]))
}
```
