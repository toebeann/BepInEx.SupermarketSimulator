![BepInEx logo](assets/logo.png)

# Tobey's BepInEx x MelonLoader Pack for Supermarket Simulator

This is a [BepInEx](https://github.com/BepInEx/BepInEx) pack for Supermarket Simulator, preconfigured and ready to use on Windows, macOS and Linux (including Steam Deck handhelds), with compatibility for MelonLoader mods and plugins!

BepInEx is a general purpose framework for Unity modding. BepInEx includes tools and libraries to

-   load custom code (hereafter _plugins_) into the game on launch;
-   patch in-game methods, classes and even entire assemblies without touching original game files;
-   configure plugins and log game to desired outputs like console or file;
-   manage plugin dependencies.

BepInEx is currently [one of the most popular modding tools for Unity on GitHub](https://github.com/topics/modding?o=desc&s=stars).

## This pack's contents

This pack is preconfigured and ready to use for Supermarket Simulator modding.\
In particular, this pack comes with

-   [BepInEx.MelonLoader.Loader](https://github.com/BepInEx/BepInEx.MelonLoader.Loader), a configurable BepInEx loader for MelonLoader mods and plugins,
-   [Tobey's BepInEx MelonLoader Wizard](https://github.com/toebeann/Tobey.BepInExMelonLoaderWizard), a utility focusing on helping users easily migrate from vanilla MelonLoader,
-   [Tobey's File Tree Logger for BepInEx](https://github.com/toebeann/Tobey.FileTree), a configurable BepInEx plugin which logs the game's file tree to aid in troubleshooting issues,
-   [Tobey's Timestamp Logger for BepInEx](https://github.com/toebeann/Tobey.BepInEx.Timestamp), a configurable BepInEx patcher which logs the current timestamp, and
-   [Tobey's Game Info Fix for BepInEx.MelonLoader.Loader](https://github.com/toebeann/Tobey.MLLoader.GameInfo), a simple patch to ensure the game info logs of BepInEx.MelonLoader.Loader are correct.

## Compatibility with MelonLoader

This pack comes with [BepInEx.MelonLoader.Loader](https://github.com/BepInEx/BepInEx.MelonLoader.Loader), enabling you to use mods made for both BepInEx and MelonLoader at the same time!

With this pack installed, mods for MelonLoader need to be installed into the `MLLoader` subfolders to work. See the [Installing mods](#installing-mods) section below for details.

When you run the game with this pack installed, [Tobey's BepInEx MelonLoader Wizard](https://github.com/toebeann/Tobey.BepInExMelonLoaderWizard) will handle migrating any MelonLoader mods you already have installed to the `MLLoader` folder for you, and clean up any MelonLoader files and folders that you won't be needing anymore!

## Installation

> [!TIP]
>
> **Make sure to check out the [Installing mods](#installing-mods) section below once you have finished installing this pack!**

### Quick start

### Windows

Extract the archive into the game folder replacing any files if prompted, run the game once to generate all needed files and folders, if any prompts about MelonLoader appear just click Yes, then quit the game at the main menu and you're good to go.

If something doesn't go according to plan or you need further guidance, please refer to the [full instructions](#full-instructions-for-windows-linux-and-steam-deck-handhelds) below. Don't worry, it looks harder than it is. **Please don't skimread!**

### Linux and Steam Deck handhelds

Same as for Windows but follow step 4 from the [full instructions](#full-instructions-for-windows-linux-and-steam-deck-handhelds) below first.

For Steam Deck handhelds, switch to Desktop mode to follow the instructions. Once you've got it all working, you'll be able to play with mods in either Desktop or Gaming mode as preferred.

### macOS

[Just use gib](https://github.com/toebeann/gib). Seriously, it's way easier than manual installation on macOS.

1. [Download Tobey's BepInEx x MelonLoader Pack for Supermarket Simulator](https://github.com/toebeann/BepInEx.SupermarketSimulator/releases/latest/download/Tobey.s.BepInEx.x.MelonLoader.Pack.for.Supermarket.Simulator.zip). Make sure to unzip it in your Downloads folder if your browser doesn't do this automatically.
2. Open Terminal with Launchpad or Spotlight (press `⌘ Space`, type `terminal`, press `Enter`).
3. Copy the command from the [gib README](https://github.com/toebeann/gib#readme) and paste it into the Terminal with `⌘ V`, and press `Enter` to run it.

If you get stuck, refer to the [gib README](https://github.com/toebeann/gib#readme) for help.

If you're a glutton for punishment and would rather install it manually, follow [the idiot's guide to macOS installation](https://github.com/toebeann/BepInEx.SupermarketSimulator/wiki/Idiot's-guide-to-macOS-installation).

### Full instructions for Windows, Linux and Steam Deck handhelds

> [!WARNING]
>
> These are instructions are **not** for macOS! Please refer to the [macOS](#macos) section above for instructions on installing this pack on macOS!

> [!TIP]
>
> **The game folder is the folder containing the game's executable (e.g. `Supermarket Simulator.exe`).**
>
> Steam users can find the game folder by right-clicking the game in their Steam library and selecting `Manage` > `Browse local files`.

1. [Download Tobey's BepInEx x MelonLoader Pack for Supermarket Simulator](https://github.com/toebeann/BepInEx.SupermarketSimulator/releases/latest/download/Tobey.s.BepInEx.x.MelonLoader.Pack.for.Supermarket.Simulator.zip).
2. Make sure the game is not running.
3. Extract the contents of the downloaded archive into the game folder. Replace any files if prompted.\

    **ℹ️** _That just means open the .zip file and drag the files and folders out into the game folder!_

    If done correctly, inside your `steamapps` > `common` > `Supermarket Simulator` folder it should look something like this (the entries in bold being from the pack):

    **⚠️ _This list is used as a reference and is non-exhaustive, there will be other stuff, please don't delete anything!_**

    - **`BepInEx`**
    - **`MLLoader`**
    - **`Plugins`**
    - `Supermarket Simulator_Data`
    - **`doorstop_config.ini`**
    - `Supermarket Simulator.exe`
    - **`version.dll`**
    - **`winhttp.dll`**

    **⚠️ _If you are missing any of these files or folders, you are probably installing to the wrong place, and this pack will not work._**

4. **Skip this step if you play on Windows!**

    Linux and Steam Deck handheld users: go to your Steam library, right-click the game, select `Properties...` and set the launch options:

    ```
    WINEDLLOVERRIDES="winhttp=n,b" %command%
    ```

    **⚠️ _Do not set the launch options if you play the game on Windows!_**

    **ℹ️** _If preferred, Linux users can instead set the Wine configuration (`winecfg`) for the game to add `winhttp` as a DLL override via the `Libraries` tab. Remove the launch options if applicable. [Full instructions here](https://docs.bepinex.dev/articles/advanced/proton_wine.html)._

5. Run the game from Steam as normal.

    If you previously had MelonLoader installed, you may be prompted to migrate your mods and clean up redundant files from MelonLoader. It is recommended to click `Yes` to each of these prompts unless you know what you're doing. This will allow any MelonLoader mods you previously installed to continue to work with this pack.

6. Exit the game at the main menu.

    Assuming you have followed these instructions correctly, inside the `Supermarket Simulator` > `BepInEx` folder there will now be a file `LogOutput.log` (or simply `LogOutput` - it's the same thing). This is your log file, and it will be regenerated every time the game runs with technical and diagnostic information about your installed mods, and any errors that might happen while playing. It's very useful for troubleshooting, and it is recommended to share it whenever asking for help with your mods. It is equivalent to the MelonLoader or BepInEx console window you might be familiar with, containing all of the same information.

    If this file is missing, it usually means that you have not installed the pack correctly and you should probably try again from scratch. Make sure to pay careful attention to the instructions and don't skimread any of the steps.

    Otherwise, you can now install mods according to the [Installing mods](#installing-mods) section below.

> [!IMPORTANT]
>
> **With just this pack installed, you will not see any changes in-game!**
>
> Check the file `Supermarket Simulator` > `BepInEx` > `LogOutput.log` to determine whether BepInEx has loaded.

## Installing mods

> [!IMPORTANT]
>
> **Always make sure the game is not running when installing, removing, or otherwise changing mod files!**

> [!TIP]
>
> **Some mods might tell you to install MelonLoader - you can and should ignore that instruction!**
>
> This pack includes a special version of MelonLoader that is compatible with BepInEx. If you install any other copy of MelonLoader, BepInEx will stop working. [Tobey's BepInEx MelonLoader Wizard](https://github.com/toebeann/Tobey.BepInExMelonLoaderWizard) is included in this pack and will attempt to fix this issue for you, and you may be prompted to migrate from MelonLoader in which case, you should click `Yes` to each prompt unless you know what you're doing. In some cases however, you might need to reinstall this pack to fix the issue.

> [!TIP]
>
> **"Extract the .zip" simply means take the contents of the .zip file and put them in the specified location.**
>
> For example, if you are told to "extract the .zip" or "extract the contents of the archive" into `BepInEx` > `plugins`, then you can simply open the .zip archive by double-clicking on it, then just select everything inside and drag the contents into your `Supermarket Simulator` > `BepInEx` > `plugins` folder. Easy!

**It is _strongly_ recommended to read and follow the instructions provided in the description of each mod you download.**

However, sometimes mod authors don't give good (or any) instructions, or you just can't be bothered to read them (we've all been there). For those occasions, here's a simple reference:

### Mod installation by type

| Mod type           | Where to extract the .zip |
| ------------------ | ------------------------- |
| BepInEx plugin     | `BepInEx` > `plugins`     |
| BepInEx patcher    | `BepInEx` > `patchers`    |
| MelonLoader mod    | `MLLoader` > `Mods`       |
| MelonLoader plugin | `MLLoader` > `Plugins`    |

### Mod installation by .zip structure

| Folder located in root of .zip | Where to extract the .zip                 |
| ------------------------------ | ----------------------------------------- |
| `BepInEx`                      | Directly in the game folder               |
| `MLLoader`                     | Directly in the game folder               |
| `plugins`                      | Try `BepInEx` first, otherwise `MLLoader` |
| `patchers`                     | `BepInEx`                                 |
| `Mods`                         | `MLLoader`                                |
| `Plugins`                      | Try `MLLoader` first, otherwise `BepInEx` |

### Mod installation by requirements

> [!TIP]
>
> **On Nexus mod pages, you can usually see a mod's requirements by expanding the `Requirements` near the top of the description tab. Otherwise, read the mod's description.**

| Listed in requirements                 | Mentioned somewhere on the page | Where to extract the .zip                                                                                                                                       |
| -------------------------------------- | ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BepInEx (especially this BepInEx pack) | MelonLoader                     | Probably `MLLoader` > `Mods`, maybe `MLLoader` > `Plugins`. Use common sense and refer to [the .zip structure](#mod-installation-by-zip-structure) as needed.   |
| BepInEx / this BepInEx pack            |                                 | Probably `BepInEx` > `plugins`, maybe `BepInEx` > `patchers`. Use common sense and refer to [the .zip structure](#mod-installation-by-zip-structure) as needed. |
|                                        | BepInEx                         | Probably `BepInEx` > `plugins`, maybe `BepInEx` > `patchers`. Use common sense and refer to [the .zip structure](#mod-installation-by-zip-structure) as needed. |
| MelonLoader                            |                                 | Probably `MLLoader` > `Mods`, maybe `MLLoader` > `Plugins`. Use common sense and refer to [the .zip structure](#mod-installation-by-zip-structure) as needed.   |
|                                        | MelonLoader                     | Probably `MLLoader` > `Mods`, maybe `MLLoader` > `Plugins`. Use common sense and refer to [the .zip structure](#mod-installation-by-zip-structure) as needed.   |

### I still can't figure it out!

First, double check and follow the instructions on the mod page. If you still can't figure it out or there aren't any instructions on the mod page, you'll have to get in touch with the author of the mod somehow. Your best bet is usually going to be the Nexus Mods posts tab of that mod. Make sure to check that the question hasn't already been asked and answered.

## Useful links for mod authors

-   [Doorstop: debugging Unity Mono games](https://github.com/NeighTools/UnityDoorstop#debugging-in-unitymono)
-   [BepInEx: writing basic plugin walkthrough](https://docs.bepinex.dev/articles/dev_guide/plugin_tutorial/)
-   [BepInEx: useful plugins for modding](https://docs.bepinex.dev/articles/dev_guide/dev_tools.html)
-   [BepInEx: patching game methods at runtime](https://docs.bepinex.dev/articles/dev_guide/runtime_patching.html)
-   [Modded Supermarket Simulator Discord](https://discord.gg/hjGpjB3GXA)

## Issues, questions, etc.

First, please make sure to check that the answer you're looking for isn't already somewhere on this page. Use Ctrl+F to search for keywords.

Second, check [the FAQ](https://github.com/toebeann/BepInEx.SupermarketSimulator/wiki/FAQ) to see if there is an answer there.

If not, you can use the following channels to ask for help:

-   [Modded Supermarket Simulator Discord](https://discord.gg/hjGpjB3GXA)
-   [Nexus Mods posts tab](https://www.nexusmods.com/supermarketsimulator/mods/9/?tab=posts)
-   [GitHub issues](https://github.com/toebeann/BepInEx.SupermarketSimulator/issues)
-   [BepInEx Discord](https://discord.gg/MpFEDAg) -- **Intended for developers, only technical support for BepInEx itself will be provided. No support for mods.**

## Licensing

This GitHub repository contains no code or binaries from external sources, only code used to automatically put together a preconfigured .zip of the BepInEx pack.

However, the .zip created by this repository's code contains binaries from the following projects, redistributed without modification and in accordance with their licenses:

| Project                                                                                      | License(s)                                                                                                                                                                                                                                                               |
| -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [BepInEx](https://github.com/BepInEx/BepInEx)                                                | [LGPL-2.1](https://github.com/BepInEx/BepInEx/blob/master/LICENSE)                                                                                                                                                                                                       |
| [BepInEx.MelonLoader.Loader](https://github.com/BepInEx/BepInEx.MelonLoader.Loader)          | [AGPL-3.0](https://github.com/BepInEx/BepInEx.MelonLoader.Loader/blob/master/LICENSE) and [Apache-2.0](https://github.com/BepInEx/BepInEx.MelonLoader.Loader/blob/master/LICENSE_MelonLoader.md) (for its use of [MelonLoader](https://github.com/LavaGang/MelonLoader)) |
| [Tobey.BepInExMelonLoaderWizard](https://github.com/toebeann/Tobey.BepInExMelonLoaderWizard) | [LGPL-3.0](https://github.com/toebeann/Tobey.BepInExMelonLoaderWizard/blob/main/LICENSE)                                                                                                                                                                                 |
| [Tobey.FileTree](https://github.com/toebeann/Tobey.FileTree)                                 | [LGPL-3.0](https://github.com/toebeann/Tobey.FileTree/blob/main/LICENSE)                                                                                                                                                                                                 |
| [Tobey.MLLoader.GameInfo](https://github.com/toebeann/Tobey.MLLoader.GameInfo)               | [LGPL-3.0](https://github.com/toebeann/Tobey.MLLoader.GameInfo/blob/main/LICENSE)                                                                                                                                                                                        |
| [Tobey.BepInEx.Timestamp](https://github.com/toebeann/Tobey.BepInEx.Timestamp)               | [LGPL-3.0](https://github.com/toebeann/Tobey.BepInEx.Timestamp/blob/main/LICENSE)                                                                                                                                                                                        |

The code in this repository is licensed under the [LGPL-3.0 license](https://github.com/toebeann/BepInEx.SupermarketSimulator/blob/main/LICENSE).
