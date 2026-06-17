# Brothership – Classic Battle Controls (Luigi = B)

Restores the classic *Mario & Luigi* battle control scheme in **Mario & Luigi: Brothership** (Switch).

In the vanilla game, both brothers' battle menus are navigated and confirmed with **A**. This mod restores the original layout from previous games:

- **Luigi's battle menu is navigated and confirmed with B** (Mario stays on A).
- **Cancel / back becomes the Left Trigger (ZL)** (the same as *Bowser's Inside Story*).
- Luigi's dodges, counters, and attacks remain on **B**, as they already were.

Mario's controls are unchanged.

---

## Installation

The mod is three files:

```
LuigiBattleBtn_P.utoc
LuigiBattleBtn_P.ucas
LuigiBattleBtn_P.pak
```

### Emulator (Sudachi / Ryujinx / Yuzu-based)

1. Right-click the game → **Open Mod Data Location** (opens `.../load/01006D0017F7A000/`).
2. Create this folder structure inside it:
   ```
   ClassicBattleControls/romfs/Vermillion/Content/Paks/~mods/
   ```
3. Copy the three `LuigiBattleBtn_P.*` files into that `~mods\` folder.
4. Right-click the game → **Properties → Add-Ons / Mods** and make sure the mod is **enabled**.
5. Launch the game.

### Hardware (Atmosphere CFW)

Copy the three files to:

```
atmosphere/contents/01006D0017F7A000/romfs/Vermillion/Content/Paks/~mods/
```

---

## Compatibility

- **Game:** Mario & Luigi: Brothership (Title ID `01006D0017F7A000`)
- Built against the launch/base version of the game (Unreal Engine 4.27).
- Should be safe to add or remove at any time; it only changes a single battle-input setting and touches no save data. If you remove it, controls revert to vanilla.
- I HAVEN'T PLAYED THROUGH THE GAME YET so it may introduce a bug or two. I honestly have no idea

---

## How it works (for the curious)

The developers actually built the classic control scheme into the game and left it switched off. A battle settings object (`BattleDebugParam`) has a `LuigiButton` value that selects which face button drives Luigi's battle input; the game's confirm/cancel logic already branches on it, including the Left-Trigger cancel. This mod simply sets that value to its "B" option (its default is the A/Brothership behavior).

No game code is patched; only one Blueprint default value is changed, repacked into a standard IoStore (`_P`) mod.

---

## Credits

Me.
