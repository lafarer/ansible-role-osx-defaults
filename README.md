[![Build Status](https://travis-ci.org/lafarer/ansible-role-osx-defaults.svg?branch=master)](https://travis-ci.org/lafarer/ansible-role-osx-defaults)

# osx-defaults

Ansible role to configure defaults on OSX.

## Requirements

Ansible 2.0

## Role Variables

```
AppStore_Enabled: false                          # Enable AppStore configuration
AppStore_AutomaticCheckEnabled: false            # Automatically check for updates
AppStore_AutomaticDownload: false                # Download newly available updates in the background
AppStore_AutoUpdate: false                       # Install app updates
AppStore_AutoUpdateRestartRequired: false        # Install OSX updates
AppStore_ConfigDataInstall: false                # Install system data files
AppStore_CriticalUpdateInstall: false            # Install security updates
AppStore_ScheduleFrequency: 7                    # Check for software updates (in days)
AppStore_ShowDebugMenu: false                    # Show debug menu
```

```
Bluetooth_Enabled: false                         # Enable Bluetooth configuration
Bluetooth_ShowInMenuBar: "false"                 # Show Bluetooth in menu bar
```

```
Dashboard_Enabled: false                         # Enable Dashboard configuration
Dashboard_McxDisabled: true                      # Disable Dashboard
Dashboard_EnabledState: 1                        # Dashboard state (1: Off, 2: As Space, 3: As Overlay)
Dashboard_DontShowAsSpace: true                  # Don’t show Dashboard as a Space
Dashboard_DevMode: false                         # Enable Dashboard dev mode (allows keeping widgets on the desktop)
```

```
DateTime_Enabled: false                          # Enable Date Time configuration
DateTime_TimeZone: "Europe/Brussels"             # Set the timezone; see `systemsetup -listtimezones` for other values
DateTime_AutomaticDateTime: "on"                 # Set date and time automatically (on | off)
DateTime_TimeServer: "time.apple.com"            # Set time server
DateTime_AutomaticTimeZone: true                 # Set time zome automatically using current location
DateTime_DateFormat: "h:mm"                      # Menu bar clock format ("h:mm": Default, "HH": Use a 24-hour clock, "a": Show AM/PM, "ss": Display the time with seconds
DateTime_FlashDateSeparators: false              # Flash the time separators
DateTime_IsAnalog: false                         # Analog menu bar clock
```

```
Displays_Enabled: false                          # Enable Displays configuration
Displays_AutomaticallyAdjustBrightness: false    # Automatically adjust brightness
Displays_ShowInMenuBarIfPresent: true            # Show mirroring options in the menu bar when available
Displays_AppleFontSmoothing: 2                   # Subpixel font rendering on non-Apple LCDs (0:Disabled, 1:Minimal, 2:Medium, 3:Smoother, 4:Strong)
Displays_DisplayResolutionEnabled: true          # Enable HiDPI display modes (requires restart)
```

```
Dock_Enabled: false                              # Enable Dock configuration
Dock_TileSize: 64                                # Dock size
Dock_Magnification: true                         # Dock magnification
Dock_LargeSize: 128                              # Icon size of magnified Dock items
Dock_Orientation: "bottom"                       # Dock orientation: left, bottom, right
Dock_MinEffect: "genie"                          # Minimization effect: genie, scale, suck
Dock_AppleActionOnDoubleClick: "Maximize"        # Double-click a window's title title bar to: None, Minimize, Maximize
Dock_MinimizeToApplication: false                # Minimize windows appliction into icon (true, false)
Dock_LaunchAnim: true                            # Animate opening applications
Dock_Autohide: false                             # Automatically hide and show the Dock
Dock_ShowProcessIndicators: true                 # Show indicator for open applications
Dock_ShowHidden: false                           # Display translucent Dock icons for hidden applications
```

```
General_Enabled: false                           # Enable General configuration
General_AppleAquaColorVariant: 1                 # Set appearance (1: Blue, 6: Graphite)
General_AppleInterfaceStyle: ""                  # Use Dark menu bar and Dock (Empty or "Dark")
General_AutoHideMenuBar: false                   # Automatically hide and show the menu bar
General_AppleHighlightColor: "Blue"              # Highlight color (Red, Orange, Yellow, Green, Blue, Purple, Pink, Brown, Graphite)
General_SidebarIconSize: 1                       # Sidebar icon size (Small: 1, Medium: 2, Large: 3)
General_AppleShowScrollBars: "Automatic"         # Scroll bar visibility (WhenScrolling, Automatic, Always)
General_AppleScrollerPagingBehavior: 0           # Click in the scrollbar to (0: Jump to the next page, 1: Jump to the spot that's clicked)
General_NSCloseAlwaysConfirmsChanges: false      # Ask to keep changes when closing documents
General_CloseWindowsWhenQuittingApp: false       # Close windows when quitting an application
General_NSScrollAnimationEnabled: true           # Smooth scrolling (Disable on older Macs)
```

```
ICloud_Enabled: false                            # Enable iCloud configuration
ICloud_NSDocumentSaveNewDocumentsToCloud: true   # Save to iCloud by default
```

```
Keyboard_Enabled: false                            # Enable Keyboard configuration
Keyboard_KeyRepeat: 0                              # Set key repeat rate (Off: 300000, Slow: 120, Fast: 2)
Keyboard_InitialKeyRepeat: 10                      # Set delay until repeat, in milliseconds (Long: 120, Short: 15)
Keyboard_fnState: false                            # Use F1, F2, etc. keys as standard function keys
Keyboard_kDim: false                               # Adjust keyboard brightness in low light
Keyboard_kDimTime: 0                               # Dim keyboard after idle time (in seconds, 0 is Never)
Keyboard_AutomaticSpellingCorrectionEnabled: false # Correct spelling automatically
Keyboard_AutomaticQuoteSubstitutionEnabled: false  # Use smart quotes
Keyboard_AutomaticDashSubstitutionEnabled: false   # Use smart dashes
Keyboard_AppleKeyboardUIMode: 3                    # Full Keyboard Access (1 : Text boxes and lists only, 3 : All controls)
Keyboard_PowerButtonSleepsSystem: false            # Prevent accidental Power button presses from sleeping system
Keyboard_PressAndHoldEnabled: false                # Disable press-and-hold for keys in favor of key repeat
```

```
LanguageRegion_Enabled: false                    # Enable Language and Region configuration
LanguageRegion_Languages: [ "en", "fr" ]         # Preferred languages (in order of preference e.g. [ "en", "fr" ])
LanguageRegion_Locale: "en_US@currency=USD"      # Locale and Currency (United States : en_US@currency=USD, Great Britian : en_GB@currency=EUR)
LanguageRegion_MeasurementUnits: "Inches"        # Measure Units (Inches, Centimeters)
LanguageRegion_Force24HourTime: "true"           # Force 12/24 hour time
LanguageRegion_MetricUnits: "false"              # Set Metric Units
```

```
MissionControl_Enabled: false                    # Enable Mission Control configuration
MissionControl_MruSpaces: false                  # Automatically rearrange Spaces based on most recent use
MissionControl_SwitchOnActivate: true            # When switching to an application, switch to a Space with open windows for the application
MissionControl_GroupByApp: true                  # Group windows by application in Mission Control
MissionControl_SpansDisplays: true               # Displays have separate Spaces
```

## Dependencies

## Example Playbook

```
    - hosts: servers
      vars:
        Bluetooth_Enabled: true
        Bluetooth_ShowInMenuBar: false

      roles:
         - { role: lafarer.osx-defaults }
```

## License

BSD

## Author Information
