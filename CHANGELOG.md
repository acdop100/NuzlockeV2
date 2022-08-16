

item_use.c:
- Flag check for when you are catching a pokemon to see if it is the first on your route

battle_script_commands.c:
- Flag check to delete a pokemon once it faints in battle

overworld.c:
- Flag check for what happens when a whiteout occurs (delete save or normal whiteout)

region_map.c:
- `sRegionMapSectionWhereCaught`: Array of each route to check if we have seen a wild pokemon yet
- `HasCaughtMonInRegion`: checks `sRegionMapSectionWhereCaught` and returns T

main_menu.c:
- Added new menu choice: 'NUZLOCKE OPTIONS`
- This menu gives users the ability to change what parts of the Nuzlocke challenge they want to conquer

globals.h:
- Added storage spaces for Nuzlocke options

flags.c:
- added flags for each Nuzlocke feature

nuzlock_options_menu.c:
- Includes functions necessary to facilitate changing Nuzlocke options
    - `DELETE FAINT`: Deletes a pokemon's data when it faints in battle
    - `WHITEOUT DELETE`: deletes your save file after you white out with no pokemon left (party or PC)
    - `WHITEOUT+`: Additional whiteout option to delete the save if you only whiteout your party, even if you have PC pokemon left
    - `SINGLE CATCH`: makes it so you can only catch the first wild pokemon you see on each route
    - `STARTER CHOICE`: Whether you can pick your starter or if it is chosen for you based on your trainer ID

strings.c:
- Added strings for nuzlocke options menu
- Added support for changing pokemon name in party menu
- Changed default trainer names :P

pokemon.c:
- Changed day/night cycle evolutions to be more in line with current gen games

field_player_avater.c:
- Added better reflection system

main.c:
- Replaced vsync call to increase speed/efficiency

event_object_movement.c:
- Edited `DoGroundEffects` functions to keep camera from making waves

data/scripts/pkmn_center_nurse.inc:
- Changed healing functionality to be instant when you talk to Nurse Joy

save.h:
- Increased size of save file space available

party_menu.c:
- Added support to change pokemon name in party menu

