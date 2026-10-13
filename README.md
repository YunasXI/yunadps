# YunaDPS

A damage meter for **CatsEyeXI** (Ashita v4 and VanaCore), in the same look as [YunaGearOpt](https://github.com/YunasXI/yunagearopt).

- **Damage for your whole party and alliance**, pets and trusts included, even while you're not attacking yourself.
- **Current DPS / Total DPS**: the current (or last) fight, or every fight since you loaded it.
- **Details per player**: click a name for melee, ranged, weapon skills, magic, abilities, skillchains, accuracy, crit rate, average and best hits.
- **Enmity window**: its own window (the Enmity button). Attach it to the meter (it moves and sizes with it) or detach it and place it anywhere; it can also shrink to its own logo with the top 3. It shows estimated enmity on your target, worked out with the server's own (LandSandBoat) rules, and a red **TARGET** tag on whoever the monster is really attacking. Your row pulses orange when you're about to pull it.
- **Minimize to the logo**: a small logo with the top 3 under it. Click it to open the meter, drag it to move it.
- **Report**: click the logo in the meter to post the top 5 in party or linkshell chat: damage, accuracy (Acc) and magic accuracy (MAcc).
- **Resizable**: drag the corner and everything inside (text, bars, logo) grows or shrinks with the window.

## Install

1. Download `yunadps-x.y.z.zip` from [Releases](https://github.com/YunasXI/yunadps/releases).
2. Unzip it into `Ashita\addons\` (VanaCore: `Vanacore\addons\ashita\`), so you have `addons\yunadps\yunadps.lua`.
3. In game: `/addon load yunadps`

## Commands

| Command | What it does |
| --- | --- |
| `/dps` | Open or close the meter |
| `/dps min` | Shrink it to the logo and back |
| `/dps current` / `total` | Switch view |
| `/dps enmity` | Open or close the Enmity window |
| `/dps reset` | Clear every number |
| `/dps report [p \| l \| l2 \| s \| echo]` | Post the top 5 in party, linkshell, linkshell 2, say, or only for you |
| `/dps idle <seconds>` | How long with no damage before a fight ends (default 20) |
| `/dps help` | List the commands |

## Good to know

- The game only sends combat messages for fights near you, so alliance members fighting far away show up once they're close.
- Enmity is an **estimate**: other players' enmity gear can't be seen (it's taken as none, except main-job **Paladins**, who are counted with YunaGearOpt's PLD Enmity / Cure set, about +40 Enmity, for Provoke, Flash, Reprisal, other abilities, Atonement and cures) and the monster's level isn't known (your level is used). Who the monster is attacking (TARGET) is real.
- `enmity_data.lua` holds the fixed enmity of every spell and job ability, taken from LandSandBoat's `spell_list.sql` and `abilities.sql`.
