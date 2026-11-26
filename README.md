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

# TryxzLib (v3.7)

A modern, modular, and fully animated User Interface library written in Luau for Roblox. Designed with smooth `TweenService` transitions, rounded aesthetics, multi-profile configuration saving, and a clean object-oriented API.

**Created by [gthsc51](https://github.com/gthsc51)**

---

## Features

- **Smooth Animations & Bottom Drag Handle:** Every interaction uses `TweenService` curves (`Quad`, `Quart`, `Back`, `Quint`). Includes a top bar drag handle plus an animated, translucent white bottom drag bar locked directly beneath the window for effortless mobile and desktop repositioning.
- **Modular & Lightweight:** Built with a decoupled component architecture to prevent Luau register/upvalue limits and keep frame rates stable.
- **Floating Collapse & Minimize Modes:** Collapse the main window into a draggable, screen-clamped floating `"UI"` pill button or minimize it cleanly to its top bar (`-`).
- **Camera Glass Blur:** Animated `BlurEffect` in `Lighting` that automatically enables when the interface is open and clears when minimized (`-`), collapsed (`UI`), hidden, or unloaded.
- **Complete Key Verification Gate:**
  - Dedicated `Note:` and `Info:` cards with automatic fallback messages (`"There is no note at this time."` / `"There is no information at this time."`).
  - Glowing crimson `"X"` close button, clipboard `"Copy Key Link"` button, and automatic key persistence (`SaveKey`) inside `SaveConfig`.
- **Adaptive Sidebar & Long Tab Names:** Automatically expands the sidebar width and wraps text cleanly when long tab titles are used.
- **Multi-Profile Save System:** Automatically saves and restores toggles, sliders, inputs, keybinds, function binds, color pickers, dropdowns, accent themes, UI scale, blur state, and audio preferences across named JSON profiles.
- **Live Customization (`⚙` Settings):**
  - **Function Keybinds Dropdown:** Automatically lists bindable Toggles, Sliders (`+KeyStep`), and Buttons so users can assign or clear hotkeys directly from `⚙`.
  - **UI Viewport Scale:** Segmented stepper slider (`-` / `+` buttons + rotating diamond knob) from `0.75x` to `1.35x`.
  - **Accent Theme Color:** Live theme switcher across the entire UI.
  - **Camera Glass Blur, Haptic Feedback & Sound Packs:** Toggleable settings with built-in and custom audio presets.
  - **Config Profile Manager:** Save, load, and delete multiple named profiles.
- **Rich Component Suite:** Tabs, Horizontal Sub-Tabs, Sections, Dividers, Labels, Paragraphs, Progress Bars, Buttons (with optional Cooldowns), Toggles, Sliders, Text Inputs, Keybind Pickers, HSV Color Pickers, Dropdowns & Multi-Dropdowns (with header & per-option icons), Tooltips, Notifications, and Confirmation Dialogs.

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
    Subtitle = "v3.7 | Interface Showcase",
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
-- Create a main sidebar tab (supports short or long titles; icon is optional)
local MainTab = Window:CreateTab("Main Tab", "rbxassetid://10747373176")

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
    Flag = "RunActionBtn",               -- Optional identifier for Gear Keybinds
    Keybind = Enum.KeyCode.R,            -- Optional default key in Gear Keybinds Dropdown
    Bindable = true,                     -- Registers in Gear (⚙) Keybinds Dropdown (default: true)
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
    Flag = "FeatureToggleFlag",          -- Unique key for SaveConfig & Gear Keybinds
    Keybind = Enum.KeyCode.V,            -- Optional default key in Gear Keybinds Dropdown
    Bindable = true,                     -- Registers in Gear (⚙) Keybinds Dropdown (default: true)
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
    KeyStep = 25,                        -- Step increment when triggered via Gear Keybinds
    Keybind = Enum.KeyCode.B,            -- Optional default key in Gear Keybinds Dropdown
    Bindable = true,                     -- Registers in Gear (⚙) Keybinds Dropdown (default: true)
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
    Default = Enum.KeyCode.G,
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

### Dropdown & Multi-Dropdown (With Icons)

```lua
-- Single Selection
MainTab:AddDropdown({
    Name = "Target Hitbox",
    Icon = "rbxassetid://10723356507", -- Optional header icon
    Flag = "HitboxDropdownFlag",
    Options = {"Head", "HumanoidRootPart", "Torso"},
    OptionIcons = {                      -- Optional per-option icons
        ["Head"] = "rbxassetid://10747373176",
        ["HumanoidRootPart"] = "rbxassetid://10734950309",
        ["Torso"] = "rbxassetid://10709790948"
    },
    Default = "HumanoidRootPart",
    Tooltip = "Choose one option",
    Callback = function(selected)
        print("Selected:", selected)
    end
})

-- Multiple Selection
MainTab:AddMultiDropdown({
    Name = "Active Overlays",
    Icon = "rbxassetid://10734933222", -- Optional header icon
    Flag = "OverlaysMultiFlag",
    Options = {"Boxes", "Names", "Distance", "Tracers"},
    OptionIcons = {                      -- Optional per-option icons
        ["Boxes"] = "rbxassetid://10723356507",
        ["Names"] = "rbxassetid://10747373176",
        ["Distance"] = "rbxassetid://10734950309",
        ["Tracers"] = "rbxassetid://10734933222"
    },
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

-- Register a custom function inside the Gear (⚙) Keybinds Dropdown
Window:RegisterKeybind({
    Id = "CustomFnBind",
    Name = "Custom Action",
    Kind = "Custom",
    DefaultKey = Enum.KeyCode.K,
    Trigger = function()
        print("Triggered from Gear Keybinds!")
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
