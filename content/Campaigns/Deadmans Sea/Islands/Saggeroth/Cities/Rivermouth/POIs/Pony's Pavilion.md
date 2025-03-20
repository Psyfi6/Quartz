---
POI_Name: "[[Pony's Pavilion]]"
POI_Island: "[[Saggeroth]]"
POI_Faction: 
POI_City: "[[Rivermouth]]"
POI_Exists: true
tags:
  - POI
  - Store
icon: TiReportMoney
Store_Owner: "[[Mulu Chestroot]]"
Store_Type: Stable
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
Situated at the outskirts of the village, this humble stable emanates a rustic charm that beckons both travelers and locals alike. The structure, constructed from sturdy timber beams and thatched roofing, blends seamlessly with the surrounding countryside. Neatly stacked hay bales flank the entrance, offering a tantalizing scent that hints at the care bestowed upon its equine inhabitants. Inside, the spacious interior is filled with the comforting sounds of contented nickers and the rhythmic beat of hooves against packed earth. Each stall is meticulously maintained, bedded with fresh straw and adorned with colorful ribbons and trinkets. Soft lantern light bathes the stable in a warm glow, casting gentle shadows that dance upon the weathered wooden walls. At the heart of Pony's Pavilion stands a weathered trough, its surface worn smooth by generations of thirsty steeds. Despite its humble appearance, this cherished sanctuary is a testament to the bond between horse and rider, where trust is earned and companionship cherished

