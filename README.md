```text
        ,----,                                                   ,--,                       
      ,/   .`|                                                ,---.'|                       
    ,`   .'  :                                                |   | :                       
  ;    ;     /                                                :   : |     ,--,     ,---,    
.'___,/    ,' __  ,-.                           ,----,        |   ' :   ,--.'|   ,---.'|    
|    :     |,' ,'/ /|         ,--,  ,--,      .'   .`|        ;   ; '   |  |,    |   | :    
;    |.';  ;'  | |' |   .--,  |'. \/ .`|   .'   .'  .'        '   | |__ `--'_    :   : :    
`----'  |  ||  |   ,' /_ ./|  '  \/  / ; ,---, '   ./         |   | :.'|,' ,'|   :     |,-. 
    '   :  ;'  :  /, ' , ' :   \  \.' /  ;   | .'  /          '   :    ;'  | |   |   : '  | 
    |   |  '|  | '/___/ \: |    \  ;  ;  `---' /  ;--,        |   |  ./ |  | :   |   |  / : 
    '   :  |;  : | .  \  ' |   / \  \  \   /  /  / .`|        ;   : ;   '  : |__ '   : |: | 
    ;   |.' |  , ;  \  ;   : ./__;   ;  \./__;     .'         |   ,/    |  | '.'||   | '/ : 
    '---'    ---'    \  \  ; |   :/\  \ ;;   |  .'            '---'     ;  :    ;|   :    | 
                      :  \  \`---'  `--` `---'                          |  ,   / /    \  /  
                       \  ' ;                                            ---`-'  `-'----'   
                        `--`                                                                
```

# TryxzLib

A modern, modular, and fully animated User Interface library written in Luau for Roblox. Designed with smooth `TweenService` transitions, rounded aesthetics, multi-profile configuration saving, and a clean object-oriented API.

**Created by [gthsc51](https://github.com/gthsc51)**

---

## Features

- **Smooth Animations:** Every interaction—window transitions, tab switching, dropdown expansion, slider dragging, notifications, and modal dialogs—uses `TweenService` curves (`Quad`, `Quart`, `Back`, `Quint`).
- **Modular & Lightweight:** Built with a decoupled component architecture to prevent Luau register/upvalue limits and keep frame rates stable.
- **Floating Collapse Mode:** Collapse the main window into a draggable, screen-clamped floating `"UI"` pill button or minimize it cleanly to its top bar.
- **Camera Glass Blur:** Optional animated `BlurEffect` that automatically enables when the interface is open and clears when minimized or collapsed.
- **Key Verification Gate:** Optional access key modal with a custom note, info card, clipboard link button, glowing close button, and automatic key persistence (`SaveKey`).
- **Multi-Profile Save System:** Automatically saves and restores toggles, sliders, inputs, keybinds, color pickers, dropdowns, accent themes, UI scale, and audio preferences across named JSON profiles.
- **Live Customization (`⚙` Settings):**
  - Real-time **Accent Theme Color** switcher.
  - Segmented diamond **UI Viewport Scale** slider (`0.75x` – `1.35x`).
  - Built-in & custom **Sound Packs** + **Haptic Feedback** controls.
  - Built-in **Config Profile Manager** (Save, Load, Delete).
- **Rich Component Suite:** Tabs, Horizontal Sub-Tabs, Sections, Dividers, Labels, Paragraphs, Progress Bars, Buttons (with optional Cooldowns), Toggles, Sliders, Text Inputs, Keybind Pickers, HSV Color Pickers, Dropdowns, Multi-Dropdowns, Tooltips, Notifications, and Confirmation Dialogs.

---

## Quick Start

Load the library directly from your repository:

```lua
local TryxzLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/gthsc51/TryxzLib-/refs/heads/main/Library/Tryxz"))()
```

---

## Creating a Window

```lua
local Window = TryxzLib:CreateWindow({
    Title = "TryxzHub",
    Subtitle = "v3.2 | Interface Showcase",
    Icon = "rbxassetid://10734950309", -- Supports rbxassetid://, numeric IDs, or text
    Profile = true,                      -- Displays user avatar & display name in sidebar
    Stats = true,                        -- Displays live FPS & Ping pill in top bar
    SearchBar = true,                    -- Enables live element search bar
    Haptics = true,                      -- Enables tactile vibration feedback
    Blur = {
        Enabled = true,                  -- Smooth background blur while open
        Size = 14
    },
    SaveConfig = {
        Enabled = true,
        SaveKey = true,                  -- Remembers verified key automatically
        DefaultProfile = "default",
        Folder = "TryxzLibConfigs",
        FileName = "TryxzHub_Config"
    },
    Sounds = {
        Enabled = true,
        Preset = "Soft Pop",             -- Built-in: "Soft Pop", "Mechanical", "Bubble", "Cyber"
        Volume = 0.5,
        Custom = {
            ["CustomAlert"] = "rbxassetid://9119713951"
        },
        Packs = {
            ["Retro Arcade"] = {
                Click = "rbxassetid://12221967",
                Hover = "rbxassetid://12221976",
                Toggle = "rbxassetid://12221967",
                Notify = "rbxassetid://12222030"
            }
        }
    },
    ToggleKey = Enum.KeyCode.RightControl,
    KeySystem = {
        Enabled = false,                 -- Set to true to enable the access key gate
        Title = "Access Verification",
        Icon = "rbxassetid://10723407389",
        Note = "Enter your access key below to continue.",
        Info = {
            Title = "Information",
            Content = "Keys can be obtained from our official link."
        },
        Keys = {"tryxz123"},             -- Accepts a string, table of strings, or validator function(key)
        ButtonText = "Verify & Enter",
        GetKeyLink = "https://github.com/gthsc51/TryxzLib-"
    }
})
```

---

## Tabs & Sub-Tabs

```lua
-- Create a main sidebar tab (icon is optional)
local MainTab = Window:CreateTab("Main", "rbxassetid://10747373176")

-- Optional: Divide a tab into horizontal sub-tabs
local GeneralSub = MainTab:AddSubTab("General")
local AdvancedSub = MainTab:AddSubTab("Advanced")
```

> **Note:** Both `MainTab` and `GeneralSub` share the exact same element API methods listed below.

---

## Components API

### Sections, Dividers, Labels & Paragraphs

```lua
MainTab:AddSection("General Controls")

local StatusLabel = MainTab:AddLabel("Status: Idle")
-- Update dynamically:
StatusLabel:Set("Status: Active")

MainTab:AddParagraph({
    Title = "Welcome",
    Content = "Configure your preferences using the controls below."
})

MainTab:AddDivider()
```

### Progress Bar

```lua
local Progress = MainTab:AddProgressBar({
    Name = "Task Completion",
    Max = 100,
    Default = 25,
    Tooltip = "Displays real-time progress"
})

-- Update value and optional custom suffix text:
Progress:Set(75, "75% Done")
```

### Button

```lua
MainTab:AddButton({
    Name = "Run Action",
    Icon = "rbxassetid://10734933222", -- Optional
    Sound = "CustomAlert",               -- Optional custom sound name or asset ID
    Cooldown = 2,                        -- Optional cooldown in seconds
    Tooltip = "Triggers an action with a 2s cooldown",
    Callback = function()
        print("Button clicked!")
    end
})
```

### Toggle

```lua
local FeatureToggle = MainTab:AddToggle({
    Name = "Enable Feature",
    Icon = "rbxassetid://10734950309", -- Optional
    Flag = "FeatureToggleFlag",          -- Unique key for SaveConfig
    Default = false,
    Tooltip = "Toggles the feature on or off",
    Callback = function(state)
        print("Toggle state:", state)
    end
})

-- Programmatically update state:
FeatureToggle:Set(true)
```

### Slider

```lua
local SpeedSlider = MainTab:AddSlider({
    Name = "WalkSpeed",
    Flag = "WalkSpeedFlag",
    Min = 16,
    Max = 250,
    Default = 16,
    Tooltip = "Adjust movement speed",
    Callback = function(value)
        print("Slider value:", value)
    end
})

-- Programmatically update value:
SpeedSlider:Set(100)
```

### Text Input

```lua
local NameInput = MainTab:AddInput({
    Name = "Target Name",
    Flag = "TargetNameFlag",
    Default = "",
    Placeholder = "Enter text...",
    Numeric = false,                     -- Set true to restrict input to numbers
    ClearOnFocus = false,
    Tooltip = "Type a value and press Enter",
    Callback = function(text, enterPressed)
        print("Input text:", text)
    end
})
```

### Keybind Picker

```lua
local Bind = MainTab:AddKeybind({
    Name = "Quick Toggle Key",
    Flag = "QuickBindFlag",
    Default = Enum.KeyCode.V,
    Tooltip = "Click badge to rebind key",
    Callback = function(key)
        print("Key pressed:", key.Name)
    end
})
```

### Color Picker (HSV)

```lua
local Picker = MainTab:AddColorPicker({
    Name = "Highlight Color",
    Flag = "HighlightColorFlag",
    Default = Color3.fromRGB(115, 85, 255),
    Tooltip = "Click to expand HSV color selector",
    Callback = function(color)
        print("Selected Color3:", color)
    end
})
```

### Dropdown & Multi-Dropdown

```lua
-- Single Selection
MainTab:AddDropdown({
    Name = "Select Mode",
    Flag = "ModeDropdownFlag",
    Options = {"Option A", "Option B", "Option C"},
    Default = "Option A",
    Tooltip = "Choose one option",
    Callback = function(selected)
        print("Selected:", selected)
    end
})

-- Multiple Selection
MainTab:AddMultiDropdown({
    Name = "Select Overlays",
    Flag = "OverlaysMultiFlag",
    Options = {"Boxes", "Names", "Distance", "Tracers"},
    Default = {"Names", "Distance"},
    Tooltip = "Select multiple options",
    Callback = function(selectedList)
        print("Active options:", table.concat(selectedList, ", "))
    end
})
```

---

## Notifications, Dialogs & Utilities

```lua
-- Send an animated notification
TryxzLib:Notify({
    Title = "Action Complete",
    Text = "Your settings have been applied.",
    Duration = 4,
    Sound = "Notify" -- Optional sound override
})

-- Open a modal confirmation dialog
TryxzLib:Dialog({
    Title = "Confirm Reset",
    Icon = "rbxassetid://10734933222",
    Content = "Are you sure you want to reset your current values?",
    ConfirmText = "Confirm",
    CancelText = "Cancel",
    OnConfirm = function()
        print("Confirmed!")
    end,
    OnCancel = function()
        print("Cancelled!")
    end
})

-- Dynamic Theme & Audio Helpers
TryxzLib:SetAccent(Color3.fromRGB(56, 152, 255))
TryxzLib:SetSoundPreset("Mechanical")
TryxzLib:RegisterSound("Beep", "rbxassetid://6895079853")
TryxzLib:PlaySound("Beep")
```

---

## License

This project is open-source and maintained by **gthsc51**. Credit is appreciated when using or modifying **TryxzLib** in your projects.
