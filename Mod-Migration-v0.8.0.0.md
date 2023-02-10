# Mod Migration Guide

*This is for game version 0.8.0.0.*

## Weapon Classes

Weapon classes are now added to weapons as resources, just like you would add a weapon's upgrade or stats resource files. This is huge news!

Previously, to add a new weapon class, you'd have to edit the hardcoded `WeaponTyp` enum -- which made adding new classes very tricky, as it required a hacky workaround if you wanted to use ModLoader.


## Effects

### Stat Effect

The file *stat_effect.gd* no longer exists. This is important because it was a very commonly used file. It has been replaced with an expanded *effect.gd*, which now has `custom_key`, which behaves like `effect_key` from *stat_effect.gd* used to. Functionally there is no change, but you'll need to change some things in your files.

**Required Changes:**

- Replace `res://effects/items/stat_effect.gd` with `res://items/global/effect.gd`
- Rename `effect_key` to `custom_key` (but only in your mod's items!)

I recommend using VS Code's search and replace for this, and restricting your search to just your mod's own folder (as the string `effect_key` is still used elsewhere by vanilla code). Just be sure to backup your files and diff the results to make sure there's no issues!

You can also do this through the editor manually, ie. without using VS Code or some other external IDE, but note that when you replace a resource's script it will wipe any variables it was previously using. It is, however, the safer and more reliable approach.

Other effect files have been simplified into just using *effect.gd*, and these are covered next.


### Removed Effects

These effect files have been removed. Their effects have been replaced with just using *effect.gd* instead, which simplifies effect management.

```
additional_weapon_effect.gd
alien_eyes_effect.gd
anvil_effect.gd
dmg_when_death_effect.gd
dmg_when_pickup_gold_effect.gd
hp_cap_effect.gd
pacifist_effect.gd
remove_speed_effect.gd
replace_effect.gd
sign.gd
starting_item_effect.gd
stat_effect.gd
tier_effect.gd
turret_flame_effect.gd
unique_weapon_effect.gd
weapon_gain_effect.gd
```


### New Effects

These effect files are new:

```
chance_stat_damage_effect.gd
stat_cap_effect.gd
```


### Effects Changes

The following effects have been removed. Some of these didn't do anything (eg. `gambler`), and others have been renamed (eg. `dmg_when_death_from_luck` > `dmg_when_death`).

```
dmg_when_death_from_luck         -- replaced with dmg_when_death
dmg_when_pickup_gold_from_luck   -- replaced with dmg_when_pickup_gold
enemy_strength                   -- split into enemy_damage/enemy_health
gambler                          -- did nothing
leave_burning                    -- did nothing
```

These effects have been changed slightly:

```
remove_speed          -- Now defaults to [], previously defaulted to [0,0]
upgrade_random_weapon -- Now defaults to [], previously defaulted to 0
```

These effects have been added:

```
consumable_stats_while_max
convert_stats_half_wave
damage_against_bosses
dmg_on_dodge
dmg_when_death
dmg_when_heal
dmg_when_pickup_gold
enemy_damage
enemy_health
explode_on_consumable
extra_enemies_next_wave
giant_crit_damage
heal_on_crit_kill
heal_on_dodge
starting_weapon
stats_next_wave
structures_cooldown_reduction
temp_pct_stats_stacking
temp_pct_stats_start_wave
upgrade_random_weapon
```

## RunData

Effects have been split into 2 funcs. Previously they were all in `init_effects`, but now there's also `init_stats`.

This new `init_stats` comes with a huge benefit: TempStats can use any stat listed here! In the last version, TempStats was limited to just the primary stats that were defined in *temp_stats.gd*. But now, this change means that custom effects that give you temporary stats can now be a lot more varied, able to affect things like `burning_cooldown_reduction`, `number_of_enemies`, `knockback`, and new effects like `damage_against_bosses`.


## DebugService

DebugService has some cool new tweaks:

- "Debug Weapons" now works like "Debug Items" does, by adding the specified weapons only once. Previously it would keep adding them at the end of every wave.
- There's a new option, "Disable Saving" (`disable_saving`), which stops the game from saving data. This makes it possible to use the debug option "Unlock All Challenges" (`unlock_all_challenges`), which previously saved your game (as part of its functionality in `complete_challenge`), which could disrupt up your save file.


## Misc

*Extra changes that might affect your mods.*

Items don't have a `unique` bool anymore. Now they're set as unique if the max number (`max_nb`) is `1`.

Custom arg color/formatting is handled differently now. Instead of using `arg_signs`, now you use "Custom Arg" (`custom_arg`). To add one, increase the `custom_arg` array size, then right-click on an `[empty]` item and choose "*New CustomArg*" (it's just below the "*New Curve*" options). Like the old `arg_signs`, each arg that's displayed on your item's text has an index, starting from `0`. You can set the respective item's options to affect how that arg looks. While this is initially a little more complex, it does offer more options for arg formatting. For more info on what the options do, see `func get_arg_value` in *effect.gd*.