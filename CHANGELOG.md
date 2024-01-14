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
