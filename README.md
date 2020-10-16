[![Build Status](https://travis-ci.org/lafarer/ansible-role-osx-defaults.svg?branch=master)](https://travis-ci.org/lafarer/ansible-role-osx-defaults)

# osx-defaults

Ansible role to configure defaults on OSX.

## Requirements

Ansible 2.0

## Role Variables
```
target_user_id: "{{ ansible_user_id }}"          # Define the username for which you want to apply the configurations
```

```
# retro compatibility with old *_Enabled variable name is maintained

Configure_ActivityMonitor: no                    # Enable ActivityMonitor configuration
Configure_AppStore: no                           # Enable AppStore configuration
Configure_ApplicationFirewall: no                # Enable Application Firewall
Configure_Bluetooth: no                          # Enable Bluetooth configuration
Configure_Dashboard: no                          # Enable Dashboard configuration
Configure_DateTime: no                           # Enable Date Time configuration
Configure_DesktopScreenSaver: no                 # Enable Desktop and Screen Saver configuration
Configure_DiskImages: no                         # Enable DiskImages configuration
Configure_Displays: no                           # Enable Displays configuration
Configure_Dock: no                               # Enable Dock configuration
Configure_EnergySaver: no                        # Enable Energy Saver configuration
Configure_Finder: no                             # Enable Finder configuration
Configure_General: no                            # Enable General configuration
Configure_HotCorners: no                         # Enable Hot Corners configurations
Configure_iCloud: no                             # Enable iCloud configuration
Configure_Keyboard: no                           # Enable Keyboard configuration
Configure_LanguageRegion: no                     # Enable Language and Region configuration
Configure_LaunchServices: no                     # Enable Launch Services configuration
Configure_LoginWindow: no                        # Enable Launch Services configuration
Configure_MissionControl: no                     # Enable Mission Control configuration
Configure_Safari: no                             # Enable Safari configuration
Configure_SetupAssistant: no                     # Enable Setup Assistant configuration
Configure_Spotlight: no                          # Enable Spotlight configuration
Configure_Trackpad: no                           # Enable Trackpad configuration
```
When a toggle for a component is enabled than the role will take in consideration the variables dedicated to the specific component as list below.


```
ActivityMonitor_OpenMainWindow: "Disabled"       # Show the main window when launching Activity Monitor
ActivityMonitor_IconType: ""                     # Activity Monitor Dock icon
                                                 # Show Application Icon
                                                 # Show Network Usage
                                                 # Show Disk Activity
                                                 # Show CPU Usage
                                                 # Show CPU History
ActivityMonitor_ShowCategory: ""                 # Show all processes in Activity Monitor
                                                 # Show All Processes
                                                 # Show All Processes, Hierarchically
                                                 # My Processes
                                                 # System Processes
                                                 # Other Processes
                                                 # Active Processes
                                                 # Inactive Processes
                                                 # Windowed Processes
                                                 # GPU Processes
```

```
AppStore_AutomaticCheckEnabled: no               # Automatically check for updates
AppStore_AutomaticDownload: no                   # Download newly available updates in the background
AppStore_AutoUpdate: no                          # Install app updates
AppStore_AutoUpdateRestartRequired: no           # Install OSX updates
AppStore_ConfigDataInstall: no                   # Install system data files
AppStore_CriticalUpdateInstall: no               # Install security updates
AppStore_ScheduleFrequency: 7                    # Check for software updates (in days)
AppStore_ShowDebugMenu: no                       # Show debug menu
```

```
ApplicationFirewall_GlobalState: "Off"           # "On", "Off", "Block All Incoming Connections"
ApplicationFirewall_AllowDownloadSigned: "Disabled"  # Automatically allow downloaded signed software to receive incoming connections
ApplicationFirewall_AllowSigned: "Disabled"      # Automatically Allow built-in software to receive incoming connections - s0 Disable, 1 Enable
ApplicationFirewall_Logging: "Disabled"          # Set logging to on or off - 0 Disable, 1 Enable
ApplicationFirewall_LoggingOption: "Throttled"   # Logging options: "Throttled", "Brief", "Detail"
ApplicationFirewall_Stealth: "Disabled"          # Enable stealth mode
```

```
Bluetooth_ShowInMenuBar: no                      # Show Bluetooth in menu bar
```

```
Dashboard_McxDisabled: yes                       # Disable Dashboard
Dashboard_EnabledState: 1                        # Dashboard state (1: Off, 2: As Space, 3: As Overlay)
Dashboard_DontShowAsSpace: yes                   # Don’t show Dashboard as a Space
Dashboard_DevMode: no                            # Enable Dashboard dev mode (allows keeping widgets on the desktop)
```

```
DateTime_TimeZone: "Europe/Brussels"             # Set the timezone; see `systemsetup -listtimezones` for other values
DateTime_AutomaticDateTime: "on"                 # Set date and time automatically (on | off)
DateTime_TimeServer: "time.apple.com"            # Set time server
DateTime_AutomaticTimeZone: yes                  # Set time zome automatically using current location
DateTime_DateFormat: "h:mm"                      # Menu bar clock format ("h:mm": Default, "HH": Use a 24-hour clock, "a": Show AM/PM, "ss": Display the time with seconds
DateTime_FlashDateSeparators: no                 # Flash the time separators
DateTime_IsAnalog: no                            # Analog menu bar clock
```

```
DesktopScreenSaver_BackGroundImage: ""           # Background image
DesktopScreenSaver_askForPassword: "Disable"     # Require password after sleep or screen saver begins
```

```
DiskImages_SkipVerify: no                        # Skip Verification
DiskImages_SkipVerifyLocked: no                  # Skip Verification for Locked Disk Images
DiskImages_SkipVerifyRemote: no                  # Skip Verification for Remote Disk Images
```

```
Displays_AutomaticallyAdjustBrightness: no       # Automatically adjust brightness
Displays_ShowInMenuBarIfPresent: yes             # Show mirroring options in the menu bar when available
Displays_AppleFontSmoothing: "Medium"            # Subpixel font rendering on non-Apple LCDs (0:Disabled, 1:Minimal, 2:Medium, 3:Smoother, 4:Strong)
Displays_DisplayResolutionEnabled: yes           # Enable HiDPI display modes (requires restart)
```

```
Dock_PersistentApps: []                          # A plain path string, if empty [] it won't change anything
  # - /Applications/Safari.app
  # - /Applications/System Preferences.app
Dock_PersistentOthers: []                        # Either a plain path string or a dict like "{path: /path, type: [file | directory], arrange: [1-5] }"
  # - /Applications/Setapp
  # - { path: "~/Library/Downloads", type: directory, arrange: 2}
  # - { path: "/Applications/Firefox.app", type: file, arrange: 3}
Dock_TileSize: 64                                # Dock size
Dock_Magnification: yes                          # Dock magnification
Dock_LargeSize: 128                              # Icon size of magnified Dock items
Dock_Orientation: "bottom"                       # Dock orientation: left, bottom, right
Dock_MinEffect: "genie"                          # Minimization effect: genie, scale, suck
Dock_AppleActionOnDoubleClick: "Maximize"        # Double-click a window's title title bar to: None, Minimize, Maximize
Dock_MinimizeToApplication: no                   # Minimize windows appliction into icon (yes, no)
Dock_LaunchAnim: yes                             # Animate opening applications
Dock_Autohide: no                                # Automatically hide and show the Dock
Dock_AutohideTimeModifier: 0                     # 0 - Disable, other Int value - Define Animation timing when hiding/showing the Dock
Dock_ShowProcessIndicators: yes                  # Show indicator for open applications
Dock_ShowHidden: no                              # Display translucent Dock icons for hidden applications
Dock_MouseOverHiliteStack: yes                   # Enable highlight hover effect for the grid view of a stack (Dock)
```

```
EnergySaver_ComputerSleepTime: "Never"           # Never, or number of minutes
EnergySaver_DisplaySleepTime: "10"               # Never, or number of minutes
```

```
Finder_ShowHardDrivesOnDesktop: no               # Show hard drives on the desktop
Finder_ShowExternalHardDrivesOnDesktop: yes      # Show external hard drives on the desktop
Finder_ShowRemovableMediaOnDesktop: yes          # Show CDs,DVDs and iPods on the desktop
Finder_ShowMountedServersOnDesktop: no           # Show connected servers on the desktop
Finder_NewWindowTarget: "All My Files"           # New Finder windows shows ("Computer", "Computer's HD", "Home", "Desktop", "Documents", "All My Files" )
Finder_FinderSpawnTab: yes                       # Open folders in tabs instead of new windows
Finder_AppleShowAllExtensions: no                # Show all fiename extensions
Finder_FXEnableExtensionChangeWarning: yes       # Show warning before changing an extension
Finder_WarnOnEmptyTrash: no                      # Show warning before emptying the trash
Finder_FXDefaultSearchScope: "SCev"              # When performing a search (SCev:Search This Mac, SCcf:Search the Current Folder, SCsp:Use the Previous Search Scope)
Finder_AppleShowAllFiles: no                     # Show hidden files
Finder_FXPreferredViewStyle: "icnv"              # View as (icnv:Icons, Nlsv:List, clmv:Column, Flwv:Cover Flow)
Finder_FXPreferredGroupBy: "None"                # Arrange By (None, Name, Application Category, Date Last Opened, Date Added, Size, Finder Tags)
Finder_ShowTabView: yes                          # Show Tab Bar
Finder_ShowPathbar: no                           # Show Path Bar
Finder_ShowStatusBar: no                         # Show Status Bar
Finder_ShowSidebar: yes                          # Show Side Bar
Finder_ColumnShowIcons: yes                      # Show Preview
Finder_FXShowPosixPathInTitle: no                # Show full POSIX path as Finder window title
Finder_QuitMenuItem: no                          # Allow quitting via ⌘ + Q
Finder_QLEnableTextSelection: no                 # Select and Copy Text from Quick Look
Finder_DSDontWriteNetworkStores: no              # if set to 'yes' prevents .DS_Store files to be written on network devices
Finder_DVSIVSarrangeBy: grid                     # Desktop, Enable snap-to-grid for icons on the desktop and in other icon views
Finder_DVSIVSiconSize: 64                        # Desktop, Set the size of icons on the desktop and in other icon views
Finder_DVSIVSshowItemInfo: no                    # Desktop, Show item info near icons on the desktop and in other icon views
Finder_DVSIVSgridSpacing: 54                     # Desktop, Increase grid spacing for icons on the desktop and in other icon views
Finder_DVSIVSlabelOnBottom: yes                  # Desktop, Show item info to the right of the icons on the desktop
Finder_SVSIVSarrangeBy: grid                     # Standard, Enable snap-to-grid for icons on the desktop and in other icon views
Finder_SVSIVSiconSize: 64                        # Standard, Set the size of icons on the desktop and in other icon views
Finder_SVSIVSshowItemInfo: no                    # Standard, Show item info near icons on the desktop and in other icon views
Finder_SVSIVSgridSpacing: 54                     # Standard, Increase grid spacing for icons on the desktop and in other icon views
```

```
General_AppleAquaColorVariant: 1                 # Set appearance (1: Blue, 6: Graphite)
General_AppleInterfaceStyle: ""                  # Use Dark menu bar and Dock (Empty or "Dark")
General_AutoHideMenuBar: no                      # Automatically hide and show the menu bar
General_AppleHighlightColor: "Blue"              # Highlight color (Red, Orange, Yellow, Green, Blue, Purple, Pink, Brown, Graphite)
General_SidebarIconSize: 1                       # Sidebar icon size (Small: 1, Medium: 2, Large: 3)
General_AppleShowScrollBars: "Automatic"         # Scroll bar visibility (WhenScrolling, Automatic, Always)
General_AppleScrollerPagingBehavior: 0           # Click in the scrollbar to (0: Jump to the next page, 1: Jump to the spot that's clicked)
General_NSCloseAlwaysConfirmsChanges: no         # Ask to keep changes when closing documents
General_CloseWindowsWhenQuittingApp: no          # Close windows when quitting an application
General_NSScrollAnimationEnabled: yes            # Smooth scrolling (Disable on older Macs)
```

```
HotCorners_AvailableModifiers:
    - { name: "Enabled", value: 0 }
    - { name: "Disabled", value: 1048576 }
HotCorners_AvailableActions:
    - { name: "no-op", value: 0 }
    - { name: "Disabled", value: 1 }
    - { name: "Mission Control", value: 2 }
    - { name: "Show Application Windows", value: 3 }
    - { name: "Desktop", value: 4 }
    - { name: "Start Screen Saver", value: 5 }
    - { name: "Disable Screen Saver", value: 6 }
    - { name: "Dashboard", value: 7 }
    - { name: "Put Display To Sleep", value: 10 }
    - { name: "Launchpad", value: 11 }
    - { name: "Notification Center", value: 12 }
HotCorners_BottomLeftModifier: "Enabled"         # Enabled, Disabled
HotCorners_BottomRightModifier: "Enabled"        # Enabled, Disabled
HotCorners_TopLeftModifier: "Disabled"           # Enabled, Disabled
HotCorners_TopRightModifier: "Enabled"           # Enabled, Disabled
HotCorners_BottomLeftAction: "Mission Control"   # Chose one of the availlable actions
HotCorners_BottomRightAction: "Show Application Windows" # Chose one of the availlable actions
HotCorners_TopLeftAction: "Disabled"             # Chose one of the availlable actions
HotCorners_TopRightAction: "Desktop"             # Chose one of the availlable actions
```

```
ICloud_NSDocumentSaveNewDocumentsToCloud: yes    # Save to iCloud by default
```

```
Keyboard_KeyRepeat: 0                            # Set key repeat rate (Off: 300000, Slow: 120, Fast: 2)
Keyboard_InitialKeyRepeat: 10                    # Set delay until repeat, in milliseconds (Long: 120, Short: 15)
Keyboard_fnState: no                             # Use F1, F2, etc. keys as standard function keys
Keyboard_kDim: no                                # Adjust keyboard brightness in low light
Keyboard_kDimTime: 0                             # Dim keyboard after idle time (in seconds, 0 is Never)
Keyboard_AutomaticSpellingCorrectionEnabled: no  # Correct spelling automatically
Keyboard_AutomaticQuoteSubstitutionEnabled: no   # Use smart quotes
Keyboard_AutomaticDashSubstitutionEnabled: no    # Use smart dashes
Keyboard_AutomaticPeriodSubstitutionEnabled: no  # Automatic period substitution
Keyboard_AppleKeyboardUIMode: "All controls"     # Full Keyboard Access (1 : Text boxes and lists only, 3 : All controls)
Keyboard_PowerButtonSleepsSystem: no             # Prevent accidental Power button presses from sleeping system
Keyboard_PressAndHoldEnabled: no                 # Disable press-and-hold for keys in favor of key repeat
```

```
#TODO: https://github.com/ansible/ansible-modules-extras/issues/2610
#LanguageRegion_Languages: [ "en", "fr" ]        # Preferred languages (in order of preference e.g. [ "en", "fr" ])
LanguageRegion_Locale: "en_US@currency=USD"      # Locale and Currency (United States : en_US@currency=USD, Great Britian : en_GB@currency=EUR)
LanguageRegion_MeasurementUnits: "Inches"        # Measure Units (Inches, Centimeters)
LanguageRegion_Force24HourTime: yes              # Force 12/24 hour time
LanguageRegion_MetricUnits: no                   # Set Metric Units
```

```
LaunchServices_LSQuarantine: yes                 # no = disable the “Are you sure you want to open this application?” dialog
```

```
LoginWindow_DisableConsoleAccess: no             # Toggle login for hidden user '>Console'
LoginWindow_GuestEnabled: no                     # Toggle guest login
LoginWindow_LoginWindowText: ""                  # Text message to show in the login screen
LoginWindow_DesktopPicture: ""                   # Change login screen background
LoginWindow_ShutDownDisabled: no                 # Disable shutdown and restart button on login Window
LoginWindow_showInputMenu: no                    # Show input menu in login window
LoginWindow_RetriesUntilHint: 0                  # Show password hints - Retries until hint, 0=disable, any other number to define the number of tries
LoginWindow_Display: "List of users"             # Display Login Window as list or fields: 'List of users' or 'Name and password'
```

```
MissionControl_MruSpaces: no                     # Automatically rearrange Spaces based on most recent use
MissionControl_SwitchOnActivate: yes             # When switching to an application, switch to a Space with open windows for the application
MissionControl_GroupByApp: yes                   # Group windows by application in Mission Control
MissionControl_SpansDisplays: yes                # Displays have separate Spaces
```

```
Safari_DebugMenu: no                             # Debug Menu
Safari_OpensWith: "A new window"                 # General - Safari opens with ("A new window", "A new private window", "All windows from last session")
Safari_NewWindowBehavior: "Favorites"            # General - New windows open with (0:Hompage, 1:Empty page, 2:Same page, 4:Favorites, 5:Tabs for Favorites)
Safari_NewTabBehavior: "Favorites"               # General - New tabs open with (0:Hompage, 1:Empty page, 2:Same page, 4:Favorites)
Safari_HistoryAgeInDaysLimit: "One year"         # General - Retain history items for after (number of days - "One day", "One week", "Two weeks", "One month", "One year")
Safari_TopSitesGridArrangement: "12 sites"       # General - Top Sites shows (0:6 sites, 1:12 sites, 2:24 sites)
Safari_DownloadsClearingPolicy: "After one day"  # General - Remove download list items (0:Manually, 1:After one day, 2:Upon successfull download, 3:When Safari quits)
Safari_AutoOpenSafeDownloads: yes                # General - Open "safe" files after downloading
Safari_TabCreationPolicy: "Automatically"        # Tabs - Open pages in tabs instead of windows (0:Never, 1:Automatically, 2:Always)
Safari_CommandClickMakesTabs: yes                # Tabs - cmd+click opens a link in a new tab
Safari_OpenNewTabsInFront: no                    # Tabs - When a new tab or window opens, make it active
Safari_Command1Through9SwitchesTabs: yes         # Tabs - Use cmd+1 through cmd+9 to switch tabs
Safari_AutoFillFromAddressBook: yes              # Autofill - Using info from my Contact card
Safari_AutoFillPasswords: yes                    # Autofill - Using names and passwords
Safari_AutoFillCreditCardData: yes               # Autofill - Using Credit cards
Safari_AutoFillMiscellaneousForms: yes           # Autofill - Using Other forms
Safari_SearchEngine: "Google"                    # Search - Search engine (Google, Yahoo, Bing, DuckDuckGo)
Safari_IncludeSearchSuggestions: yes             # Search - Include search engine suggestions
Safari_WebsiteSpecificSearchEnabled: yes         # Search - Smart Search Field - Enable Quick Website Search
Safari_PreloadTopHit: yes                        # Search - Smart Search Field - Preload Top Hit in the background
Safari_ShowFavoritesUnderSmartSearchField: yes   # Search - Smart Search Field - Show Favorites
Safari_WarnAboutFraudulentWebsites: yes          # Security - Fraudulent Sites - Warn when visiting a fraudulent website
Safari_JavaScriptEnabled: yes                    # Security - Web Content - Enable Javascript
Safari_BlockPopupWindows: no                     # Security - Web Content - Block pop-up windows
Safari_AllowWebGL: yes                           # Security - Web Content - Allow WebGL
Safari_AllowPlugins: yes                         # Security - Internet plug-ins - Allow Plug-ins
Safari_Cookies: "Always from current website only" # Privacy - Cookies and website data ("Always block", "Always from current website only", "Allow from websites I visit", "Always allow")
Safari_SafariGeolocationPermissionPolicy: "Prompt for each site one time only" # Privacy - Website use of location services (0:Deny without prompting, 1:Prompt for each site once each day, 2:Prompt for each site one time only)
Safari_SendDoNotTrackHTTPHeader: no              # Privacy - Website tracking - Ask websites not to track me
Safari_CanPromptForPushNotifications: yes        # Notification - Allow websites to ask for permission to send push notifications
Safari_InstallExtensionUpdatesAutomatically: yes # Exensions - Automatically update extensions from Safari Extensions Gallery
Safari_ShowFullURLInSmartSearchField: no         # Advanced - Smart Search Field - Show full website address
Safari_WebKitMinimumFontSize: 0                  # Advanced - Accessibility - Never use font sizes smaller than (0 means disabled)
Safari_WebKitTabToLinksPreferenceKey: no         # Advanced - Accessibility - Press Tab to highlight ach item on a webpage
Safari_BookmarksMenuIncludesRendezvous: no       # Advanced - Bonjour - Include Bonjour in the Bookmarks Menu
Safari_StopPuginsToSavePower: yes                # Advanced - Internet plug-ins - Stop plug-ins to saver power
Safari_ShowDeloperMenu: no                       # Advanced - Show Develop menu in menu bar
Safari_ShowFavoritesBar: no                      # View - Show Favorites Bar
Safari_AlwaysShowTabBar: no                      # View - Show Tab Bar
Safari_ShowOverlayStatusBar: no                  # View - Show Status Bar
Safari_ShowSidebarInNewWindows: no               # View - Show Sidebar
Safari_SidebarViewModeIdentifier: "Bookmarks"    # View - Show Sidebar Mode ("Bookmarks","Reading List","Social Links")
Safari_ShowFrequentlyVisitedSites: yes           # Bookmarks - Show Frequently Visited in Favorites
```

```
# when set to `yes` it will prevent the show of the SetupAssistant widow requesting consent for the specific option
# Usually helpful only when configurating a new user account
SetupAssistant_DidSeeActivationLock: no
SetupAssistant_DidSeeAppearanceSetup: no
SetupAssistant_DidSeeApplePaySetup: no
SetupAssistant_DidSeeAvatarSetup: no
SetupAssistant_DidSeeCloudDiagnostics: no
SetupAssistant_DidSeeCloudSetup: no
SetupAssistant_DidSeePrivacy: no
SetupAssistant_DidSeeScreenTime: no
SetupAssistant_DidSeeSiriSetup: no
SetupAssistant_DidSeeSyncSetup: no
SetupAssistant_DidSeeSyncSetup2: no
SetupAssistant_DidSeeTouchIDSetup: no
SetupAssistant_DidSeeTrueTone: no
SetupAssistant_DidSeeTrueTonePrivacy: no
SetupAssistant_DidSeeiCloudLoginForStorageServices: no
SetupAssistant_SkipFirstLoginOptimization: no
```

```
# Spotlight_OrderedItems is an Array
Spotlight_OrderedItems:
  - '{"enabled" = 1;"name" = "APPLICATIONS";}'
  - '{"enabled" = 1;"name" = "SYSTEM_PREFS";}'
  - '{"enabled" = 1;"name" = "DIRECTORIES";}'
  - '{"enabled" = 1;"name" = "PDF";}'
  - '{"enabled" = 1;"name" = "FONTS";}'
  - '{"enabled" = 1;"name" = "DOCUMENTS";}'
  - '{"enabled" = 1;"name" = "MESSAGES";}'
  - '{"enabled" = 1;"name" = "CONTACT";}'
  - '{"enabled" = 1;"name" = "EVENT_TODO";}'
  - '{"enabled" = 1;"name" = "IMAGES";}'
  - '{"enabled" = 1;"name" = "BOOKMARKS";}'
  - '{"enabled" = 1;"name" = "MUSIC";}'
  - '{"enabled" = 1;"name" = "MOVIES";}'
  - '{"enabled" = 1;"name" = "PRESENTATIONS";}'
  - '{"enabled" = 1;"name" = "SPREADSHEETS";}'
  - '{"enabled" = 1;"name" = "SOURCE";}'
  - '{"enabled" = 1;"name" = "MENU_DEFINITION";}'
  - '{"enabled" = 1;"name" = "MENU_OTHER";}'
  - '{"enabled" = 1;"name" = "MENU_CONVERSION";}'
  - '{"enabled" = 1;"name" = "MENU_EXPRESSION";}'
  - '{"enabled" = 1;"name" = "MENU_WEBSEARCH";}'
  - '{"enabled" = 1;"name" = "MENU_SPOTLIGHT_SUGGESTIONS";}'
```

```
Trackpad_ClickHapticFeedback: "Medium"                    # Set Haptic Feedback strength 0 - "Light", 1 - "Medium", 2 - "Firm"
Trackpad_Clicking: "Enabled"                              # Tap to Click
Trackpad_Dragging: "Enabled"                              # Dragging
Trackpad_DragLock: "Disabled"                             # DragLock
Trackpad_ForceClickAndHapticFeedback: "Disabled"          # Force Click and haptic feedback
Trackpad_ScrollDirectionNatural: "Enabled"                # Enable Natural Scroll Direction (it's a macOS default)
Trackpad_SilentClicking: "Disabled"                       # Silent clicking
Trackpad_TrackingSpeed: "Medium"                          # Modulate the tracking speed "Very Slow", "Slow", "Medium", "Fast", "Really Fast"
Trackpad_TrackpadCornerSecondaryClick: "Enabled"          # 0 - Disabled, 2 - Enabled
Trackpad_TrackpadFiveFingerPinchGesture: "Enabled"        # 0 - Disabled, 2 - Enabled
Trackpad_TrackpadFourFingerHorizSwipeGesture: "Enabled"   # 0 - Disabled, 2 - Enabled
Trackpad_TrackpadFourFingerPinchGesture: "Enabled"        # 0 - Disabled, 2 - Enabled
Trackpad_TrackpadFourFingerVertSwipeGesture: "Enabled"    # 0 - Disabled, 2 - Enabled
Trackpad_TrackpadHandResting: "Enabled"                   # 0 - Disabled, 1 - Enabled
Trackpad_TrackpadHorizScroll: "Enabled"                   # 0 - Disabled, 1 - Enabled
Trackpad_TrackpadMomentumScroll: "Enabled"                # 0 - Disabled, 1 - Enabled
Trackpad_TrackpadPinch: "Enabled"                         # 0 - Disabled, 1 - Enabled
Trackpad_TrackpadRightClick: "Enabled"                    # 0 - Disabled, 1 - Enabled
Trackpad_TrackpadRotate: "Enabled"                        # 0 - Disabled, 1 - Enabled
Trackpad_TrackpadScroll: "Enabled"                        # 0 - Disabled, 1 - Enabled
Trackpad_TrackpadThreeFingerDrag: "Disabled"              # 0 - Disabled, 1 - Enabled
Trackpad_TrackpadThreeFingerHorizSwipeGesture: "Disabled" # 0 - Disabled, 1 - Enabled
Trackpad_TrackpadThreeFingerTapGesture: "Disabled"        # 0 - Disabled, 1 - Enabled
Trackpad_TrackpadThreeFingerVertSwipeGesture: "Three and Four Fingers Mission Control/App Exposé" # 0 - Disabled, 1 - Four Fingers Mission Control/App Exposé, # 2 - Three and Four Fingers Mission Control/App Exposé
Trackpad_TrackpadTwoFingerDoubleTapGesture: "Disabled"    # 0 - Disabled, 1 - Enabled
Trackpad_TrackpadTwoFingerFromRightEdgeSwipeGestapure: "Notification Center" #  0 - Disabled, 3 - Notification Center
Trackpad_USBMouseStopsTrackpad: "Disabled"                # 0 - Disabled, 1 - Enabled
```

## Dependencies

## Example Playbook

```
    - hosts: servers
      vars:
        Configure_Bluetooth: yes
        Bluetooth_ShowInMenuBar: no
        target_user_id: 'testuser_name'

      roles:
         - { role: lafarer.osx-defaults }
```

## Known Issues
* On MacOS Catalina 10.15.x Desktop Image assignation doesn't work, apparently it is changed the way the `/Library/Application Support/Dock/desktoppicture.db` is manipulated

## License

BSD

## Author Information
