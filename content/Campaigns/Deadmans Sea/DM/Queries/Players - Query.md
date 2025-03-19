---
F_Exclude_Inactive: true
icon: RaPlayer
---
## Players

>[!info] Current Filters: F_Exclude_Inactive = `$= dv.current().F_Exclude_Inactive`

```dataviewjs 
var filterFile = dv.current()


if(filterFile.F_Exclude_Inactive == false) {
	dv.table(["Name", "Class", "Subclass", "Background", "Alignment", "Passive Perception", "Languages", "Active"], 
		dv.pages("#PC")
			.where(p => p.PC_Name)
			.map(p => [p.PC_Name, p.PC_Class, p.PC_Subclass, p.PC_Background, p.PC_Alignment, p.PC_Passive_Perception, p.PC_Languages, p.PC_Active]))
} else {
dv.table(["Name", "Class", "Subclass", "Background", "Alignment", "Passive Perception", "Languages", "Active"], 
		dv.pages("#PC")
			.where(p => p.PC_Name && p.PC_Active == true)
			.map(p => [p.PC_Name, p.PC_Class, p.PC_Subclass, p.PC_Background, p.PC_Alignment, p.PC_Passive_Perception, p.PC_Languages, p.PC_Active]))
}

```