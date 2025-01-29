# Crossfire RPG DockWindow Client (DockClient)

> Please note that this software is NOT SUPPORTED by the official Crossfire project or Crossfire developers.
>
> Support requests, bug reports, general questions and comments should be
directed to **@RetroCloak** on the Crossfire Discord / IRC or on the project
issue tracker.

This is yet another game client for **Crossfire: The Multiplayer Adventure Game**

**Officially Supported** clients can be found at:
- http://crossfire.real-time.com/clients/index.html

More information about Crossfire:
- http://crossfire.real-time.com
- https://sourceforge.net/projects/crossfire/

How to Play Crossfire:
- http://crossfire.real-time.com/guides/
- http://crossfire.real-time.com/guides/handbook/index.html


## Brief History of the Crossfire RPG DockWindow Client
I first found Crossfire around 2009, and played for quite some time on a private server. In 2021, I came back to play again after a number of years of not playing, and found the game and interface wasn't super friendly to new players. All in all, I found the interface and control schemes pretty confusing with the mix of a GUI and text commands.

I remembered I wanted to write my own client back in 2009 just to see if I could, and lately I felt that I needed a new project project, so I figured I'd try to come up with something that might be a little easier to use for new or beginner players.


## Client Features

### More accessible for new and returning players
- Adheres more to Windows UI standards compared to other clients
- Consistent UX throughout the application
- Mouse friendly interface, with right click context menus for actions and command help, and drag/drop functionality
- Each dockable panel has a toolbar and context menu with related options and actions (Also accessible via right click on the title or via down arrow in toolbar)

### Utilizes a Dockable Window System
- Panels are movable, dockable, floatable, and rearrangeable on the fly
- Support for multiple saved panel layouts (global, per character, and multiple custom layouts)
- Layouts are switchable via keybinds or when selecting a character to play

### Completely Theme-able
- Background/Foreground colours, font styles and sizes are changeable on the fly
- Themes can be imported and exported
- Each dockable panel provides additional customization, eg:
	- Inventory item colours and display can be changed based on item info
	- Message colors can be overridden based on category
	- Row heights and icon sizes can be changed in listboxes
	- List views can be sorted, grouped, and support multiple view types (details, icon, etc)

### Additional Functionality
- New DockClient only local commands:
	- Type 'localcommands' or 'localcommands help' to see the list
- Drag and Drop items between inventory, ground and container panels
- Plugin support to add additional game panels and functionality

### Other minor but useful changes
- Supports quest list and knowledge panel like the Java client
- Open containers pop up a new inventory panel to display their contents
- Map panel scales to screen and is easily zoomable, or map scale can be changed via a fixed amount
- Message panel display can be zoomed in or out
- Can hide or show any panel via keybinds
- QuickKey / Hotkey bar
- Character Notes panel
- Native windows application
	- Minimal dependencies and dlls
	- Small install size (~2mb)


## Crossfire RPG DockWindow Client Manual

### Game Panels

_Game Panels_ are the name of the panels arranged around the **map panel**, which provide information and allow interactions with the **Crossfire Server**. These can be shown, hidden, and moved around as required.

_Game Panels_ can be individually configured by the settings icon on the game panel toolbar, right-clicking the game panel title, or by the **settings menu** item under the `Options` menu.

Each _Game Panel_ also contains a common toolbar with server **commands** related to the panel, as well as **help** on the commands.


### Setting and Customizing the Theme

Set the client theme by either:
- Importing an existing theme via the `Options->Import Options->Theme` menu
- Manually customizing the theme via the `Options->Theme` menu

**NOTE:** Light/Dark mode is changed under the `Client & Game Panels->Display->Menu & Toolbar` setting, found in the `Options->Theme` menu

A theme consists of:
- Overall client toolbar and menu theme
- Game Panel fonts, background and text colours
- List item selection display
- List item secondary text display
- Panel specific theme settings
  - Text highlighting colours


### Setting and Customizing the Game Panel Layout

The client layout can be saved **to the character**, or saved as a **client default** layout. Existing layouts can be imported under the `Panel Layout->Load Existing Layout->From File...` menu, and then saved as the **Global Default Layout** or as the **Default Layout for Current Character** under `Panel Layout->Save Current Layout`.

Any client layout can be exported to a file, and importing a layout from file can be bound to a keybind or quickkey using the `loadlayoutfile` _localcommand_.

A layout consists of:
- Game Panel Positions and Visibility (Hidden, Docked, Floating)
- ListView View, Sorting, Grouping, and Column Widths
- Toolbar Dock Positions and Visibility (Hidden, Image, Text, Both)
- Panel specific layout settings
  - Inventory Panel filters and sorting
  - Character Panel subpanel sizes and visibility


### Setting and Customizing the Quick Keys

The **Quick Key Bar** can be set up for a _character_ by:
- Dragging a _Skill_ from the _Skill Panel_ to a _Quick Key_ and selecting **Use** or **Ready**
- Dragging a _Spell_ from the _Spell Book Panel_ to a _Quick Key_ and selecting **Cast** or **Invoke**
- Dragging a _Item_ from the _Inventory Panel_ to a _Quick Key_ and selecting **Toggle**, **Apply**, **Unapply** or **Open**
- Dragging a _Command_ from the _Command Panel_ to a _Quick Key_
- Dragging an _Equipment Set_ from the _Equipped Item_ header of the _Character Panel_ to a _Quick Key_ and selecting **Toggle**, **Apply** or **Unapply**
- Dragging an _Pickup Mask_ from the _Auto Pickup Panel_ to a _Quick Key_
- Dragging an _Inhibit Pickup Toggle_ from the _Auto Pickup Panel_ to a _Quick Key_
- Right-clicking a _Quick Key_ and selecting **Edit Quick Key** and manually filling in the _Command_

Once a _Quick Key_ is set up, the _Quick Key Command_ can be triggered by:
- the default keybinds of `F1`-`F12`
- a left mouse click on the _Quick Key_

Additional _Quick Keys_ are available in the _Hotkey Bar Panel_ and are triggered with the default keybinds of `Shift-F1`-`Shift-F12`.

Multiple commands can be bound to a single _Quick Key_ by using `;` to delimit multiple commands. Pressing the `...` button when editing the _Command_ setting for a _Quick Key_ allows each command to be entered on its own line.

**NOTES:**
- Quick Keys are saved **to the character**.
- The image displayed along with the _Quick Key_ may change due to a server upgrade, and can be changed / disabled by modifying the _Face_ setting
- _Quick Key_ commands are sent to the server via a keybind running a **localcommand**



### Advanced Client Options & Tweaks

- **Apply Items In Open Container** allows the **apply** command to be disabled when there is an **open container** stopping the accidental apply of items
- **Auto-Commands** allow commands to be run when **choosing a player** or entering a **new map**.



## Client Installation Information

### Settings Location
Client settings are stored by default in the `%APPDATA%\Crossfire DockWindow Client` directory, which can be changed via the `-d` command line parameter if required.


### Portable Mode
Instead of using the _Crossfire DockWindow Client installer_ to install the client and plugins, the Crossfire DockWindow Client can be started in a portable mode via the `-p` command line parameter, or by running the `portable.bat` batch file. Running in portable mode will create and save any client settings to a `Data` sub-directory where the `CrossfireRPG.DockClient.exe` file exists.

Note that the portable directory does not include any plugins by default. Plugins can be installed to a portable installation as documented below, and will need to be upgraded (or removed) with each new client version.


### Plugin Installation
Supported plugins can be installed/upgraded using the _Crossfire DockWindow Client installer_. If plugins need to be installed manually, a plugin can be installed by copying all the files inside a plugin location to the Crossfire DockClient `Plugins` directory. This directory may need to be created

Manual installation steps:
1. Create a sub-directory named `Plugins` where the `CrossfireRPG.DockClient.exe` file exists
2. Copy dlls and datafiles from inside the plugin location (eg. `Plugins\PluginName`) and place them in the `Plugins` sub-directory

**NOTE:** Some plugins may be experimental, and require that experimental game panels are enabled in the client settings.


### Command Line Options
```
CrossfireRPG.DockClient.exe [-h] | [-p] | [-d <DataFolder>]

  -h                        Shows help
  -p                        Portable Mode (saves settings to <PortableDir>\Data)
  -d <DataFolder>           Saves settings to a custom data directory
```
