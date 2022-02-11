![BepInEx logo](https://avatars2.githubusercontent.com/u/39589027?s=256)

# BepInExPack for Valheim

This is [BepInEx 5.4.19](https://github.com/BepInEx/BepInEx) pack for Valheim.

BepInEx is a general purpose framework for Unity modding.
BepInEx includes tools and libraries to

* load custom code (hereafter *plugins*) into the game on launch;
* patch in-game methods, classes and even entire assemblies without touching original game files;
* configure plugins and log game to desired outputs like console or file;
* manage plugin dependencies.

BepInEx is currently [one of the most popular modding tools for Unity on GitHub](https://github.com/topics/modding?o=desc&s=stars).

## This pack's contents

This pack is preconfigured and usable for Valheim modding.  
In particular, the changes from base BepInEx releases are:

* Added preconfigured `BepInEx.cfg` with console enabled.
* Added unstripped Unity + Mono BCL DLLs for current versions of the game. See [this issue comment for more info](https://github.com/NeighTools/UnityDoorstop/issues/10#issuecomment-776921796).
* Updated Doorstop configuration and BepInEx to allow to load unstripped DLLs without having to overwrite game DLLs.
* Added scripts necessary to run both game and dedicated server on Linux machines

## Installation (game, automated)

This is the recommended way to install BepInEx on the game.

1. Download and install [Thunderstore Mod Manager](https://www.overwolf.com/app/Thunderstore-Thunderstore_Mod_Manager) or [r2modman](https://valheim.thunderstore.io/package/ebkr/r2modman/)
2. Click **Install with Mod Manager** button on top of the page
3. Run the game via the mod manager

## Installation (server, automated)

There are some managed dedicated server that support simple and automatic BepInEx installation.  
Here is a list of known ones (list updated as more is known).  
*Note: Some of the links may be affiliate links*

[![ValheimServerHosting](https://i.imgur.com/w21YSPf.jpg)](https://valheimserverhosting.com/?via=bepinex)

[![XGamingServer](https://i.imgur.com/sRUEoy0.png)](https://link.xgamingserver.com/BepInEx)


## Installation (manual)

If you are installing this manually, do the following

1. Extract the archive into a folder. **Do not extract into the game folder.**
2. Move the contents of `BepInExPack_Valheim` folder into `<Steam Location>\steamapps\common\Valheim`.
3. Check that you have installed it correctly. 
    If done correctly, your folder will look as follows

    ![BepInEx, winhttp.dll, doorstop_config.ini and unstripped_corlib in Valheim folder.](https://i.imgur.com/CPG0PXA.png)
4. Follow either Windows or Linux game running instructions below:

### Configuration (Windows)

No need to configure. Simply run the game. If everything is correct, you will see a console pop up.

### Configuration (Linux, game)

1. Make `start_game_bepinex.sh` executable with `chmod u+x start_game_bepinex.sh`.
2. In Steam, go to game's properties and set game's launch arguments to
    
	```
	./start_game_bepinex.sh %command%
	```
	
	Note to advanced users: You can change `./start_game_bepinex.sh` to full path to the script. This way you can install this pack entirely outside of game folder.
3. Run the game via Steam.

At this moment you will not see any clear indication if BepInEx works.
It is suggested to test by installing a simple plugin such as [MessageCenter from BepInEx.Utility](https://github.com/BepInEx/BepInEx.Utility).

### Configuration (Linux, server)

This guide assumes you have enough knowledge working with Linux.  
If not, it is suggested you use [ValheimPlus](https://github.com/valheimPlus/ValheimPlus) instead and server hosts that support it out of the box.

1. Make `start_server_bepinex.sh` executable with `chmod u+x start_server_bepinex.sh`.
2. Edit `start_server_bepinex.sh` to change the launch parameter like you would with Valheim's own launch script.
3. Run `start_server_bepinex.sh` to start the server.

If done correctly, you will see BepInEx bootstrap messages in the terminal.


## Checking BepInEx version and load status

If BepInEx was loaded successfully into the game, you should see BepInEx version info in top left corner of the main menu:

![BepInEx version in top-left corner of main menu](https://i.imgur.com/Yha5IkQ.png)

## Useful links

* [BepInEx: writing basic plugin walkthrough](https://docs.bepinex.dev/articles/dev_guide/plugin_tutorial/index.html)
* [BepInEx: useful plugins for modding](https://docs.bepinex.dev/articles/dev_guide/dev_tools.html)
* [BepInEx: patching game methods at runtime](https://docs.bepinex.dev/articles/dev_guide/runtime_patching.html)

## Issues, questions, etc.

At this moment, you can use the following channels to ask for help

* [Valheim Modding Discord](https://discord.gg/RBq2mzeu4z)
* [BepInEx Discord](https://discord.gg/MpFEDAg) -- **Only technical support for THIS PACKAGE. No support for plugins.**

## Changelog

#### 5.4.1900
* Updated to BepInEx 5.4.19 ([changelog](https://github.com/BepInEx/BepInEx/releases/tag/v5.4.19))

#### 5.4.1700
* Updated to BepInEx 5.4.17 ([changelog](https://github.com/BepInEx/BepInEx/releases/tag/v5.4.17))

#### 5.4.1601
* Updated unstripped DLLs for Unity 2019.4.31

#### 5.4.1600
* Updated to BepInEx 5.4.16 ([changelog](https://github.com/BepInEx/BepInEx/releases/tag/v5.4.16))

#### 5.4.1502
* Adjusted `start_game_bepinex.sh` to handle cmdline args better

#### 5.4.1501
* Updated Valheim.DisplayBepInExInfo to 2.0.0([changelog](https://github.com/Valheim-Modding/Valheim.DisplayBepInExInfo/releases/tag/v2.0.0))

#### 5.4.1500
* Updated to BepInEx 5.4.15 ([changelog](https://github.com/BepInEx/BepInEx/releases/tag/v5.4.15))

#### 5.4.1400

* Updated to BepInEx 5.4.14 ([changelog](https://github.com/BepInEx/BepInEx/releases/tag/v5.4.14))
* Updated *nix start script for games to account for new Steam game bootstrapper

#### 5.4.1100

* Updated to BepInEx 5.4.11 ([changelog](https://github.com/BepInEx/BepInEx/releases/tag/v5.4.11))

#### 5.4.1001

* Updated unstripped DLLs for Unity 2019.4.24

#### 5.4.1000

* Updated to BepInEx 5.4.10 ([changelog](https://github.com/BepInEx/BepInEx/releases/tag/v5.4.10))
* Updated Valheim.DisplayBepInExInfo to 1.1.0 ([changelog](https://github.com/Valheim-Modding/Valheim.DisplayBepInExInfo/releases/tag/v1.1.0))

#### 5.4.901

* Updated README with some dedicated servers that support BepInEx by default

#### 5.4.900

* Updated to BepInEx 5.4.9 ([changelog](https://github.com/BepInEx/BepInEx/releases/tag/v5.4.9))
* Updated Valheim.DisplayBepInExInfo to 1.0.1 ([changelog](https://github.com/Valheim-Modding/Valheim.DisplayBepInExInfo/releases))
* Set `PreventClose` to `true` by default. This prevents console from being closed (and thus unsaved game being closed by accident)

#### 5.4.800

* Updated to BepInEx 5.4.8
* Added [Valheim.DisplayBepInExInfo](https://github.com/Valheim-Modding/Valheim.DisplayBepInExInfo) plugin

#### 5.4.701

* Updated screenshot of example installation

#### 5.4.700

* Updated to BepInEx 5.4.7

#### 5.4.603

* Updated BepInEx 5.4.6 to a newer build
* Added `--enable-console true|false` command-line option to enable or disable BepInEx console
* Added `--doorstop-dll-search-override` command-line option to behave the same way as config's `dllSearchPathOverride` option

#### 5.4.602

* Updated BepInEx 5.4.6 to a newer build
* Update config to write Unity logs to LogOutput.log by default
* Added preconfigured scripts and files to run the game under Linux

#### 5.4.601

* Updated unstripped DLLs for Unity 2019.4.20

#### 5.4.600

* Adjusted README
* Adjusted versioning to account for inter-version changes

#### 5.4.6

* Initial release with BepInEx 5.4.6