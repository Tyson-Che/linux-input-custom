# Linux Input Hierarchy

This document outlines the layers involved in processing keyboard input on a Linux system with X11.

1. Hardware Level
   - Physical key press sends electrical signal

2. Kernel Level
   - Linux kernel's input subsystem processes the signal
   - Generates input event

3. evdev (Event Device)
   - Generic input driver for Linux
   - Standardizes events for higher-level software

4. X11 Server (e.g., Xorg)
   - Receives standardized events from evdev
   - Manages the graphical environment

5. XKB (X Keyboard Extension)
   - Part of X11 server
   - Interprets events based on current keyboard layout and modifiers
   - Applies any custom mappings or layouts

6. Window Manager / Desktop Environment
   - Receives events from X11
   - Can apply additional mappings or shortcuts

7. Application
   - Receives final processed input

## Tools in the Hierarchy

- `setxkbmap`: Configures keyboard layout and options in XKB
- `xmodmap`: Modifies keymaps in X
- `xcape`: Allows keys to act differently when pressed alone vs. in combination

These tools interact with XKB (level 5 in the hierarchy) to modify how key events are interpreted before they reach applications.
