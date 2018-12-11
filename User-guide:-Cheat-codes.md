Like many emulators, OpenEmu allows the use of [cheat codes](http://en.wikipedia.org/wiki/Cheating_in_video_games) to change the way a game plays (invincibility, level skipping, etc.).

Cheat-code support in OpenEmu is determined by each [core](https://github.com/OpenEmu/OpenEmu/wiki/User-guide:-Preferences:-Cores) and its underlying emulation code. Some cores do not support cheat codes; OpenEmu knows which cores those are, and its cheat functionality will not be available when they are in use.

### Finding cheats

A good resource for finding cheat codes is [GameHacking.org](http://gamehacking.org).

**Important**: Be sure that the codes you use are for the proper region and revision of the game you are playing. Since there can be different versions of a game for various locales, there are also different codes that have to be used. For example: cheat codes for a US version of a game may not work for an EU version of a game.

### Adding cheats

To add a cheat code, you must be running a game. Within the game window, move the mouse to produce the [HUD bar](#), and click the cog/gear icon near the center. If the core supports cheat codes, a menu item called *Select Cheat* will be available. In this menu, there will be another item labelled *Add Cheat...* — click here to input a new code.

![HUD Select Cheat menu](http://i.imgur.com/nz9wA5M.png)

In the dialogue that opens, you can enter a name for the cheat (to identify it in the *Select Cheat* menu), as well as the code itself. Enter codes in whatever format the core supports; usually, these formats will be identical to the most popular cheat devices available for the system in question (such as Action Replay or Game Genie). You can also choose to enable a cheat right away or wait to enable it later.

![Add Cheat dialogue](http://i.imgur.com/6nQUt58.png)

The following table shows a list of supported code types:

Console | Cheat type | Example code
--- | --- | ---
Game Boy | Game Genie | FA1-B9C-4C1
Game Boy (Color) | GameShark | 0101CEC1
Game Boy Advance | GameShark Advance/Action Replay (v1/v2) | CD93194F 089CE0B4
Game Boy Advance | Action Replay MAX (v3/v4) | 4E26D7A1 6D72DA8B
Game Boy Advance | Codebreaker/GameShark SP/Xploder | A62B1D67EB2D
Game Gear | Action Replay | 00D159:98
Game Gear | Game Genie | 3A7-E4C-2A2
Nintendo (NES) / Famicom | Game Genie | APEETPEY
Nintendo (NES) / Famicom | Raw | C900:ED
Nintendo (NES) / Famicom | Raw (with compare) | 810E?F0:10
Nintendo 64 | GameShark | 8033B177 0015
Nintendo DS | Action Replay | 22085A50 00000001
Sega Genesis / Mega Drive<br>Sega CD / Mega CD | Action Replay | FFFE21:0032
Sega Genesis / Mega Drive<br>Sega CD / Mega CD | Game Genie | NN8A-AADN
Sega Master System | Action Replay | 00C094:01
Sega Master System | Game Genie | 00D-70F-E68
Super Nintendo (SNES) | Action Replay | 7E1490:FF
Super Nintendo (SNES) | Game Genie | 14B4-6F07

For multi-line codes, use a plus (`+`) to separate each line. For example: `AVSOYOSZ+ELEAPOZE+AIEAZPAP`

### Using cheats

After you've added a cheat, you'll need to enable it if you haven't already. Return to the *Select Cheat* menu, and you will now see the cheat that was just added in the list. Click on it to enable it. If you need to disable it later, simply return to this menu and click it again.

![HUD Select Cheat menu with cheat added](http://i.imgur.com/Lgwe3Lx.png)

### GBA cheats
**TL;DR only Codebreaker/GameShark SP and GameShark Advance cheats are supported for GBA. Not Action Replay v3.**

If the code is Action Replay v3/v4, you will have to instead use a GameShark equivalent code or attempt to convert it here: http://gamehacking.org/?sys=gba

This is because we cannot automatically detect if a code is AR v3 since they are the same length as the AR/GameShark v1/v2 (16 chars), and v3 uses different encryption.

There is no good way to detect v3 unless you explicitly tell mGBA that the code is v3. There are numerous problems with front ends and codes floating around the web:
* Cheat code websites usually all have AR/GS formatted as XXXXXXXX YYYYYYYY and don't tell you which type of AR/GS, unless its a good cheat code website such as gamehacking.org which will denote AR/GS v1/v2 codes as **AR12** and AR v3 as **AR34**.

* Many cheat code websites have codes mislabeled or plain wrong, without noting which region and revision they are.

* VBA standalone expects AR/GS v1/v2 formatted as XXXXXXXXYYYYYYYY (no spaces) but AR v3 formatted as XXXXXXXX YYYYYYYY (8 chars separated by a space). But it doesn't tell you this in the UI!

* GBA4iOS forces all 16 char AR/GS as "AR v3" which is wrong and breaks the use of valid AR/GS v1/v2 codes. (it also incorrectly states GameShark SP codes aren't supported when those are actually the same as Codebreaker, 12 chars minus the space).

So, which cheat codes can 'just work' with OpenEmu's mGBA core plugin?
* Raw Address:Value cheat codes (11, 13 or 17 chars including the colon).
* Codebreaker/GameShark SP codes (these are 12 chars, minus the space).
* GameShark Advance/Action Replay v1/v2 codes (these are 16 chars, minus the space).

What doesn't work?
* Action Replay v3 codes (these are also 16 chars, minus the space).

Note: you don't have to worry about adding spaces in your cheats that you input for OpenEmu.

More general info on GBA cheat types here: http://doc.kodewerx.org/hacking_gba.html

### Limitations

OpenEmu currently has no way of saving cheats — any codes entered will be lost as soon as you leave the game. Improved cheat-code functionality (potentially including a built-in database of codes) is planned for a future version of the application.