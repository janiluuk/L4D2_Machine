# L4D2_Machine

Provides smart, deployable turrets and gatling guns with 8 different types of ammo:

- standard
- tesla
- nauseating
- fire
- laser
- freeze ray
- incentiary
- explosive


Gatling guns are weaker, have less ammo and cannot be moved.

Turrets can be carried around and can take more hit.
Both types explode after getting too much damage.

Supports classic mode, which simply spawns single portable turret.

Improved enemy detection and logic for prioritising attacks

Highly configurable

## Build Requirements

- [SourceMod](https://www.sourcemod.net/downloads.php) 1.11 or newer
- SourcePawn compiler (`spcomp`) from the same SourceMod release

## Compilation

1. Place the `.sp` files in your server's `addons/sourcemod/scripting` folder.
2. Run the compiler:

   ```sh
   spcomp l4d_machine_multi.sp
   ```

   or execute `compile.sh` to build everything in the folder.
3. The compiled `l4d_machine_multi.smx` will be written to `addons/sourcemod/plugins`.

## Installation

1. Copy `l4d_machine_multi.smx` to `addons/sourcemod/plugins` on your game server.
2. Copy `l4d_machine_multi.phrases.txt` to `addons/sourcemod/translations` for in‑game messages.
3. Restart the server or change map to load the plugin.

## Configuration

Common ConVars include:

| Cvar | Default | Description |
| --- | --- | --- |
| `l4d_machine_enable` | `1` | Enable or disable the plugin. |
| `l4d_machine_finale_only` | `0` | Restrict turrets to finale events. |
| `l4d_machine_ammo_count` | `2000` | Ammo per turret. |
| `l4d_machine_ammo_type` | `0` | Ammo type: 0 normal, 1 incendiary, 2 explosive. |
| `l4d_machine_health` | `2000` | Health per 50cal turret. |
| `l4d_machine_allow_carry` | `1` | Carry 50cal turret: 0 disabled, 1 anyone, 2 owner only. |
| `l4d_machine_allow_use` | `1` | Allow manual control of turrets. |
| `l4d_machine_limit` | `1` | Turrets allowed per user. |
| `l4d_machine_max_allowed` | `8` | Total turrets allowed in the game. |
| `l4d_machine_overheat` | `10.0` | Seconds before a turret overheats. |
| `l4d_machine_range` | `1000` | Enemy detection range. |
| `l4d_machine_enable_explosion` | `10` | Damage dealt when a turret explodes (0 disables). |

The source file contains many more options for fine‑tuning behaviour.

## Gameplay

- Admins spawn turrets with `sm_machine` and remove them with `sm_removemachine`.
- `sm_machinemenu` opens an in‑game menu for placing turrets.
- `sm_resetmachine` reloads settings and clears all placed turrets.
- Turrets can be carried, overheat after sustained fire, and support multiple ammunition types.
