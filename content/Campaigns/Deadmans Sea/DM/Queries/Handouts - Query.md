---
icon: RiFilePaper2Line
F_Handed_Out_Only: false
---

## Handouts

>[!info] Current Filters: F_Handed_Out_Only = `$= dv.current().F_Handed_Out_Only`

```dataviewjs 
var filterFile = dv.current()


if(filterFile.F_Handed_Out_Only == false) {
	dv.table(["Name", "Handed Out"], 
		dv.pages("#Handout")
			.where(h => h.Handout_Name)
			.map(h => [h.Handout_Name, h.Handed_Out]))
} else {
	dv.table(["Name", "Handed Out"], 
		dv.pages("#Handout")
			.where(h => h.Handout_Name && h.Handed_Out == true)
			.map(h => [h.Handout_Name, h.Handed_Out]))
}

```