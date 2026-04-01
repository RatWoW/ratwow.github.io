---
layout: default
title: Cheatsheet
sidebar: mydoc_sidebar
---

# Cheatsheet and helpful links


## A quickguide for useful commands  

| Command | Purpose | Explanation |
| :--- | :--- | :--- |
| `.npc info` | Target info | Get the **DisplayID** and **GUID** and more of an existing NPC |
| `.gps` | Position info | Get MapID, zoneid, **X, Y, Z, ** and **Orientation** of an NPC, or yourself |
| `.npc add [id]` | Spawn Template | Quickly test the NPC template you just created |
| `.npc delete` | Remove NPC | Deletes the *spawned instance* you are currently targeting |
| `.lookup creature [name]` | Find a creatures ID by name | Use this ID to look at templates in Keira3  |
| `.mod speed [#]`, `.gm fly on`  | Move Quickly | Use these to traverse the world swiftly |
| `.server restart #` | Restart the server | Server must restart for new NPCs to be added. The # = Delay before restart |
| `.npc move (#)` | Temporary reposition | Moves an npc to your location until server restart. By selection or guid |
| `.npc set level [1-80]` | Modify Level | Temporarily changes an NPCs level (Inc mana, hp, etc) for testing |
| `.reload creature_template [#id]` | Reload the NPCs template | Will apply executed changes to the creature_template |  


## Quick references

**Faction IDs**:  
Friendly: `35`  
Hostile: `14` (Monster)  
Neutral: `7`    

**Map IDs**:  
Eastern Kingdoms: `0`  
Kalimdor: `1`  
Outland: `530`  
Northrend: `571`  


## Helpful link collection 

[Npc flag checker, for use with the .npc info command](https://www.azerothcore.org/flag-checker){:target="_blank"}  

[List of Emote ids](https://www.azerothcore.org/wiki/emotes){:target="_blank"}  

[TrinityCore World database](https://trinitycore.info/en/database/335/world/home){:target="_blank"}  

 
