---
POI_Name: "[[Glimmering Gear]]"
POI_Island: "[[Saggeroth]]"
POI_Faction: 
POI_City: "[[Rivermouth]]"
POI_Exists: true
tags:
  - POI
  - Store
icon: TiReportMoney
Store_Owner: "[[Tharendel Swiftfoot]]"
Store_Type: General
Store_Renown: -2
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
Welcome to Glimmering Gear, contains the occasional magical item while still offering all the mundane items a traveler might need on their journey. The store is tucked away in a cozy corner of a medieval town, nestled between a blacksmith and a bustling tavern. The entrance is a beautifully carved wooden door, adorned with intricate runes and symbols that seem to shimmer and dance in the sunlight.

As you push open the door, you are greeted by the warm, inviting aroma of burning candles and fresh herbs. The interior is dimly lit, yet cozy, with soft, glowing lanterns hanging from the wooden beams above. The walls are lined with shelves upon shelves of various items, each meticulously organized and tagged with enchanted price labels that update in real-time.

The air is filled with the gentle hum of magical energy, as the enchantments woven into each item gently pulsate with an otherworldly aura. The floor beneath your feet is made of well-worn, dark hardwood planks, worn smooth with age and use. 


## Reserved Items
Items currently on hold: 
+1 Glaive - 1020 GP
+1 Rapier - 1025 GP
+1 Crossbow (hand) - 1075 GP



