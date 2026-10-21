# Oh Sir Access

Blind accessibility mod for Oh...Sir! The Insult Simulator (Steam). Download the zip from the Releases page.

```
Oh Sir Access 0.5.4
A screen reader accessibility mod for Oh...Sir! The Insult Simulator (Steam, Windows).

What it does
The mod makes the game playable without sight. It speaks the menus, settings, screen titles, results and loading hints, and gives you keyboard commands to hear and pick insult phrases during a match. It announces every phrase either player adds, grammar mistakes, damage, combos, pride and who won. In offline games the turn timer is doubled by default. Online games always use the normal timer.

Speech works with:
- JAWS (tested). The mod talks to JAWS directly.
- NVDA, through the NVDA controller client.
- Other screen readers supported by the Tolk library, such as System Access and Dolphin.
- No screen reader: Windows voices (SAPI) are used instead.
The right method is picked automatically. If you hear nothing, press F11 in the game (see below).

Easy install
1. Before extracting, right click the zip file, choose Properties, check Unblock near the bottom of the General tab, and choose OK. This stops Windows warnings later. If there is no Unblock box, skip this step.
2. Extract the zip to any folder, for example your Downloads folder.
3. Close the game if it is running. Open the extracted folder and run Install.bat.
4. If you hear "Windows protected your PC", choose More info, then Run anyway. This appears because the file came from the internet and is not signed. Install.bat and OhSirAccess_Setup.ps1 are plain text files: you can open them in Notepad to see exactly what they do.
5. The installer finds Steam and the game by itself, on any drive and in any Steam library folder. If it cannot, it asks you to type or paste the game folder path. It then copies the mod files and says Success or Failed, with the folder it used. Press any key to close the window.
6. Start your screen reader, then start the game from Steam as usual. After a few seconds you will hear: Oh Sir access mod loaded. Press F1 for help. The first start can take a little longer while BepInEx sets itself up.
The installer leaves other BepInEx mods and their settings alone. If you already had a different BepInEx.cfg, it is saved as BepInEx\config\BepInEx.cfg.before-OhSirAccess.bak before the mod's own one is copied in.
To update, run Install.bat from the new version. Your Oh Sir Access settings are kept. Version 0.5.2 and newer use a new settings file name, so settings from 0.5.1 or older start from the defaults; you can delete the old settings file in BepInEx\config.

Manual install (if Install.bat does not work)
1. Find the game folder. In Steam, right click the game in your library, choose Manage, then Browse local files. It is usually
   C:\Program Files (x86)\Steam\steamapps\common\Oh...Sir! The Insult Simulator
2. Extract everything in this zip straight into that folder, so that winhttp.dll and Tolk.dll end up next to ohsir.exe and the BepInEx folder is inside the game folder. If Windows asks, say yes to merge folders and replace files. Install.bat, Uninstall.bat and OhSirAccess_Setup.ps1 are not needed in the game folder, but they do no harm there.
3. Start your screen reader, then start the game from Steam as usual.

If the game does not save your progress
Windows Controlled Folder Access (ransomware protection) can block the game from saving in your Documents folder. In Windows Security, open Virus and threat protection, Ransomware protection, Allow an app through Controlled folder access, and add ohsir.exe.

If you hear nothing
1. Press F11 a few times, waiting a moment after each press, until you hear "Speech test via ...". Each press switches to the next method: Tolk, JAWS API library, JAWS COM object, Windows voice. The one you stop on is saved.
2. If the game's menus are blank or don't respond, open the folder OhSirAccess_Tools in the game folder and run EntryPoint_Camera.bat, then start the game again. EntryPoint_MonoBehaviour.bat puts back the setting this mod comes with. Do not change the entry point to Application: that setting breaks this game's menus.
3. To report a problem, send the file BepInEx\LogOutput.log from the game folder, and also ohsir_Data\output_log.txt. If something specific doesn't work, press F12 on that screen first: that writes a detailed report into the log.

Keys in menus
Up and Down arrows: move between the items on the screen.
Tab and Shift plus Tab: also move. These always work.
Enter or Space: choose the current item.
Left and Right arrows: change a slider, or turn the wheel of gentlemen or scenes on the selection screen.
Home and End: on a slider, jump to the minimum or maximum.
Escape or Backspace: go back.
F1: help, then the list of switches and whether each is on or off.
F2: read the screen: title, information, then the buttons.
Page Down and Page Up: read the screen's text line by line, for example credits, results, story mode summaries and achievements.
F3: where am I.
F11: switch the speech method and say a test line.
F12: write a diagnostics report to the log.
F4 to F9, Shift plus F4 and Shift plus F9: on and off switches, see Switches below.
R: repeat the last thing spoken.
Each screen says its title when it opens. Settings are read as label, value and type, for example "Music, slider, 80 percent" or "Fullscreen, on, switch", and the new value is spoken when you change it.
Statistics: the game shows achievements and leaderboards in the Steam overlay, which screen readers cannot read. On the Statistics screen, press F2 or Page Down to hear your achievements instead. The leaderboard is not available.
Loading screen: the hint is read. When the "Thank you sir" button appears, press Enter to continue.

Choosing a fight
Main menu: "Insult your CPU!" is single player, "Insult a human!" is multiplayer, "Run away!" quits. The two icon buttons below are Options (settings, Twitch and credits) and Statistics.
Selection screen: Left and Right turn the wheel and read each gentleman. Enter on the gentleman opens his details and reads his weakness and biography. Then move to the select button with Down or Tab and press Enter to confirm. Do the same for the scene. Escape goes back one step.
Start of a match: the game shows two instruction pictures. Press Enter to go past each one. In the tutorial, press Enter after each message to continue.

Keys during a match
1 to 9 (top row or number pad): hear a board phrase. This also moves the game's focus to it, so Enter may pick it too.
Shift plus 1 to 9: pick that board phrase.
Q or W: hear your first or second hand phrase.
Shift plus Q or Shift plus W: pick that hand phrase.
T: drink tea, which swaps your two hand phrases for new ones, once per round.
F: finish your insult. If your sentence is not complete yet, the mod warns you first. Press F again within 3 seconds to finish anyway.
B: read the whole board.
H: read your hand.
S: read your sentence so far.
O: read your opponent's sentence so far.
P: both pride values. Pride is your health.
L: time left on the turn timer.
G: which kind of phrase fits next.
I: status: whose turn, time, tea, what fits next, pride.
N: both gentlemen's names and weaknesses.
R: repeat.
Enter or Space: go past the instruction pictures and tutorial messages.
F1: help, then the list of switches and whether each is on or off. F2: read screen. F3: where am I. F4 to F9, Shift F4 and Shift F9: switches. F11: switch speech method. F12: diagnostics. Escape: pause menu, then use the menu keys.

How phrases are described
Each phrase is read as its words, then its kind, then whether it fits right now (OK or wrong grammar).
Kinds:
noun: who or what you insult, for example your mother.
ending verb: completes a sentence, for example is a hamster.
linking verb: must be followed by a noun, for example looks like.
and: joins two phrases.
closer: a final flourish such as sir or you numpty. It ends your insult right away.
continue next round: carries your unfinished insult into the next round.
A simple good insult is: noun, then ending verb, then a closer, or noun, linking verb, noun.
If you pick a phrase marked wrong grammar, the mod asks you to press it again to confirm. A wrong pick costs pride.

Switches (on and off keys)
These keys work everywhere, in menus and during a match. Each press flips the switch, says the new state, for example "Timer warnings off", and saves it right away, so it stays that way next time. F1 reads all of them with their current state.
F4: timer warnings, saying 10 seconds and 5 seconds left on your turn. Default on. The game itself ticks at 3, 2, 1.
Shift plus F4: double timer in offline games (single player, hot-seat, tutorial). On means twice the normal time, off means the normal game timer. Default on. It never applies online, and the change starts from the next turn.
F5: read all 9 board phrases at the start of each round. Default off.
F6: read your two hand phrases at the start of each of your turns. Default off.
F7: also read the finished insult with the screen reader. Default off, because the insult is already voice acted.
F8: wrong grammar warning: when you pick a phrase that breaks grammar, warn first and require a second press. Default on.
F9: read the tutorial messages and the start-of-match picture card prompts. Default on.
Shift plus F9: when the items in a menu change, say how many there are and the first one. Default on.
F10 is not used, because Windows uses it for the menu bar.

Other settings (in the settings file)
Everything on the switch keys is also stored in the settings file, along with a few settings that have no key. You rarely need these.
How to change them:
1. Close the game. Settings are only read when the game starts, and the game saves the file when it closes.
2. In the game folder, open the folder BepInEx, then config, and open the file ohsiraccess.mod.cfg in Notepad. The file is created the first time you start the game with the mod.
3. Each setting is one line in the form Name = value, for example
   MenuNavigation = Auto
   Lines starting with # are explanations and are ignored. Change only the part after the equals sign, keep the spelling and capital letters of the values exactly as listed below, and use true or false for on and off.
4. Save the file with Control plus S, close Notepad, and start the game.
If the file gets messed up, delete it; the game creates a fresh one with the defaults on the next start.
The settings without a key:
SpeechBackend: Auto (default), Tolk, JawsDirect, JawsDLL, JawsCOM or SAPI. Auto uses JAWS directly when JAWS is running, otherwise Tolk (NVDA and others), otherwise the Windows voice. F11 in the game also changes and saves this.
MenuNavigation: Auto (default), Mod or Game. Who handles arrows and Enter in menus. Auto lets the game do it when its own keyboard navigation works, otherwise the mod does. Mod makes the mod always do it. Game makes the game always do it, Tab still works. Try Mod if the arrow keys behave oddly in a menu.
ForceGameKeyboardNavigation: true (default) or false. Switches on the game's own arrow key navigation if it is off.
OfflineTimeMultiplier: any number from 1 to 10, default 2. Shift plus F4 switches between 2 and 1; edit the file for other values, for example 3 for triple time. 1 is the normal timer. Never applied online.
AutoDiagnostics: true or false, default false. Writes a list of the screen's items and extra activity notes to the log on every new screen.
LogSpeech: true or false, default false. Writes everything spoken to the log.
Both of these are only for problem reports and make the log bigger. For a normal problem report you do not need them: just press F12 on the screen where something goes wrong, then send the log. F12 writes what is on the screen; it does not record what you type. Turn them back to false afterwards.
The switch settings in the file are SpeakTimerWarnings (F4), AutoReadBoardOnNewRound (F5), AutoReadHandOnTurn (F6), SpeakFinalInsultText (F7), ConfirmWrongGrammarPicks (F8), SpeakTutorialMessages (F9) and AnnounceScreenChanges (Shift F9), each true or false.

Uninstalling
Easy way: close the game, then run Uninstall.bat from the extracted zip folder. It finds the game the same way as the installer and removes only the files this mod added, including its settings file. If no other BepInEx mods are installed, it asks whether to remove the BepInEx loader too: type y for yes or n for no, then press Enter. If other BepInEx mods are found, the loader is kept for them.
Manual way: delete winhttp.dll from the game folder. The game then runs exactly as before, without the mod.
To remove everything by hand, also delete from the game folder: the BepInEx folder, the OhSirAccess_Tools folder, doorstop_config.ini, .doorstop_version, changelog.txt, Tolk.dll, nvdaControllerClient32.dll, SAAPI32.dll, dolapi32.dll and this file. If you use other BepInEx mods, keep winhttp.dll, doorstop_config.ini, .doorstop_version and the BepInEx folder, and delete only BepInEx\plugins\OhSirAccess and BepInEx\config\ohsiraccess.mod.cfg.
Steam's "Verify integrity of game files" does not remove these files, but it never needs to: the game files themselves are not changed.

Credits and licenses
Oh Sir Access is a fan-made accessibility mod. Oh...Sir! The Insult Simulator is by Vile Monarch; this mod is not affiliated with them.
This package includes:
- BepInEx 5.4.23.2, MIT license.
- Unity Doorstop 4.3.0 (winhttp.dll), GNU LGPL 2.1.
- HarmonyX, MonoMod and Mono.Cecil (in BepInEx\core), MIT license.
- Tolk by Davy Kager, GNU LGPL version 3 (which builds on the GNU GPL version 3, also included).
- NVDA Controller Client (nvdaControllerClient32.dll) by NV Access, GNU LGPL 2.1.
- SAAPI32.dll (System Access) and dolapi32.dll (Dolphin), screen reader client libraries distributed with Tolk.
The license texts are in the folder BepInEx\plugins\OhSirAccess\licenses. The LGPL libraries are used unmodified as separate DLL files; you can replace them with your own builds.

License
Oh Sir Access itself is released under the MIT License (see LICENSE.txt). Bundled third-party components keep their own licenses, listed above.

Changes
0.5.4: on and off switches on F4 to F9, Shift plus F4 and Shift plus F9, saved right away. F1 now also lists the switches with their current state. The Settings section explains how to change the other settings in the settings file. Activity logging (menu presses, screen changes, tutorial steps) now only happens when AutoDiagnostics is on.
```
