[![Build Status](https://travis-ci.org/lafarer/ansible-role-osx-defaults.svg?branch=master)](https://travis-ci.org/lafarer/ansible-role-osx-defaults)

# osx-defaults

Ansible role to configure defaults on OSX.

## Requirements

Ansible 2.0

## Role Variables

```
AppStore:
  ScheduleFrequency: 7                        # Check for software updates (in days)
  AutomaticCheckEnabled: "false"              # Automatically check for updates
  AutomaticDownload: "false"                  # Download newly available updates in the background
  AutoUpdate: "false"                         # Install app updates
  AutoUpdateRestartRequired: "false"          # Install OSX updates
  ConfigDataInstall: "false"                  # Install system data files
  CriticalUpdateInstall: "false"              # Install security updates
```

```
Dashboard:
  McxDisabled: "true"                         # Disable Dashboard
  EnabledState: 1                             # Dashboard state (1: Off, 2: As Space, 3: As Overlay)
  DontShowAsSpace: "true"                     # Don’t show Dashboard as a Space
  DevMode: "false"                            # Enable Dashboard dev mode (allows keeping widgets on the desktop)
```

```
DateTime:
  TimeZone: "Europe/Brussels"                 # Set the timezone; see `systemsetup -listtimezones` for other values
  AutomaticDateTime: "on"                     # Set date and time automatically (on | off)
  TimeServer: "time.apple.com"                # Set time server
  AutomaticTimeZone: "true"                   # Set time zome automatically using current location
  DateFormat: "HH:mm"                         # Menu bar clock format ("h:mm": Default, "HH": Use a 24-hour clock, "a": Show AM/PM, "ss": Display the time with seconds
  FlashDateSeparators: "false"                # Flash the time separators
  IsAnalog: "false"                           # Analog menu bar clock
```

```
Displays:
  AutomaticallyAdjustBrightness: "true"       # Automatically adjust brightness
  AppleFontSmoothing: 2                       # Subpixel font rendering on non-Apple LCDs (0:Disabled, 1:Minimal, 2:Medium, 3:Smoother, 4:Strong)
  DisplayResolutionEnabled: "true"            # Enable HiDPI display modes (requires restart)
  ShowInMenuBarIfPresent: "true"              # Show mirroring options in the menu bar when available
```

```
Dock:
  TileSize: 32                                # Dock size
  Autohide: "true"                            # Automatically hide and show the Dock
  Magnification: "true"                       # Dock magnification
  LargeSize: 64                               # Icon size of magnified Dock items
  MinEffect: "genie"                          # Minimization effect: genie, scale, suck
  Orientation: "bottom"                       # Dock orientation: left, bottom, right
  ShowHidden: "true"                          # Display translucent Dock icons for hidden applications
```

```
General:
  AppleAquaColorVariant: 1                    # Set appearance (1: Blue, 6: Graphite)
  AppleHighlightColor: "Blue"                 # Highlight color (Red, Orange, Yellow, Green, Blue, Purple, Pink, Brown, Graphite)
  AppleInterfaceStyle: ""                     # Use Dark menu bar and Dock (Empty or "Dark")
  AutoHideMenuBar: "false"                    # Automatically hide and show the menu bar
  NSTableViewDefaultSizeMode: 1               # Sidebar icon size (Small: 1, Medium: 2, Large: 3)
  AppleShowScrollBars: "Automatic"            # Scroll bar visibility (WhenScrolling, Automatic, Always)
  NSScrollAnimationEnabled: "true"            # Smooth scrolling (Disable on older Macs)
  NSQuitAlwaysKeepsWindows: "false"           # Close windows when quitting an application
```

```
Keyboard:
  PressAndHoldEnabled: "true"                 # Disable press-and-hold for keys in favor of key repeat
  KeyRepeat: 0                                # Set key repeat rate (Off: 300000, Slow: 120, Fast: 2)
  InitialKeyRepeat: 10                        # Set delay until repeat, in milliseconds (Long: 120, Short: 15)
  kDim: "true"                                # Adjust keyboard brightness in low light
  kDimTime: 300                               # Dim keyboard after idle time (in seconds)
  AppleKeyboardUIMode: 3                      # Full Keyboard Access (1 : Text boxes and lists only, 3 : All controls)
  fnState: "false"                            # Use F1, F2, etc. keys as standard function keys
  AutomaticQuoteSubstitutionEnabled: "false"  # Use smart quotes
  AutomaticDashSubstitutionEnabled: "false"   # Use smart dashes
  AutomaticSpellingCorrectionEnabled: "false" # Correct spelling automatically
  PowerButtonSleepsSystem: "false"            # Prevent accidental Power button presses from sleeping system
```

```
MissionControl:
  MruSpaces: "false"                          # Automatically rearrange Spaces based on most recent use
  SwitchOnActivate: "true"                    # When switching to an application, switch to a Space with open windows for the application
  GroupByApp: "true"                          # Group windows by application in Mission Control
  SpansDisplays: "true"                       # Displays have separate Spaces

```

## Dependencies

## Example Playbook

```
    - hosts: servers
      vars:

      roles:
         - { role: lafarer.osx-defaults }
```

## License

BSD

## Author Information

