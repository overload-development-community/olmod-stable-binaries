olmod 0.2.2 - Overload mod
Community mods for Overload
https://github.com/arbruijn/olmod

Overload is a registered trademark of Revival Productions, LLC.  This is an
unaffiliated, unsupported tool.  Use at your own risk.

How to run
----------

- If you installed Overload using Steam or GOG Galaxy you can extract olmod
  anywhere and it will find Overload automatically.

- If you installed Overload yourself or on linux, extract olmod in the Overload main
  directory (where Overload.exe / Overload.x86_64 is also located).

- Run olmod.exe / olmod.sh (linux) instead of Overload.exe

- Use olmodserver.bat / olmodserver.sh (linux) to start a server

What does it do
---------------

- Shows a modified indicator in the main menu

- Allows access to the unfinished Monsterball multiplayer mode (with tweaks
  by terminal).
  The Monsterball multiplayer mode only works when both server and clients run olmod.

- Puts a MP player in observer mode if it uses a pilot name starting with
  OBSERVER.
  The observer mode only works when the server and the observer client run olmod.

- Reads projdata.txt / robotdata.txt with custom projectile (weapon) and
  robot settings. You can extract the stock data from the game with the
  included tool olgetdata. The txt files must be in the same directory as
  olmod.exe. You can run olgetdata on linux with: mono olgetdata.exe

- Adds frametime non-cheat code and rearview cheat code

- Allows MP with up to 16 players (server and all clients must run olmod)

- Allows MP with up to 8 teams (server and all clients must run olmod)

- Writes ServerStatLog.txt on server (by luponix)

- Fixes MP client homing behaviour (by terminal)

- Allows shoot to open doors in MP

- Allows pasting in the MP password field

- Allows joining in progress matches when enabled for the match

- Adds option to enable console with ` key

- Adds console commands: xp, reload_missions, mipmap_bias, ui_color

- Allows custom music in custom levels

- Allows spawn data for custom MP levels

- Adds Internet match option with built in olproxy

How does it work
----------------

The regular Overload.exe just runs UnityMain from UnityPlayer.dll.  The
replacement olmod.exe also runs UnityMain, but intercepts calls from Unity
to the mono C# engine to also load GameMod.dll.  The file GameMod.dll
contains a C# class that uses Harmony to modify the game scripting code in
memory.
