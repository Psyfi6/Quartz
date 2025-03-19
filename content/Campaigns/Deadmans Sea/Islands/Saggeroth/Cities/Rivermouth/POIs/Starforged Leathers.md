---
POI_Name: "[[Starforged Leathers]]"
POI_Island: "[[Saggeroth]]"
POI_Faction: "[[Deadmans Sea/World Info/Faction Info/Factions/Minor/The Iron Legion]]"
POI_City: "[[Rivermouth]]"
POI_Exists: true
tags:
  - POI
  - Store
icon: TiReportMoney
Store_Owner: "[[Dromac Zumruvo]]"
Store_Type: Blacksmith & Leatherworker
Store_Renown: 0
---
## Renown
```dataviewjs
var Store_Renown =  dv.current().Store_Renown

var NPC_Renown = dv.page(dv.current().Store_Owner.path).NPC_Renown

var Faction_Renown = 0
if(dv.current().POI_Faction) {
Faction_Renown = dv.page(dv.current().POI_Faction.path).Faction_Renown
}

var Faction_Renown_Parent = 0
if(dv.current().POI_Faction && dv.page(dv.current().POI_Faction.path).Faction_Parent) {
Faction_Renown_Parent = dv.page(dv.page(dv.current().POI_Faction.path).Faction_Parent).Faction_Renown
}

var Combined_Renown = Store_Renown + NPC_Renown + Faction_Renown + Faction_Renown_Parent



dv.paragraph("Combined [[Renown]]: " + Combined_Renown)

if(Combined_Renown < 0) {
dv.span("[[Renown]] Impact: " + (Combined_Renown * -2.5) + "% increased cost")
} else if(Combined_Renown > 0) {
dv.span("[[Renown]] Impact: " + (Combined_Renown * 2.5) + "% decreased cost")
}

```
## Description
A sturdy stone building adorned with wrought iron fixtures, Starforged Leathers stands as a beacon of craftsmanship in the village. The clang of hammers against anvils reverberates from within, mingling with the rhythmic scrape of leather being worked. Display racks showcase finely crafted armor and leather goods, each piece bearing intricate designs and expert stitching. The air is thick with the scent of smoldering embers and tanned hides, while the glow of the forge bathes the interior in a warm, flickering light. Amidst the tools and workbenches, skilled artisans ply their trade, shaping raw materials into works of art destined to withstand the trials of adventuring in the wilds.


