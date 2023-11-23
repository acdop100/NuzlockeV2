# Pokeemerald-Expansion Changelog

# Version 1.6.2

## 🌋 *IMPORTANT CHANGES* 🌋
### Battle changes
* Battler Types are now obtained via `GetBattlerType` instead of `gBattleMons[battlerId].type1/2/3` to better consider Roost. Be sure to update your custom battle effects to account for this change.

## 🧬 General 🧬
### Fixed
* Fixed Cheat Start not initiating time-based events by @AsparagusEduardo in https://github.com/rh-hideout/pokeemerald-expansion/pull/3446

## 🐉 Pokémon 🐉
### Changed
* Updated Cresselia's base stats to Gen 9 by @LOuroboros in https://github.com/rh-hideout/pokeemerald-expansion/pull/3419
* Updated Zacian/Zamazenta base stats to Gen 9 by @AsparagusEduardo in https://github.com/rh-hideout/pokeemerald-expansion/pull/3421
### Fixed
* Fixed Kleavor, Hisuian Sneasel and Sneasler missing their SV abilities  by @LOuroboros in https://github.com/rh-hideout/pokeemerald-expansion/pull/3391
* Fixed Bergmite/Avalugg old and updated egg groups being switched by @AsparagusEduardo in https://github.com/rh-hideout/pokeemerald-expansion/pull/3380

## 🤹 Moves 🤹
### Changed
* Quick Draw now uses weighted RNG by @Bassoonian in https://github.com/rh-hideout/pokeemerald-expansion/pull/3399
* Added `IS_BATTLER_TYPELESS` macro that checks if the specified battler has no valid type by @LOuroboros in https://github.com/rh-hideout/pokeemerald-expansion/pull/3303
### Fixed
* Fixed Protect failing if the user flinched on the previous turn by @DizzyEggg in https://github.com/rh-hideout/pokeemerald-expansion/pull/3345
* Fixed entry hazards not working properly being cleared on switch-in by @DizzyEggg in https://github.com/rh-hideout/pokeemerald-expansion/pull/3316
    * This includes Toxic Spikes not working if Pecha Berry actived on the previous turn.
* Fixed Roost overwriting other type changing at the end of the turn (Soak, Forest's Curse, Color Change, etc.) by @BLourenco in https://github.com/rh-hideout/pokeemerald-expansion/pull/3258
    *  Now it suppresses the user's Flying-type rather than remove and re-add it.
* Fixes Salt Cure visual bug if mon fainted by direct attack by @AlexOn1ine in https://github.com/rh-hideout/pokeemerald-expansion/pull/3388
* Fixed Purifying Salt not preventing the use of Rest by @Bassoonian in https://github.com/rh-hideout/pokeemerald-expansion/pull/3399
* Fixed Make it Rain lowering Sp. Attack twice if hitting 2 targets in double battles by @AlexOn1ine in https://github.com/rh-hideout/pokeemerald-expansion/pull/3441
* Fixed Reflect Type not properly handle 3rd types by @LOuroboros in https://github.com/rh-hideout/pokeemerald-expansion/pull/3303
* Fixed form change triggered by switching not occuring when using moves like U-Turn or Baton Pass by @AlexOn1ine in https://github.com/rh-hideout/pokeemerald-expansion/pull/3463
* Fixed Last Resort not counting Sleep Talk as used for its effect by @DizzyEggg in https://github.com/rh-hideout/pokeemerald-expansion/pull/3378

## 🎭 Abilities 🎭
### Changed
* Removed unused `STATUS3_CANT_SCORE_A_CRIT` by @AlexOn1ine in https://github.com/rh-hideout/pokeemerald-expansion/pull/3377
* Moved Beads of Ruin and Sword of Ruin damage to the appropiate damage modifier functions by @kittenchilly in https://github.com/rh-hideout/pokeemerald-expansion/pull/3415
### Fixed
* Fixed Intimidate increasing the attack of both opponents if one of them has Contrary in double battles by @DizzyEggg in https://github.com/rh-hideout/pokeemerald-expansion/pull/3365
* Fixed Battle/Shell Armor not preventing critical hits by @AlexOn1ine in https://github.com/rh-hideout/pokeemerald-expansion/pull/3377
* Fixed Rivalry's effect being reversed by @AsparagusEduardo in https://github.com/rh-hideout/pokeemerald-expansion/pull/3381
* Fixed Rivalry lowering attack if either attacker or target were genderless by @AsparagusEduardo in https://github.com/rh-hideout/pokeemerald-expansion/pull/3381
* Fixed missing Poison Heal Ability Popup by @Bassoonian in https://github.com/rh-hideout/pokeemerald-expansion/pull/3385
* Fixed Parental Bond not working at all by @AsparagusEduardo in https://github.com/rh-hideout/pokeemerald-expansion/pull/3417
* Fixed Beads of Ruin and Sword of Ruin damage modifiers by @kittenchilly in https://github.com/rh-hideout/pokeemerald-expansion/pull/3415
* Fixed Sheer Force not negating effects that benefit the user (eg. Flame Charge, Power-Up Punch) by @DizzyEggg in https://github.com/rh-hideout/pokeemerald-expansion/pull/3378
* Fixed Strength Sap not healing the user when used on a Substitute by @DizzyEggg in https://github.com/rh-hideout/pokeemerald-expansion/pull/3486
* Fixed Substitute showing the "took damage for" message if Strength Sap was used on it by @DizzyEggg in https://github.com/rh-hideout/pokeemerald-expansion/pull/3486
* Fixed Weak Armor interrupting Multi Hit moves by @DizzyEggg in https://github.com/rh-hideout/pokeemerald-expansion/pull/3497

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

- Added global PC access
- Changed Day/Night cycles https://github.com/pret/pokeemerald/wiki/Change-Time-Based-Evolution-Times
- Ability to fly from pokemon moves menu
- Upgraded audio engine
- Faster healing
- Catch both Latios and Latias
- Press B to hover "run" in wild battle
- Other misc. changes and fixes
