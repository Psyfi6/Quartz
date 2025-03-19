---
F_Exclude_Pre_Obsidian: false
icon: RiBook2Line
---
## Session Logs

>[!info] Current Filters: F_Exclude_Pre_Obsidian = `$= dv.current().F_Exclude_Pre_Obsidian`
```dataviewjs 
var filterFile = dv.current()

if(filterFile.F_Exclude_Pre_Obsidian == false) {
	dv.table(["Session #", "Session Date", "Attending Players", "Notable Events", "Pre Obsidian"], 
		dv.pages("#Deadmans-Sea-Session-Log")
			.where(c => c.Session_Date)
			.sort(c => c.Session_Date, 'asc')
			.map(c => [c.file.name, c.Session_Date, c.Attending_Players, c.Notable_Events, c.Pre_Obsidian]))
} else {
	dv.table(["Session #", "Session Date", "Attending Players", "Notable Events", "Pre Obsidian"], 
			dv.pages("#Deadmans-Sea-Session-Log")
				.where(c => c.Session_Date && c.Pre_Obsidian == false)
				.sort(c => c.Session_Date, 'asc')
				.map(c => [c.file.name, c.Session_Date, c.Attending_Players, c.Notable_Events, c.Pre_Obsidian]))
}
```
