# CapsLock Mapping Implementation

This document details the process of remapping the CapsLock key to function as Escape when tapped and to switch the input method to English.

## Overview

1. Disable the default CapsLock behavior
2. Map CapsLock to Escape
3. Use xcape to send F12 when Escape (CapsLock) is tapped
4. Use i3wm to catch F12 and run a script to switch input method

## Implementation

### 1. X Session Startup (.xprofile)

```bash
# Disable CapsLock
setxkbmap -option caps:none

# Map CapsLock to Escape
xmodmap -e 'keycode 66 = Escape NoSymbol Escape'

# Use xcape to make a tap on Escape send F12
xcape -e 'Escape=F12'
