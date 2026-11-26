<div align="center">

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

<h3>✨ Modern, Modular & Fully Animated UI Library for Roblox (Luau) ✨</h3>

<p>
  <img src="https://img.shields.io/badge/Version-v3.7-7355FF?style=for-the-badge&logo=roblox&logoColor=white" alt="Version v3.7" />
  <img src="https://img.shields.io/badge/Language-Luau-00A2FF?style=for-the-badge&logo=lua&logoColor=white" alt="Language Luau" />
  <img src="https://img.shields.io/badge/Author-gthsc51-16161C?style=for-the-badge&logo=github&logoColor=white" alt="Author gthsc51" />
  <img src="https://img.shields.io/badge/License-Open_Source-41C378?style=for-the-badge" alt="Open Source" />
</p>

<p>
  <a href="#-quick-start">Quick Start</a> •
  <a href="#-core-features">Features</a> •
  <a href="#-window-configuration">Window Setup</a> •
  <a href="#-components-api">Components API</a> •
  <a href="#-utilities--themes">Utilities</a>
</p>

<img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=12,20,24&height=2&section=header" width="100%" />

</div>

## 🌟 Overview

**TryxzLib** is a sleek, high-performance User Interface framework built from the ground up in **Luau** for Roblox. Engineered with a decoupled, modular architecture to avoid Luau register/upvalue limits, it delivers silky-smooth `TweenService` animations, rounded aesthetics, a multi-profile save system, and comprehensive mobile & desktop ergonomics.

---

## 🚀 Core Features

| Feature | Description |
| :--- | :--- |
| 🎨 **Silky `TweenService` Motion** | Every window transition, tab indicator, slider drag, dropdown expansion, and modal dialog uses calibrated easing curves (`Quad`, `Quart`, `Back`, `Quint`). |
| 🤍 **Bottom White Drag Handle** | Features a classic top bar drag handle **plus** a translucent white animated bottom drag bar locked directly beneath the window for effortless mobile & desktop dragging. |
| 🌫️ **Camera Glass Blur** | Integrated `BlurEffect` in `Lighting` that smoothly fades in when the UI is open and automatically clears when minimized (`-`), collapsed (`UI`), hidden, or unloaded. |
| 💊 **Floating `"UI"` Pill Mode** | Collapse the entire interface into a draggable, screen-clamped floating `"UI"` pill button and restore it with a single tap. |
| 🔐 **Key Verification Gate** | Built-in access gate featuring dedicated `Note:` & `Info:` cards (with automatic empty-state fallbacks), a glowing crimson `"X"` close button, `"Copy Key Link"`, and `SaveKey` persistence. |
| 💾 **Multi-Profile Save System** | Automatically saves and restores component states, keybinds, accent colors, UI scale, blur state, and audio settings across named JSON profiles. |
| ⚙️ **Interactive Gear (`⚙`) Panel** | Includes a **Function Keybinds Dropdown** (auto-lists Toggles, Sliders & Buttons), **Diamond UI Scale Slider** (`0.75x–1.35x`), **Live Accent Swatches**, **Sound Packs**, **Haptics**, and **Profile Manager**. |
| 📐 **Adaptive Long-Tab Sidebar** | Automatically expands sidebar width and wraps text cleanly when long tab titles are used. |

---

## ⚡ Quick Start

Load **TryxzLib** directly into your script using `HttpGet`:

```lua
local TryxzLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/gthsc51/TryxzLib-/refs/heads/main/Library/Tryxz"))()
```

---

## 🪟 Window Configuration

Initialize your main interface window with full customization options:

```lua
local Window = TryxzLib:CreateWindow({
    Title = "TryxzHub",
    Subtitle = "v3.7 | Interface Showcase",
    Icon = "rbxassetid://10734950309", -- Accepts rbxassetid://, numeric IDs, or text/emoji
    Profile = true,                      -- Shows player headshot & @username in sidebar
    Stats = true,                        -- Shows live FPS & Ping pill in top bar
    SearchBar = true,                    -- Live search bar to filter elements across tabs
    Haptics = true,                      -- Tactile controller/device vibration feedback
    Blur = {
        Enabled = true,                  -- Camera blur while window is active
        Size = 14
    },
    SaveConfig = {
        Enabled = true,
        SaveKey = true,                  -- Automatically remembers verified access key
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
        Enabled = false,                 -- Set to true to enable the key verification modal
        Title = "Access Verification",
        Icon = "rbxassetid://10723407389",
        Note = "Enter your access key below to continue.",
        Info = {
            Title = "Information",
            Content = "Keys can be obtained from our official link."
        },
        Keys = {"tryxz123"},             -- Supports string, table of strings, or function(key)
        ButtonText = "Verify & Enter",
        GetKeyLink = "https://github.com/gthsc51/TryxzLib-"
    }
})
```

---

## 📑 Tabs & Horizontal Sub-Tabs

Organize your controls cleanly using sidebar tabs and horizontal sub-tabs:

```lua
-- Create a main sidebar tab (supports short or long names; icon is optional)
local MainTab = Window:CreateTab("Main Tab", "rbxassetid://10747373176")

-- Optional: Split a tab into horizontal sub-tabs
local GeneralSub = MainTab:AddSubTab("General")
local AdvancedSub = MainTab:AddSubTab("Advanced")
```

> 💡 **Tip:** Both `MainTab` and `GeneralSub` expose the exact same element creation API documented below.

---

## 🧩 Components API

<details open>
<summary><b>📌 Sections, Dividers, Labels & Paragraphs</b></summary>

```lua
MainTab:AddSection("General Controls")

local StatusLabel = MainTab:AddLabel("Status: Idle")
StatusLabel:Set("Status: Active") -- Update dynamically

MainTab:AddParagraph({
    Title = "Welcome to TryxzLib",
    Content = "Configure your preferences using the interactive controls below."
})

MainTab:AddDivider()
```
</details>

<details open>
<summary><b>📊 Progress Bar</b></summary>

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
</details>

<details open>
<summary><b>🔘 Button (With Cooldown & Gear Keybind Support)</b></summary>

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
</details>

<details open>
<summary><b>🔀 Toggle</b></summary>

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

FeatureToggle:Set(true) -- Programmatically update state
```
</details>

<details open>
<summary><b>🎚️ Slider</b></summary>

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

SpeedSlider:Set(100) -- Programmatically update value
```
</details>

<details open>
<summary><b>⌨️ Text Input & Keybind Picker</b></summary>

```lua
-- Text / Numeric Input
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

-- Standalone Keybind Picker
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
</details>

<details open>
<summary><b>🎨 HSV Color Picker</b></summary>

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
</details>

<details open>
<summary><b>📋 Dropdown & Multi-Dropdown (With Header & Option Icons)</b></summary>

```lua
-- Single Selection Dropdown
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

-- Multiple Selection Dropdown
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
</details>

---

## 🛠️ Utilities & Themes

```lua
-- 🔔 Send an animated toast notification
TryxzLib:Notify({
    Title = "Action Complete",
    Text = "Your settings have been applied.",
    Duration = 4,
    Sound = "Notify" -- Optional sound override
})

-- 💬 Open a modal confirmation dialog
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

-- ⌨️ Register a custom function inside the Gear (⚙) Keybinds Dropdown
Window:RegisterKeybind({
    Id = "CustomFnBind",
    Name = "Custom Action",
    Kind = "Custom",
    DefaultKey = Enum.KeyCode.K,
    Trigger = function()
        print("Triggered from Gear Keybinds!")
    end
})

-- 🎨 Dynamic Theme & Audio Helpers
TryxzLib:SetAccent(Color3.fromRGB(56, 152, 255))
TryxzLib:SetSoundPreset("Mechanical")
TryxzLib:RegisterSound("Beep", "rbxassetid://6895079853")
TryxzLib:PlaySound("Beep")
```

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=12,20,24&height=2&section=footer" width="100%" />

**Maintained with ❤️ by [gthsc51](https://github.com/gthsc51)**  
*Credit is appreciated when using or modifying **TryxzLib** in your projects.*

</div> 
