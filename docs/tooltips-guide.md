# Tooltips Guide

Tooltips are used in the Dota 2 user interface to communicate information about units, abilities, debuffs, almost everything.

## General Information

Tooltips are important for communicating information about the game to the players. They can be translated into multiple languages. Tooltips are compiled by a script, or by hand, into a file called "addon_language.txt". By default, OAA creates tooltips in English and translators use those files to make tooltips in these additional languages using Transifex translation software.

The data for the English tooltips has been generated by hand, however much of the data is in need of updating, correction, and other housekeeping. Authors should create or modify the individual files and run "generate-translations.js" to compile the main English tooltip file (addon_english.txt) for testing. Once tested, this file should not be committed along with the rest of the files as it would generate conflicts if another author also edited the file and attempted to merge it as well. To ensure you do not commit such changes you should undo any changes before committing all, or commit all the files separately.

## Directories

The main English tooltip file is located in ".../games/resource/". 
The individual English tooltip files are located in ".../games/resource/English/". The individual tooltips are divided into subfolders: ability, modifier, & npc.

### Ability

The Ability subfolder is where tooltips for **Hero and unit abilities** are located. These are the dialog boxes that appear when you mouse-over on a hero or unit's base abilities (ex. Berserker's Call).

### Modifier

The Modifier subfolder is where tooltips for **buffs & debuffs** are located. These are the dialog boxes that appear when you mouse-over on a buff or debuff (ex. if a unit is affected by Battle Hunger).

### NPC

The NPC subfolder is where tooltips for **units** are located. These are primarily used for the names of heroes, creeps, summons, and other units.

## Coded Information

Some of the information in Tooltips is coded and should not be translated. Many of the default codes are listed here: https://developer.valvesoftware.com/wiki/Dota_2_Tooltip_Formatting

### Key Value Pairs

Within most tooltip files you will find Keys with the prefix "DOTA_Tooltip_type_subtype_name_suffix". These are raw-value names taking various suffixes (ex. Description, duration, etc.)

- Type/subtype - Indicates whethere this tooltip is a modifier, item, ability, etc.

- Name - The name of the item, ability, etc.

- Suffixes
  - Default - Default suffixes include "Description, Note, and Lore.
  - Custom - These are taken from the "AbilitySpecial" Values found in the item or abilty's corresponding "npc_name" file.

## Syntax and Organization

The content of the individual English tooltip files is organized into pairs of strings enclosed in quotation marks. 

### Ability

The individual Ability tooltip files in OAA are divided into item abilities and unit abilities folders. Each individual Ability tooltip file contains the data for either a single item or set of cloned items (ex. force of nature or all 5 abyssal blades).

### Modifier

The individual Modifier tooltip files in OAA are also divided into item modifiers and unit modifiers folders. Each individual Modifier tooltip file contains the data for either a single item or set of cloned items (ex. decay)

### NPC

Each individual NPC tooltip file in OAA contains multiple units. The different files are: npc_bosses, npc_buildings, npc_creeps, npc_item_summons, and npc_unit_summons.

- The first string of each pair in an NPC tooltip file is the raw-data value, or internal name, given to the unit (ex. npc_dota_hero_axe).

- The second string of each pair in an NPC tooltip file is the name that should appear to players in the user interface (ex. Axe).

