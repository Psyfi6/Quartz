---
icon: TiUsersGroup
---
## Factions

```dataviewjs
var filterFile = dv.current()

 

dv.table(["Name", "Parent Faction", "Type", "Presence", "Renown"], 
	dv.pages("#Faction")
		.where(f => f.Faction_Name)
		.sort(f => f.Faction_Name, 'desc')
		.map(f => [f.Faction_Name, f.Faction_Parent, f.Faction_Type, f.Faction_Presence, f.Faction_Renown]))

```