## Crossfire DockWindow Client v0.8.8
### July 26, 2024

**Fixes:**
- `Character Panel`: Fix setting wrong item power label when level changes
- `Map Panel`: Fix issue where fog of war could not be disabled
- `Map Panel`: Fix issue where moving multi-tile images may not be fully re-drawn, resulting in random parts of the multi-tile being left on the display
- `Map Manager`: Fix issue where map cells were not always flagged as FOW cells when the viewport scrolled, resulting in multi-tile images being drawn when they don't exist
- `Map Manager`: Update logic to consistently clear OOB and FOW cells when they come back into view, to avoid multi-tile images being drawn when they don't exist

**Minor Changes:**
- `Inventory Panel`: Update tooltip for item number counter (was Take/Drop) for clarity
- `Map Panel`: Allow fog of war data to be drawn without a style
- `Skill Panel`: Add more information to skill increase/decrease messages
- `Main Window`: Add links to crossfire atlas and wiki in help menu
- `Docs`: Update changelog format as it was getting flagged as a script malware

---

## Crossfire DockWindow Client v0.8.7
### July 20, 2024

**New Features & Notable Changes:**
- `Map Panel`
  - Implement smoothing of face corners
    - Note that smoothing is still marked as experimental, as there are some performance issues with larger viewports
- `MiniMap Panel`
  - Speed up minimap render times when minimap contains a lot of map information
- `Plugins` -> `Discord`
  - Add experimental Discord Rich Presense plugin (under Options->Settings->Discord when installed)
    - Plugin Location: Plugins\Discord
    - To install a plugin, copy all the files inside a plugin location to the Crossfire DockClient Plugin directory
      - (eg: <InstallDir>\Plugins\ or <PortableDir>\Plugins\)

**Fixes:**
- `Inventory Panel`: Fix issue with drag and drop not triggering when only moving the mouse horizontally or vertically
- `Map Panel`: Fix draw order issue with multi-tile faces being drawn underneath faces on the same layer
- `Map Panel`: Many smoothing related fixes
- `Map Panel`: Auto adjust text colour of status labels to maintain a good contrast with the background colour
- `Command/Inventory/Quest Panels`: Ensure text is always displayed regardless of theme font size
- `Account/Player/Server Dialogs`: Ensure text is always displayed regardless of theme font size
- `Core`: Fix minor issue generating RTF text for message panel

**Minor Changes:**
- `Knowledge Panel`: Ensure text displays ... when there is more text to display
- `MiniMap Panel`: Make minimum tile size configurable
- `Account Dialog`: Remove darkness protocol override (darkness is configurable via the map settings)
- `Core`: Add ability to create plugins that don't have an associated Game Panel

---

## Crossfire DockWindow Client v0.8.5
### July 13, 2024

**Fixes:**
- `Message Panel`: Fix occasional client deadlock when adding messages to message panel
- `Main Window`: Display game panel load errors on startup
- `Main Window`: Don't stop loading game panels after first game panel load failure
- `Main Window`: Fix race condition where server login screen occasionally fails to display
- `Game Panels`: Fix null references that appear when using different OS and .NET versions

**Minor Changes:**
- `Message Panel`: Add button to scroll to end of messages
- `Message Panel`: Scroll to end of message when changing font size
- `Layouts`: Include layouts inside setup project
- `Themes`: Include themes inside setup project

---

## Crossfire DockWindow Client v0.8.4
### June 28, 2024

> - Map Rewrite Release
> - Over 100 map related commits in this release!

**New Features & Notable Changes:**
- `Message Panel`
  - Add configuration option to limit the number of messages in the message panel
- `Map Panel`
  - Re-implement map data storage for faster access
    - Map no longer grinds to a halt when containing lots of fog of war information
  - Re-implement map drawing routines to simplify and speed up map updates
  - Add new map viewport options
    - Custom viewport sizes
    - Map zoom (scale factor)
  - Add new map display options
    - Fog of war colour schemes
    - Darkness dark factor
  - Zoom in and out works without changing the map size and losing map data
- `Protocol`
  - Move mapsize protocol level configuration to server settings
    - The mapsize protocol value is now independent of the map display, and will default to the largest available mapsize unless explicitly set to a fixed size

**Minor Changes:**
- `Knowledge Panel`: Bind middle click to attempt alchemy
- `Map Panel`: Default map scale algorithm to nearest-neighbour make display more pixelated
- `Map Panel`: Default map fog of war style to sepia to highlight fog of war vs darkness
- `Map Panel`: Add new local command _mapzoom_ to set zoom / scale factor
- `Map Panel`: Add new local command _mapzoomreset_ to reset zoom back to 100%
- `MiniMap Panel`: As the minimap panel now shares drawing code with the map panel, all map related enhancements are available to the minimap
- `MiniMap Panel`: Center minimap on player when minimap gets too large to display

**Fixes:**
- `Character Panel`: Fix issue displaying X-Ray status
- `Inventory Panel`: Fix crash when performing action on unselected item
- `MiniMap Panel`: Fix issue where minimap dissapears when it is too large
- `Animations`: Fix issue not animating random synchonized animations
- `Main Window`: Fix crash performing layout
- `Themes`: Update hard to read message text colour on parchment theme

---

## Crossfire DockWindow Client v0.8.3
### May 29, 2024

**New Features & Notable Changes:**
- `Inventory Panel`
  - Change find toolbar to be toggled on/off via a toolbar button, to reduce toolbar size
- `Message Panel`
  - Drastically improve message redraw times when many messages come in at the same time
  - Use the scrollbar position to determine if new messages should scroll the message panel
  - Add option to always scroll the message panel, regardless of scroll position
- `MiniMap Panel`
  - Drastically improve mini-map redraw times
- `Map Panel`
  - Drastically improve darkness rendering speed
  - Add Player and Communication Labels
  - Add label theme options
- `Themes`
  - Main Window/Toolbar Theme can be changed without a restart
  - Add new theme "Parchment", update "Dark" theme
- `Protocol`
  - Support protocol version 1030

**Minor Changes:**
- `Character Panel`: Minimize calls to update the UI as much as possible
- `Inventory Panel`: Minimize calls to update the UI as much as possible
- `Inventory Panel`: Add different apply choices when dropping an item on to a quick key
- `Inventory Panel`: Add apply -o command to context menu
- `Inventory Panel`: Move player weight from toolbar to titlebar, to reduce toolbar size
- `Map Panel`: Minimize calls to update the UI as much as possible
- `Map Panel`: Add option to render Fog of War as Sepia instead of GrayScale
- `Message Panel`: Copy hyperlinks to clipboard on click
- `MiniMap Panel`: Add player and viewport highlighting as an option
- `Main Window`: Load main window menu and toolbar layouts from game data
- `Main Window`: Minor re-org of toolbar display
- `Settings`: Add options to enable admin, experimental, secondary, and debug panels
- `Core`: Add performance monitor while in debug mode to help improve the overall experience

**Fixes:**
- `MiniMap Panel`: Fix player dash offset animation stopping when left running for a long time
- `Skill Panel`: Re-align skills when a new skill is added
- `Spell Panel`: Re-align spells when a new spell is added
- `Commands`: Fix missing help commands (death, mode, move)
- `Core`: Add some protections arround accessing the underlying array of an Expanding2DArray
- `Core`: Ensure & are displayed in formatted message boxes
- `Protocol`: Work around skill_extra not existing on older servers
- `Themes`: Change how colours are written to settings to avoid settings loss
- `Core`: Fix potential crash on exit

**Hacks:**
- `Message Panel`: Scroll to end of messages during panel resize
  - This avoids issues where the scroll position changes and scrolling does not occur

---

## Crossfire DockWindow Client v0.8.2
### April 20, 2024

**New Features & Notable Changes:**
- `Keybinds`
  - Add ability to have keybinds with multiple modifiers
  - Move default keybinds to game data to allow new keybinds to be added with new releases
    - Note that default keybinds are application level, and are separate from global/character keybinds
- `Message Panel`
  - Add ability to set command repeat (used for dimension door)
  - Add localcommands _setrepeat_ and _addrepeat_ to set repeat via a hotkey
- `Notes Panel`
  - Add ability to zoom the text of the notes panel
- `Resistance Panel`
  - Add new panel for displaying character resistances

**Minor Changes:**
- `Character Panel`: Add description indicating stat highlighting can be disabled
- `Inventory Panel`: Refocus map when pressing ESC from inventory toolbar controls
- `Spell Panel`: Allow spell attune/repel/deny highlighting to be disabled
- `Spell Panel`: Add explicit commands to invoke spells with an argument
- `Message Panel`: Clean up message type descriptions, fix spelling and case

**Fixes:**
- `Main Window`: Reset a game panel if the loaded layout does not include that panel
- `Main Window`: Update about box with contact information
- `MiniMap Panel`: Don't draw null maps
- `Item Manager`: Fix crash where server adds an item that already exists, but none of the item properties changed

---

## Crossfire DockWindow Client v0.8.1
### April 11, 2024

**New Features & Notable Changes:**
- `Main Window`
  - Add (and move) server commands to main window toolbar
  - Add server help to main window menu
- `Gameplay`
  - Add option to inhibit applying items from containers
- `Map Panel`
  - Add ability to configure scaling algorithm
- `Message Panel`
  - Add ability to configure message filters per message panel
  - Add alternate message panel
- `Pickup Panel`
  - Add saving pickup value and pickup commands to a QuickKey
- `Spell Panel`
  - Add theme settings for highlighting attuned/repelled/denied spells
- `Plugins` -> `IRC`
  - Add IRC text colour and text formatting

**Minor Changes:**
- `Settings`: Minor moving and renaming settings and settings groups for ease of use and discoverability
- `Knowledge Panel`: Add options to change mouse wheel scrolling behaviour
- `Commands`: Update some command definitions
- `Choose Player Dialog`: Show connected server
- `Create Player Dialog`: Show connected server
- `MiniMap Panel`: Set graphics scaling modes to high speed
- `Pickup Panel`: Add pickup help and commands to context menu

**Fixes:**
- `Game Panels`: Fix issue where custom game panel context menus were not shown
- `Game Panels`: Fix issue where Configure Toolbar option was not shown on panel context menus
- `Inventory Panel`: Fix display size not working after re-org of settings (introduced in 0.8.0)

---

## Crossfire DockWindow Client v0.8.0
### Mar 13, 2024

> - First Public Release!
> - 225 commits since last release!


**New Features & Notable Changes:**
- `Main Window`
  - Add a QuickKey Toolbar to main window
  - Rework menu items
    - Add Theme settings under Options Menu
    - Split Panels menu on main window into Player, Items, Info, Map, Extra menus
    - Rework Layout menu for a better experience
- `Inventory Panel`
  - Add moving items between inventory/ground/open containers via dragging and dropping
  - Add using an item with another via dragging and dropping (player inventory panel only)
- `QuickKeys`
  - Allow spells, skills, inventory items, and selected message text to be dragged then dropped onto a QuickKey/Hotkey button
  - Update HotKeys Panel to use new QuickKey system
- `Character Panel`
  - Add saving current equipment set to a QuickKey
  - Add menu to change stat panel sizes
- `Choose Server Dialog`
  - Show official server at the top of the list, with a star icon
- `Login Dialog`
  - Saved passwords are now encrypted instead of being saved in plain text
  - Changed Save Password option from a global setting to a server setting
  - Show connected server
- `Theme`
  - Split out theme configuration from settings
    - `BREAKING CHANGE`: This change will cause all existing theme related to be lost
  - Add ability to import and export theme
- `Settings`
  - Add ability to import and export settings, player settings
  - Save QuickKeys/Hotkeys per character instead of globally
    - `BREAKING CHANGE`: This change will cause all existing saved hotkeys to be lost
  - Change names of various global / client settings filenames
    - `BREAKING CHANGE`: This change will cause old settings to not be loaded, although the files can be renamed
    - default.layout -> crossfireclient.layout
    - global.keys -> crossfireclient.keys
    - recent.xml -> crossfireclient.serverlist
    - settings.xml -> crossfireclient.settings
  - Move some settings from one settings page to another
    - `BREAKING CHANGE`: This change will cause these settings to be lost
    - Auto-Commands: OnChoosePlayer, OnChooseMap,
    - Server Fonts: Fixed, Arcane, Handwriting, Strange
    - Message Colours
  - Rename Game Windows to Game Panels. This was a major refactor of file locations, file names, class names, namepsace names
    - `BREAKING CHANGE`: This change will cause some settings pages to be reset to defaults (Map, Message, Notes)
- `Plugins` -> `IRC`
  - Add experimental IRC plugin (under Extra menu when installed)
    - Plugin Location: Plugins\IRC
    - To install a plugin, copy all the files inside a plugin location to the Crossfire DockClient Plugin directory
      - (eg: <InstallDir>\Plugins\ or <PortableDir>\Plugins\)

**Minor Changes:**
- `All Panels`: Change command menu icon to a hamburger menu
- `All Panels`: Right click on a panel bar brings up both settings and theme options for the panel
- `Character Panel`: Add unequip menu item
- `Character Panel`: Many minor adjustments for a better experience
- `Character Panel`: Show spell stats as multiple items
- `Dialogs`: Increase size of link labels
- `Inventory Panel`: Adjust default settings for to showcase available options
- `Item Manager`: Minor speed improvements when adding and searching for items
- `Keybinds`: Adjust default settings for to showcase available options
- `Knowledge Panel`: Adjust default settings for to showcase available options
- `Layouts`: Saved layouts now have a .cfx-layout extension
- `Main Window`: Improve many error and warning messages
- `Main Window`: Settings dialog now contains panel settings
- `Message Box`: Add configuration to change default popup message size
- `Message Panel`: Many minor adjustments for a better experience
- `Minimap Panel`: Highlight player on mini-map
- `Settings`: Rename many settings group names for clarity and consistency
- `Theme`: Add an example theme that can be imported
- `Theme`: Adjust default settings for a better initial experience

**Fixes:**
- `Character Panel`: Fix some minor theming issues on labels
- `Login Dialog`: Ensure faceset selection is based on ID, not order of facesets
- `Message Panel`: Fix issue displaying curly braces and backslashes

**Known Issues:**
- `Inventory Panel`: Listbox smooth scroll temporarily re-appears when the inventory panel re-gains focus via clicking on the scroolbar, then scrolling the listbox with the mousewheel.
  - Clicking on the listbox item instead of the scrollbar does not have this problem.
- `Inventory Panel`: Working with items in the container game panel is very slow (#64)
  - When items in an open container are removed, the server clears and resends all the contained items
- `Main Window`: Can't Use ESC key to close floating windows until it gets focus (#2)

---

## 0.7.8-beta
### Jan 14, 2024

**Fixes:**
- `Plugins`: Fix crash when plugin folder doesn't exist

---

## 0.7.7-beta
### Jan 14, 2024

**New Features & Notable Changes:**
- `Plugins`
  - External plugins (new panels) can be added via by copying them to the Plugins/ folder
- `Skills Panel`
  - Add option to show experience increases and decreases in the message panel
- `Account Login`
  - Show options to change the face set and enable/disable darkness for the session
- `Map Panel`:
  - Add player info block at the bottom of the window (ranged item/type plus item that would be applied)

**Minor Changes:**
- `Character Panel`: Show total available item power
- `Knowledge Panel`: Minor display changes on controls
- `Hotkey Panel`: Added a multiline string editor for editing commands
- `Hotkey Panel`: Allow hotkey bar layout to be changed on the fly
- `Settings`: Added a new multiline string editor for editing commands
- `Client`: Send the program version as the client version string
- Increase size of account and character dialogs and slightly adjust control positions
- Add ability to right click and copy text (with formatting) from messageboxes and lines from the message window to the clipboard
- Remove extra metadata from messageboxes (date/time, etc)
- Save listview column widths as part of the saved layout
- Create an auto-build and auto-package set of scripts
- Add sample layouts

**Fixes:**
- `Protocol`: Fix unicode text in item names not displaying properly
- `Protocol`: Fix sending unicode text to server
- `Inventory Panel`: Fix being unable to apply next/prev pseudo objects in paged containers
- `Inventory Panel`: Fix displaying & in container names
- `Character Panel`: Fix redraw issues when changing panel size

---

## 0.7.6-beta
### October 22, 2023

**Fixes:**
- Fix display issues on MiniMap panel on maps larger than 50x50

---

## 0.7.5-beta
### October 21, 2023

**New Features & Notable Changes:**
- `Inventory Panel`
  - Add find toolbar (simple or regex) to highlight / find inventory items
- `Knowledge Panel`
  - Add filter toolbar (simple or regex) to filter knowledge
- `Keybind Panel`
  - Add themeing, grouping, sorting
  - Additional changes for a better user experience
- `MiniMap Panel`
  - Displays current map in its entirety
  - Saves current map on a map change
  - Experimental: Allows saved maps to be manually merged into current map
- Support skill descriptions (requires server commit 38c711ccdb @ March 18 2023)

**Minor Changes:**
- `Knowledge Panel`: Add sort options
- `Character Panel`: Change bar colours to enhance readability
- `Ground Panel`: Add toolbar settings for new find toolbar
- `Container Panel`: Add toolbar settings for new find toolbar
- `Theme Settings`: Add secondary colour, secondary font, list highlight colour
- Support tilesets other than 32x32
- Add MapDataManager for handling map updates (Currently used by MiniMap)

**Fixes:**
- Load default layout if overridden default layout is not found
- Properly convert UTF strings from server
- Fix focus issues when closing formatted message boxes
- Fix issue displaying metaservers when a single metaserver is unavailable
- Fix display issue on skill large icon view
- Fix default sorting on listviews

---

## 0.7.3-beta
### March 07, 2023

**New Features & Notable Changes:**
- Add command auto-completion
- Add `Dungeon Master` panel with most of the DM commands
- Add new `Inventory` actions to prompt for number of items to pick up/drop
- Add command line arguments to set:
  - DataFolder (-d <folder>)
  - Portable mode (-p)
- DataFolder defaults to %APPDATA%\Crossfire DockWindow Client

**Minor Changes:**
- `Keybind Panel` shows list of all available commands to help with binding
- Add ctrl-backspace to clear command entry, but still keep focus
  - As opposed to escape, which clears the entry and removes focus
- Add icons to some commands
- Enhance `Character Creation` dialog
  - Add colours to stat points to indicate if they are out of range
  - Update error messages and add tooltips

**Fixes:**
- Fix issue using host:ip format when connecting to private servers
- Fix issue where items without a group name are not displayed

---

## 0.7.2-beta
### Feb 08, 2023

**New Features & Notable Changes:**
- Fix some issues where grouping didn't work properly

**Minor Changes:**
- Add numeric column sorting to `Spells` and `Skills` panels
- Clean up grouping on `Skills` panel
- Enhance `Character` panel: Stat colours, DPS display, update some tooltips and labels
- Update some help text

---

## 0.7.1-beta
### July 31, 2022

**New Features & Notable Changes:**
- Allow `Layouts` to be imported and exported
- Consolidate and re-organize `Game Settings`
- Add `Inventory` sorting
- Add Theming for all listviews, treeviews, listboes

**Minor Changes:**
- Move `Inventory` filters to drop down menu
- Save `Inventory` filters and sort options to layout
- Save option to lock docking
- Add option to maximize on startup
- Move Map Window options to main window menu from the options menu
- Add option to theme a secondary foreground colour, use in inventory and quest windows
- Improve speed of initial quest window display

---

## 0.6.0-beta
### Not released

**Major Changes & Updates:**
- Completely rework `Character Panel` with collapsable panels, tooltips
- Completely rewrite toolbar/menu system for windows
  - Commands use external command definitions
  - Menus and toolbars can use external images and command definitions
  - Prompts for commands can have descriptions
  - Toolbar settings are saved with the layout

**New Features & Notable Changes:**
- Reworked `Choose Server Dialog` to look nicer and be more usable
  - Metaservers are always displayed
- Message Panel
  - Cycle through command history with up/down arrows
  - View Command history with new command `history` and `history [value]`
- Inventory Panel
  - Inventory icon overlays for item status
- Note Panel
  - Added new command `note [text]` to add and save a note
- Misc
  - Changed default layout

**Minor Changes:**
- Theming
  - Selected item themeing on lists
- Layouts
  - Store listview view/sort/group orders with the layout
  - Toolbar settings and positions are saved with the layout
- Character Panel
  - Add tooltips to stats/labels for additional information
- Misc
  - Start to add code licenses to move towards an open source release
  - Add status form when connecting to a server
  - Add option to show commands generated from a button/menu item to the message window
  - Configurable character presets for new character creation (Advanced Options)
  - Add ability to override client/server versions for connecting to incompatible servers
  - Add ability to override client version string
  - Support logging into ancient versions of crossfire
  - Added new command `listwindows`
  - Move any saved settings/notes/layouts/etc into a `data subfolder` (portable mode)

**Fixes:**
- Multicommands can now have a space after the semi-colon
- Change order of item colour display to have better colourization of items
- Ensure quests with no parents are still displayed
- Improved connection handling
- Fix display issue with mousewheel mapzoom
- Allow disconnection from the server when in a query dialog
- Fix race condition that was causing ServerProtocolVersion to be cleared after it was set
- Tons of minor fixes

---

## 0.5.0-beta
### Nov 26, 2021

**New Features & Changes:**
- Add full *Fog of War* support
- Allow server message fonts to be changed
- Allow message window mouse wheel scroll amount to be configurable
- Rework inventory item display to use displaysize for layouts
- Rework inventory action menu
- Speed up message window
- Popup messages when applying books,cards,paper,monuments,signs
- Add *character notes window*, to store free-form notes along with the character
- Add *auto-commands* settings, to run user commands on a new map or on choose player
- Add new command `usercommands`, `usercommands help` to list new client commands
- Add new command `echo` to add user information to message window
- Add option to display extra fog of war around map
- Increase messagebox default size, and allow resizing via shift-click
- Allow up/down control to use different increments when using shift/ctrl keys
- Have up/down control to reset on double-click
- Add options for how container inventory works (show inline, use new window)

**Fixes:**
- Fix issues with older servers, such as metalforge
- Fix many map issues (map scroll, offscreen tiles, fog of war)
- Show message form if hidden when pressing the ' key
- Fix loss of formatting and colours in messagewindow when moving around the window
- Fix lots of strange behaviour with the message window
- Fix windows not honouring the theme font
- Set hotkey default keybinds to not use alt modifier
- Fix player/character window flicker while casting spells
- Lots of back end refactoring preparing for source code release

**Known Issues:**
- Multicommands cannot have a space after the semi-colon

---

## 0.4.0-beta
### Nov 11, 2021

**New Features:**
- Rework of settings and the Options Menu, to make settings easier to find and use
- New default layout
- Run/Fire status shows on the status bar
- Window menu shows which windows are visible
- New inventory filter icons
- More formatting options for inventory items
- Toolbars can be toggled on or off
- Help menu has links to the crossfire website and wiki
- Take and Drop menu items now have mouse bindings

**Fixes:**
- The number of updates of the inventory window is much less
- The number of updates to the player window is some less
- The inventory mouse scroll issues have been fixed, and the scroll amount is configurable
- Sometimes keypresses would accidentally be lost, this has been fixed
- The number entry box for drop/take commands now works when using a keybind or text command
- Large amounts of experience display correctly
- A few crashes have been resolved

**Known Issues:**
- The player/character window flickers while casting spells
- Default hotkey bindings (F1-F6) have an alt key modifier, and should not

---

## 0.3.0-beta
### Nov 07, 2021

**New Features:**
- Configurable Hotkey bar
- A magic map that shows walls
- Zoom map via keybinds instead of just mouse wheel
- GTK compatible mouse binding options
- More inventory drawing customizations
- Allow rendering the viewport at 1:1, instead of scaling to fit the pane

**Fixes:**
- Concurrency fixes
- Reducing the number of inventory updates
- Spell argument support

---

## 0.2.0-beta
### Nov 03, 2021
- First release to testers

## First Look  Oct 22, 2021
- Initial showcase of client on twitch
- https://www.youtube.com/watch?v=6Mn-Ytob9Ec

## Aug 10, 2021
- Start of development
