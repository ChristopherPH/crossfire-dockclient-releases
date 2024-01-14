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

## Notable Features
- More Accessible for new and returning players
	- Adheres more to Windows UI standards compared to other clients
	- Consistent UX throughout the application
	- Mouse friendly interface, with right click context menus for actions and command help
	- Each dockable window has a toolbar and context menu with related options and actions (Also accessible via right click on the title or via down arrow in toolbar)
- Utilizes a Dockable Window System
	- Windows are movable, dockable, floatable, and rearrangeable on the fly
	- Support for multiple saved window layouts (global, per character, and multiple custom layouts)
	- Layouts are switchable via keybinds or when selecting a character to play
- Completely Theme-able
	- Background/Foreground colours, font styles and sizes are changeable on the fly
	- Each dockable window provides additional customization, eg:
		- Inventory item colours and display can be changed based on item info
		- Message colors can be overridden based on category
		- Row heights and icon sizes can be changed in listboxes
		- List views can be sorted, grouped, and support multiple view types (details, icon, etc)
- Other minor but useful changes
	- Supports quest list and knowledge window like the Java client
	- Open containers pop up a new inventory window to display their contents
	- Map window scales to screen and is easily zoomable, or map scale can be changed via a fixed amount
	- Message window display can be zoomed in or out
	- Can hide or show any window via keybinds
	- Hotkey bar
	- Character Notes window
	- New client only commands:
		- Type 'usercommands' or 'usercommands help' to see the list
    - Native windows application
		- Minimal dependencies and dlls
		- Small install size (~2mb)

## Roadmap
- More options and customization, such as:
	- Customization of mouse controls for actions (click/right click, shift click, etc are all customizable per window)
	- Theming per character
- Adding the ability to create new instances of existing windows
	- Multiple message windows (player chats, party, dm etc)
	- Multiple inventory windows with different views, groups, sorts
- Plugin capable for new functionality
	- New commands, protocol messages
- High DPI support
- Alias system
	- Similar to keybinds, but for the user to create new commands instead of keypresses
