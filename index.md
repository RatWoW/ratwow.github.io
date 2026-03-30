# Keira3 NPC Tutorial
https://www.azerothcore.org/Keira3/

## Overview 
This guide walks through making a basic friendly NPC with Keira3, including assigning values, giving it a model, a gossip interaction, and spawning it in game


## Before you begin... 
Ensure Keira3 is connected to the correct database. If you created a new ssh tunnel after initial setup, you may need to update the port
Log out of Keira3 and log back in to ensure the connection is active. If your database ever disconnects, Keira3 won't be able to push changes until you do

## Step 1: Creating a creature template 
  In this guide, only necessary fields will be used. Later, a cheatsheet will be provided for what each field actually means

i. Open the Creature dropdown menu, and click Select Creature
  
ii. Under "Create New", you will see the number 9000000. This is the unique ID for your creature. Click "Select". You should be moved to the "Creature Template" tab
  
iii. Enter a name for your NPC. This will appear in game
  
iv. Click IconName, and scroll down to the chat bubble icon. This will appear on mouseover
  
v. Set both the minlevel and maxlevel to the level you wish your NPC to be
  
vi. Set "expansion" to Wrath of the Lich King (Not entirely necessary, just most simple)
  
vii. Next to "faction", press the "..." icon. In the "faction name" section, type your desired faction, E.G Darnassus (79), or Orgrimmar (29)
  Faction determines what the NPC is friendly or hostile to. 35 is the ID for a "friendly to all" NPC
  
viii. Open the "npcflag" menu, and enable "GOSSIP", so the NPC can be interacted with. Not necessary for non-interactable NPCs
  
ix. Move to "unit flags". Enable IMMUNE_TO_PC, so no player characters can attack the NPC (Optional)
 
x. Under flags_extra, enable the "civilian" flag, to reduce aggro range
 
xi. In behaviour, under AIName, select SmartAI. This will be used to make the NPC emote when you talk to it. We'll configure this later

xii. Set gossip_menu_id to 140. This ID links to the basic "greetings" message
  
xiii. Scroll back up to the top and press "Execute". You should get a success notification in the top right

**Now you have a custom creature template.
Click the "creature template" tab on the left again, and a new array of menus will pop up, dedicated to editing the "creature" you just created**


## Step 2: Giving your NPC a model

Click on "Template Model"
The important field here is "CreatureDisplayId". It directly translates to an existing NPC model
The easiest way to get a specific model's ID is to find them in game

i. Click on an NPC, and use the command ```.npc info```. This will list everything about them, including displayid

ii. Click "Add New Row" to add the displayid to your template
  
The model should appear in the viewer at the bottom. Click Execute


## Step 3: Using SmartAI to make the NPC use an emote when interacted with
This is simpler than it looks. For our purpose, most fields go unused

i. Click add row

 ### *General tab*

ii. In "Event", scroll down to "64 - GOSSIP_HELLO". This refers to when the "gossip" menu is opened

iii. In "Action" select "5 - PLAY_EMOTE"

iv. In "Target" select "1 - SELF"

 ### *Action tab*

This is where you can select which emote the NPC plays. 

https://www.azerothcore.org/wiki/emotes

There is a list of EmoteIds here. Pick one

Click Execute


## Step 4: GUID and spawning your NPC

What is a GUID? Every spawned creature has a unique GUID, that is assigned to each instance of it. A creature won't spawn if it has the same GUID as another
At the bottom of all of the Keira3 menus, there is an "unused GUIDs" finder. Click "Search" and copy one

i. Now move to the "Spawn" tab

ii. Add new row, paste the GUID

iii. In game, type the ```.gps``` command while you're standing exactly where you want your NPC. This will give you the information for mapid, zoneid, areaid, positions, and orientation

![.gps command demo](images/gpsdemo.png)

### Notes
- Make sure you don't have any NPC selected when using the command, as it will give you their position instead of yours
- Use X, Y, and Z, **not** ZoneX, ZoneY, or Ground Z
- If the yellow is hard to read, you can right click "General" > Settings > Other and change the colour of "System Messages"

iv. Click Execute. Now restart your worldserver

The process is complete, and you now have a new friendly NPC to populate the world


 
