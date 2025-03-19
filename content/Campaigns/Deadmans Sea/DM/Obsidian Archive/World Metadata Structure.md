
- Folders for each island including mainland and open water
- add folder notes and have each main folder be the primary info page of that island 
- meta data 
	- POIs should be tagged with their island and possibly city as well
	- Islands should have present factions, 
	- NPCs should be tied to POIs (optional), islands, factions
- Major Locations are things like a city that has many POIs within it
- Meta data for quests and just use dataview to make a list of them

# Metadata Structure

#### Quests ([[Admin/Templater Templates/Quest Template]])
- Quest_Name: quest 1
- Quest_Island: Saggeroth
- Quest_Location: POI 1 or City 1 (Wherethe quest objective is)
- Quest_Giver: NPC 1
- Quest_Available: True/False
	- NPC may have died or maybe a previous decision the party made changed this
- Quest_Status: Not Started/In progress/Finished


#### NPCs ([[Admin/Templater Templates/NPC Template]])
- NPC_Name: NPC 1
- NPC_Island: Saggeroth
- NPC_Location: POI 1
- NPC_Alive: True
- NPC_Faction: None
- NPC_Quests: Quest1, Quest2


#### POIs ([[Admin/Templater Templates/POI Template]])
- POI_Name: POI 1
- POI_Island: Saggeroth
- POI_Faction: None
- POI_Exists: True
- Store (Optional)
	- Store_Owner: NPC 1
	- Store_Type: Potions

#### Cities ([[Admin/Templater Templates/City Template]])
- City_Name: City 1
- City_Island: Saggeroth
- City_Faction_Rulers: Big Bad guys
- City_Faction_Presence: Big Bad guys, Small bad guys
	- This would be factions that are actively doing stuff in this area. Large operations. Not just random guys here and there.
- City_Renown: 6


#### Island ([[Admin/Templater Templates/Island Template]])
- Island_Name: POI 1
- Island_Major_Locaitons: City1
- Island_Faction_Presence: Big Bad guys, Small bad guys






