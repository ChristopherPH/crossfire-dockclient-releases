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
