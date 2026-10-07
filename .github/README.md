# Fast Forward - Character Pregeneration

A module for AzerothCore

## Description

This module allows for quick character generation for drop-in play or testing. After creating a reservation, the next matching character for the account will enter the world at the desired level, with:

- **Useable gear**: Dungeon and world drops already equipped
- **Abilities**: Core abilities already trained
- **Skills**: Core skills up-to-level
- **Mounts**: Appropriate mounts for level and zone
- **Bags**: A full complement of bags
- **Flight paths**: Flight paths already discovered

## How to install

Run the SQL manually or use the installer. Fast Forward requires a few new tables to track generation reservations.

## How to use this module

### Example

If you want to prep a level 60 frost mage, you might do the following:

```
ff prepfor archaicprose frost 60
```

This creates a reservation for your account that waits for the creation of a new mage character. You can still choose the race and appearance of your character in-game. On accepting character creation your new mage, the reservation will be claimed and your mage will be fast-forwarded to level 60.

|||
|---|---|
|![Image of character creation after selecting mage class](./assets/fastforward_creation.png)|![Image of character select screen with fast-forward mage](./assets/fastforward_created.png)|
|![Image of fast-forward mage in-game with skills and items](./assets/fastforward_entergame.png)||

### Spec Ids & Aliases

Nearly every fast-forward command requires a `specid` to make decisions about items. You can use either the numeric code or the string alias where a command calls for a `specid`.

| Class | Spec | Alias | specid |
| --- | --- | --- | --- |
| Warrior | Arms | `arms` | 1 |
| | Fury | `fury` | 2 |
| | Protection | `prot` `protw` | 3 |
| Paladin | Holy | `holy` `hpal` | 4 |
| | Protection | `prot` `protp` | 5 |
| | Retribution | `ret` | 6 |
| Hunter | Beast Mastery | `bm` | 7 |
| | Marksmanship | `mm` `marks` | 8 |
| | Survival | `sv` | 9 |
| Rogue | Assassination | `assassin` | 10 |
| | Combat | `combat` | 11 |
| | Subtlety | `subtlety` | 12 |
| Priest | Discipline | `disc` | 13 |
| | Holy | `holy` `hpriest` | 14 |
| | Shadow | `shadow` | 15 |
| Death Knight | Blood | `bdk` `blood` | 16 |
| | Frost | `frost` `fdk` | 17 |
| | Unholy | `uh` `uhdk` | 18 |
| Shaman | Elemental | `ele` `elem` | 19 |
| | Enhancement | `enh` | 20 |
| | Restoration | `resto` `rsham` | 21 |
| Mage | Arcane | `arc` | 22 |
| | Fire | `fire` | 23 |
| | Frost | `frost` | 24 |
| Warlock | Affliction | `aff` `afflict` | 25 |
| | Demonology | `demo` | 26 |
| | Destruction | `destro` | 27 |
| Druid | Balance | `bal` `boomy` | 28 |
| | Feral Combat (Cat) | `feral` `cat` | 29 |
| | Restoration | `resto` `tree` | 30 |
| | Feral Combat (Bear) | `bear` `guardian` | 99 |

Notice you can use certain terms like `frost` or `holy` as an alias despite it applying to multiple classes. The next character creation that matches the criteria will claim the reservation.

### Console

In the Worldserver console, you can use the following commands to create fast-forward reservations for specific accounts.

```
ff prepfor <accountname> <specid> <level>
```

You can cancel all reservations for an account in a similar way.

```
ff cancelfor <accountname>
```

### In-Game

The in-game commands are much the same.

```
ff prep <specid> <level>
```
```
ff cancel
```


## Future Development

Still working on additional features, like:

- Professions
- Talents
- Better tuning and configuration for gear