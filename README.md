# Crossfire DockWindow Client (DockClient)

    WARNING! This software is NOT SUPPORTED and NOT ENDORSED
             by the official Crossfire project or Crossfire 
             developers!

This is an **unofficial** game client for **Crossfire: The Multiplayer Adventure Game**

**Official** clients can be found at:
- http://crossfire.real-time.com/clients/index.html

More information about Crossfire:
- http://crossfire.real-time.com
- https://sourceforge.net/projects/crossfire/

How to Play Crossfire:
- http://crossfire.real-time.com/guides/
- http://crossfire.real-time.com/guides/handbook/index.html


## Brief History of the Crossfire DockWindow Client
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


## Roadmap
- More options and customization, such as:
	- Customization of mouse controls for actions (click/right click, shift click, etc are all customizable per panel)
- Adding the ability to create new instances of existing panels
	- Multiple message panels (player chats, party, dm etc)
	- Multiple inventory panels with different views, groups, sorts
- More plugin functionality
	- New commands, protocol messages
- High DPI support
- Alias system
	- Similar to keybinds, but for the user to create new commands instead of keypresses

## Building
 1. Open `Crossfire.sln` with Visual Studio 2022 Community Edition
 2. Build Solution

> Note: It is possible that some nuget packages will need to be downloaded to compile this application.

> Note: To build the setup project, install the VS extension "Microsoft Visual Studio Installer Projects"
