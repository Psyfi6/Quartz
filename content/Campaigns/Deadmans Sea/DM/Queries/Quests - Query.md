---
F_Island: 
F_Status: Not Started
F_Available: true
icon: TiBookmarkQuestion
---
## Quests

> [!info] Current Filters: F_Island = `$= dv.current().F_Island` | F_Status = `$= dv.current().F_Status` | F_Available = `$= dv.current().F_Available`

```dataviewjs
var filterFile = dv.current()
var activeFilters = []
if(filterFile.F_Island != null) activeFilters.push("F_Island")
if(filterFile.F_Status != null) activeFilters.push("F_Status")

if(activeFilters.length == 0) {
dv.table(["Name", "Island", "Location", "Giver", "Available", "Status"], 
	 dv.pages("#Quest")
		.where(q => q.Quest_Name && q.Quest_Available == filterFile.F_Available)
		.map(q => [q.Quest_Name, q.Quest_Island, 
		q.Quest_Location, q.Quest_Giver, q.Quest_Available, 
		q.Quest_Status])
		)
} else if(activeFilters.includes("F_Island") && activeFilters.length == 1) {
dv.table(["Name", "Island", "Location", "Giver", "Available", "Status"], 
	 dv.pages("#Quest")
		.where(q => q.Quest_Name && q.Quest_Available == filterFile.F_Available
				&& q.Quest_Island && q.Quest_Island.toString() == filterFile.F_Island.toString()
				)
		.map(q => [q.Quest_Name, q.Quest_Island, 
		q.Quest_Location, q.Quest_Giver, q.Quest_Available, 
		q.Quest_Status])
		)
} else if(activeFilters.includes("F_Status") && activeFilters.length == 1) {
dv.table(["Name", "Island", "Location", "Giver", "Available", "Status"], 
	 dv.pages("#Quest")
		.where(q => q.Quest_Name && q.Quest_Available == filterFile.F_Available
				&& q.Quest_Status && q.Quest_Status == filterFile.F_Status
				)
		.map(q => [q.Quest_Name, q.Quest_Island, 
		q.Quest_Location, q.Quest_Giver, q.Quest_Available, 
		q.Quest_Status])
		)
} else if(activeFilters.includes("F_Island") && activeFilters.includes("F_Status") && activeFilters.length == 2) {
dv.table(["Name", "Island", "Location", "Giver", "Available", "Status"], 
	 dv.pages("#Quest")
		.where(q => q.Quest_Name && q.Quest_Available == filterFile.F_Available
				&& q.Quest_Status && q.Quest_Status == filterFile.F_Status
				&& q.Quest_Island && q.Quest_Island.toString() == filterFile.F_Island.toString()
				)
		.map(q => [q.Quest_Name, q.Quest_Island, 
		q.Quest_Location, q.Quest_Giver, q.Quest_Available, 
		q.Quest_Status])
		)
}




```
