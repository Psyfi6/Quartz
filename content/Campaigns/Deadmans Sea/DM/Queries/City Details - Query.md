---
F_City_Name: "[[Rivermouth]]"
icon: TiInfoSquare
---
## City Details

>[!info] Current Filters: City_Name = `$= dv.current().F_City_Name`

## POIs
```dataviewjs
var filterFile = dv.current()


dv.table(["Name", "Island", "Faction", "City", "Exists"], 
	dv.pages("#POI")
		.where(p => p.POI_Name && p.POI_City && p.POI_City.toString() == filterFile.F_City_Name.toString())
		.map(p => [p.POI_Name, p.POI_Island, p.POI_Faction, p.POI_City, p.POI_Exists]))


```

## NPCs

```dataviewjs
var filterFile = dv.current()
var city_POI_Name = []
var NPC_Name = []

// find all POIs that belong to the filtered city
var POI_Count = dv.pages("#POI").length
for(let i = 0; i < POI_Count; i++) {
	if(dv.pages("#POI")[i].POI_Name && dv.pages("#POI")[i].POI_City && dv.pages("#POI")[i].POI_City.toString() == filterFile.F_City_Name.toString()) {
		city_POI_Name.push(dv.pages("#POI")[i].POI_Name) 
	} 
}

var NPC_Count = dv.pages("#NPC").length
for(let i = 0; i < NPC_Count; i++) {
	var temp_NPC = dv.pages("#NPC")[i]
	if(temp_NPC.NPC_Name) {
		for(let ii = 0; ii < city_POI_Name.length; ii++) {
			if(temp_NPC.NPC_Location && city_POI_Name[ii].toString() == temp_NPC.NPC_Location.toString()) {
				NPC_Name.push(temp_NPC.NPC_Name)			
			}
		}
	}
}


dv.table(["Name", "Island", "Location", "Faction", "Renown", "Quests", "Alive"], 
	dv.pages("#NPC")
		.where(n => n.NPC_Name && n.NPC_Location && NPC_Match(n.NPC_Name))
		.map(n => [n.NPC_Name, n.NPC_Island, n.NPC_Location, n.NPC_Faction, n.NPC_Renown, n.NPC_Quests, n.NPC_Alive]))



function NPC_Match(Query_NPC_Name) {
	for(let i = 0; i < NPC_Name.length; i++) {
		if (Query_NPC_Name.toString() == NPC_Name[i].toString()) {
			return true
		}
	}
}
```

## Stores
```dataviewjs
var filterFile = dv.current()


dv.table(["Name", "Island", "Store Type", "Store Owner", "Store Renown", "Faction", "City", "Exists"], 
	dv.pages("#Store")
		.where(p => p.POI_Name && p.POI_City.toString() == filterFile.F_City_Name.toString())
		.map(p => [p.POI_Name, p.POI_Island, p.Store_Type, p.Store_Owner, p.Store_Renown, p.POI_Faction, p.POI_City, p.POI_Exists]))


```