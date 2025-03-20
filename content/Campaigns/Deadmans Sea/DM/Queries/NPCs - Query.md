---
F_Island: 
F_Location: 
F_Alive: true
icon: TiMichelinBibGourmand
---
## NPCs

>[!info] Current Filters: F_Island = `$= dv.current().F_Island` | F_Location = `$= dv.current().F_Location` | F_Alive= `$= dv.current().F_Alive`

```dataviewjs
var filterFile = dv.current()
var activeFilters = []
if(filterFile.F_Island != null) activeFilters.push("F_Island")
if(filterFile.F_Location != null) activeFilters.push("F_Location")


if(activeFilters.length == 0) {
dv.table(["Name", "Island", "Location", "Faction", "Renown", "Quests", "Alive"], 
	dv.pages("#NPC")
		.where(n => n.NPC_Name && n.NPC_Alive == filterFile.F_Alive)
		.map(n => [n.NPC_Name, n.NPC_Island, n.NPC_Location, n.NPC_Faction, n.NPC_Renown, n.NPC_Quests, n.NPC_Alive]))
} else if(activeFilters.includes("F_Island") && activeFilters.length == 1) {
dv.table(["Name", "Island", "Location", "Faction", "Renown", "Quests", "Alive"],
	dv.pages("#NPC")
		.where(n => n.NPC_Name && n.NPC_Alive == filterFile.F_Alive && n.NPC_Island && n.NPC_Island.toString() == filterFile.F_Island.toString())
		.map(n => [n.NPC_Name, n.NPC_Island, n.NPC_Location, n.NPC_Faction, n.NPC_Renown, n.NPC_Quests, n.NPC_Alive]))
} else if(activeFilters.includes("F_Location") && activeFilters.length == 1) {
dv.table(["Name", "Island", "Location", "Faction", "Renown", "Quests", "Alive"],
	dv.pages("#NPC")
		.where(n => n.NPC_Name && n.NPC_Alive == filterFile.F_Alive && n.NPC_Location && n.NPC_Location.toString() == filterFile.F_Location.toString())
		.map(n => [n.NPC_Name, n.NPC_Island, n.NPC_Location, n.NPC_Faction, n.NPC_Renown, n.NPC_Quests, n.NPC_Alive]))
} else if(activeFilters.includes("F_Island") && activeFilters.includes("F_Location") && activeFilters.length == 2) {
dv.table(["Name", "Island", "Location", "Faction", "Renown", "Quests", "Alive"],
	dv.pages("#NPC")
		.where(n => n.NPC_Name && n.NPC_Alive == filterFile.F_Alive && n.NPC_Island && n.NPC_Island.toString() == filterFile.F_Island.toString() && n.NPC_Location && n.NPC_Location.toString() == filterFile.F_Location.toString())
		.map(n => [n.NPC_Name, n.NPC_Island, n.NPC_Location, n.NPC_Faction, n.NPC_Renown, n.NPC_Quests, n.NPC_Alive]))
}
```
