# Keira3 NPC Tutorial
https://www.azerothcore.org/Keira3/

## Overview 
This guide walks through making a basic friendly NPC with Keira3, including assigning values, giving it a gossip interaction, and spawning it in game


## Before you begin... 
Ensure Keira3 is connected to the correct database. If you created a new ssh tunnel after initial setup, you may need to update the port.
Log out of Keira3 and log back in to ensure the connection is active. If your database ever disconnects, Keira3 won't be able to push changes until you do

## Step 1: Creating a creature template 
In this guide, I will only list steps for necessary fields. At the end, I'll provide a cheatsheet for what each field actually means

- Open the Creature dropdown menu, and click Select Creature
  
- Under "Create New", you will see the number 9000000. This is the unique ID for your creature. Click "Select". You should be moved to the "Creature Template" tab
  
- Enter a name for your NPC. This will appear in game
  
- Click IconName, and scroll down to the chat bubble icon. This will appear on mouseover
  
- Set both the minlevel and maxlevel to the level you wish your NPC to be
  
- Set "expansion" to Wrath of the Lich King (Not entirely necessary, just most simple)
  
- Next to "faction", press the "..." icon. In the "faction name" section, type your desired faction. In my case, it will be Darnassus, which will show me the ID is 79
  
- Open the "npcflag" menu, and enable "GOSSIP", so the npc can be interacted with
  
- Move to "unit flags". I turned on IMMUNE_TO_PC, so nobody can kill our NPC
 
- Under flags_extra, enable the "civilian" flag, to reduce aggro range
 
- In behaviour, under AIName, select SmartAI. We'll configure this later

- Set gossip_menu_id to 140. This is a basic "greetings" message
  
- Scroll back up to the top and press "Execute". You should get a success notification in the top right

**Now you have a custom creature template.
Click the "creature template" tab on the left again, and a new array of menus will pop up, dedicated to editing the "creature" you just created.**
 
