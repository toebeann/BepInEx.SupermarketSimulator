![BepInEx logo](assets/logo.png)

# Tobey's BepInEx Pack for Supermarket Simulator

This is a [BepInEx](https://github.com/BepInEx/BepInEx) pack for Supermarket Simulator, preconfigured and ready to use on Windows and Linux (including SteamOS), with compatibility for MelonLoader mods and plugins!

BepInEx is a general purpose framework for Unity modding. BepInEx includes tools and libraries to

-   load custom code (hereafter _plugins_) into the game on launch;
-   patch in-game methods, classes and even entire assemblies without touching original game files;
-   configure plugins and log game to desired outputs like console or file;
-   manage plugin dependencies.

BepInEx is currently [one of the most popular modding tools for Unity on GitHub](https://github.com/topics/modding?o=desc&s=stars).

## This pack's contents

This pack is preconfigured and ready to use for Supermarket Simulator modding.\
In particular, this pack comes with

-   [BepInEx.MelonLoader.Loader](https://github.com/BepInEx/BepInEx.MelonLoader.Loader), a BepInEx loader for MelonLoader mods and plugins,
-   [Tobey.PluginDoctor](https://github.com/toebeann/Tobey.PluginDoctor), a BepInEx plugin & patcher combo which diagnoses and reports advice on how to handle common problems with BepInEx 5 plugins, and
-   [Tobey.FileTree](https://github.com/toebeann/Tobey.FileTree), a configurable BepInEx plugin which logs the game's file tree to aid in troubleshooting issues.

## Compatibility with MelonLoader

This pack comes with [BepInEx.MelonLoader.Loader](https://github.com/BepInEx/BepInEx.MelonLoader.Loader), and as such should be compatible with most mods and plugins made for MelonLoader 0.5.7.

To use BepInEx plugins and patchers together with MelonLoader mods and plugins, you should [uninstall MelonLoader](https://github.com/LavaGang/MelonLoader.Installer/blob/master/README.md#how-to-un-install-melonloader) (if applicable), then install this pack following [the instructions below](#installation).

Then, simply follow [the below instructions for installing mods](#installing-mods) to have mods made for both BepInEx and MelonLoader running side-by-side!

## Installation

> [!TIP]\
> The game folder is the folder containing the game's executable (e.g. `Supermarket Simulator.exe`).\
> \
> Steam users can find the game folder by right-clicking the game in their Steam library and selecting `Manage` -> `Browse local files`.

To install manually, follow these instructions:

1. [Download Tobey's BepInEx Pack for Supermarket Simulator](https://github.com/toebeann/BepInEx.SupermarketSimulator/releases/latest/download/BepInEx.zip).
1. Extract the contents of the downloaded archive into the game folder.\
   **ℹ️** _That just means open the .zip file and drag the files and folders out into the game folder!_
1. **Linux (SteamOS etc.) only:** In your Steam library, right-click the game, select `Properties...` and set the launch arguments to:
    ```
    WINEDLLOVERRIDES="winhttp=n,b" %command%
    ```
1. Run the game as normal (e.g. launch it from Steam).\
   You can check the file `LogOutput.log` in the `BepInEx` folder. If it exists, that means BepInEx has loaded and is doing its thing.

> [!IMPORTANT]\
> **With just this pack installed, you will not see any changes in-game!**\
> Check the `LogOutput.log` file in the `BepInEx` folder to determine whether BepInEx has loaded.

## Installing mods

> [!NOTE]\
> The paths in this section are relative to the game folder, i.e. `BepInEx/plugins` = `[game folder]/BepInEx/plugins`, where `[game folder]` is the path to the folder containing the game's executable (e.g. `Supermarket Simulator.exe`).\
> \
> Steam users can find the game folder by right-clicking the game in their Steam library and selecting `Manage` -> `Browse local files`.

> [!TIP]\
> "Extract the .zip" simply means take the contents of the .zip file and put them in the specified location.\
> \
> For example, if you are told to "extract the .zip" or "extract the contents of the archive" into `BepInEx/plugins`, then you can simply open the .zip archive by double-clicking on it, then just select everything inside and drag the contents into your `BepInEx/plugins` folder. Easy!

**It is _strongly_ recommended to read and follow the instructions provided in the description of each mod you download.**

However, sometimes mod authors don't give good (or any) instructions, or you just can't be bothered to read them (we've all been there). For those occasions, here's a simple reference:

### Mod installation by type

| Mod type           | Where to extract the .zip |
| ------------------ | ------------------------- |
| BepInEx plugin     | `BepInEx/plugins`         |
| BepInEx patcher    | `BepInEx/patchers`        |
| MelonLoader mod    | `MLLoader/Mods`           |
| MelonLoader plugin | `MLLoader/Plugins`        |

### Mod installation by .zip structure

| Folder located in root of .zip | Where to extract the .zip                     |
| ------------------------------ | ----------------------------------------- |
| `BepInEx`                      | Directly in the game folder               |
| `MLLoader`                     | Directly in the game folder               |
| `plugins`                      | Try `BepInEx` first, otherwise `MLLoader` |
| `patchers`                     | `BepInEx`                                 |
| `Mods`                         | `MLLoader`                                |
| `Plugins`                      | Try `MLLoader` first, otherwise `BepInEx` |

### Mod installation by requirements

> [!TIP]\
> On Nexus mod pages, you can usually see a mod's requirements by expanding the `Requirements` near the top of the description tab. Otherwise, read the mod's description.

| Listed in requirements                 | Mentioned somewhere on the page | Where to extract the .zip                                                                                                                                          |
| -------------------------------------- | ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BepInEx (especially this BepInEx pack) | MelonLoader                     | Probably `MLLoader/Mods`, maybe `MLLoader/Plugins`. Use common sense and refer to [the .zip structure](#mod-installation-by-zip-structure) as needed.   |
| BepInEx / this BepInEx pack            |                                 | Probably `BepInEx/plugins`, maybe `BepInEx/patchers`. Use common sense and refer to [the .zip structure](#mod-installation-by-zip-structure) as needed. |
|                                        | BepInEx                         | Probably `BepInEx/plugins`, maybe `BepInEx/patchers`. Use common sense and refer to [the .zip structure](#mod-installation-by-zip-structure) as needed. |
| MelonLoader                            |                                 | Probably `MLLoader/Mods`, maybe `MLLoader/Plugins`. Use common sense and refer to [the .zip structure](#mod-installation-by-zip-structure) as needed.   |
|                                        | MelonLoader                     | Probably `MLLoader/Mods`, maybe `MLLoader/Plugins`. Use common sense and refer to [the .zip structure](#mod-installation-by-zip-structure) as needed.   |

### I still can't figure it out!

First, double check and follow the instructions on the mod page. If you still can't figure it out or there aren't any instructions on the mod page, you'll have to get in touch with the author of the mod somehow. Your best bet is usually going to be the Nexus Mods posts tab of that mod. Make sure to check that the question hasn't already been asked and answered.

## Useful links for mod authors

-   [BepInEx: writing basic plugin walkthrough](https://docs.bepinex.dev/articles/dev_guide/plugin_tutorial/)
-   [BepInEx: useful plugins for modding](https://docs.bepinex.dev/articles/dev_guide/dev_tools.html)
-   [BepInEx: patching game methods at runtime](https://docs.bepinex.dev/articles/dev_guide/runtime_patching.html)

## Issues, questions, etc.

First, please make sure to check that the answer you're looking for isn't already somewhere on this page. Use Ctrl+F to search for keywords.

Second, check [the FAQ](https://github.com/toebeann/BepInEx.SupermarketSimulator/wiki/FAQ) to see if there is an answer there.

If not, at this moment, you can use the following channels to ask for help:

-   [Nexus Mods posts tab](https://www.nexusmods.com/supermarketsimulator/mods/9/?tab=posts)
-   [GitHub issues](https://github.com/toebeann/BepInEx.SupermarketSimulator/issues)
-   [BepInEx Discord](https://discord.gg/MpFEDAg) -- **Intended for developers, only technical support for BepInEx itself will be provided. No support for mods.**

## Licensing

This GitHub repository contains no code or binaries from external sources, only code used to automatically put together a preconfigured .zip of the BepInEx pack.

However, the .zip create by this repository's code contains binaries from the following projects, redistributed without modification and in accordance with their licenses:

| Project                                                                             | License(s)                                                                                                                                                                                                                                                               |
| ----------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [BepInEx](https://github.com/BepInEx/BepInEx)                                       | [LGPL-2.1](https://github.com/BepInEx/BepInEx/blob/master/LICENSE)                                                                                                                                                                                                       |
| [BepInEx.MelonLoader.Loader](https://github.com/BepInEx/BepInEx.MelonLoader.Loader) | [AGPL-3.0](https://github.com/BepInEx/BepInEx.MelonLoader.Loader/blob/master/LICENSE) and [Apache-2.0](https://github.com/BepInEx/BepInEx.MelonLoader.Loader/blob/master/LICENSE_MelonLoader.md) (for its use of [MelonLoader](https://github.com/LavaGang/MelonLoader)) |
| [Tobey.PluginDoctor](https://github.com/toebeann/Tobey.PluginDoctor)                | [LGPL-3.0](https://github.com/toebeann/Tobey.PluginDoctor/blob/main/LICENSE)                                                                                                                                                                                             |
| [Tobey.FileTree](https://github.com/toebeann/Tobey.FileTree)                        | [LGPL-3.0](https://github.com/toebeann/Tobey.FileTree/blob/main/LICENSE)                                                                                                                                                                                                 |

The code in this repository is licensed under the [LGPL-3.0 license](https://github.com/toebeann/BepInEx.SupermarketSimulator/blob/main/LICENSE).
