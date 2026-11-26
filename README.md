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

# TryxzLib v3.9

### A Modular, Animated & Theme-Driven Luau UI Library for Roblox Executors

[![Version](https://img.shields.io/badge/Version-v3.9-7355FF?style=for-the-badge&logo=lua&logoColor=white)](https://github.com/gthsc51/TryxzLib-)
[![Language](https://img.shields.io/badge/Language-Luau-3898FF?style=for-the-badge)](https://luau-lang.org/)
[![Author](https://img.shields.io/badge/Author-gthsc51-2ECC71?style=for-the-badge&logo=github&logoColor=white)](https://github.com/gthsc51)
[![Platform](https://img.shields.io/badge/Platform-Executor%20Ready-EC5FB9?style=for-the-badge)](https://github.com/gthsc51/TryxzLib-)

---

![Cyberpunk Workspace Banner](https://images.unsplash.com/photo-1550751827-4bd374c3f58b?auto=format&fit=crop&w=1400&q=80)

</div>

> **TryxzLib v3.9** is engineered for smooth performance, visual polish, and clean script organization. It separates structural layout elements (**Sections**, **Dividers**, **Labels**, and **Paragraphs**) from interactive controls, introduces **6 full color themes** plus custom theme support, renders clean icon badges inside **Dropdowns** and **Multi-Dropdowns**, includes a translucent white bottom drag bar, and provides a richly decorated **Settings (`⚙`)** panel with function keybinds, sound packs, diamond viewport scaling, and multi-profile configuration saving.

---

## Color Themes

Every built-in theme updates the entire UI color palette dynamically—including background, sidebar, elements, hover states, dividers, text hierarchy, and accent colors.

| Theme Name | Accent | Background | Sidebar | Element | Vibe |
| :--- | :---: | :---: | :---: | :---: | :--- |
| **Obsidian** | `#7355FF` | `#101014` | `#16161C` | `#1E1E26` | Deep dark with violet glow |
| **Crimson Night** | `#EB445A` | `#140E10` | `#1C1216` | `#26181D` | Charcoal shadow with crimson highlights |
| **Abyss Ocean** | `#3898FF` | `#0D121A` | `#121924` | `#192230` | Midnight navy with ocean blue |
| **Emerald Forest** | `#2ECC71` | `#0D1612` | `#121E18` | `#182820` | Dark woodland with emerald green |
| **Solar Amber** | `#F5B22D` | `#16130E` | `#1E1A13` | `#282319` | Warm graphite with golden amber |
| **Sakura Dusk** | `#EC5FB9` | `#160F18` | `#1E1421` | `#281B2C` | Twilight plum with neon rose |

---

## Features & Architecture

![Modular UI Architecture](https://images.unsplash.com/photo-1518770660439-4636190af475?auto=format&fit=crop&w=1400&q=80)

### Structural Hierarchy Elements
- **Sections (`AddSection`):** Clean section headers featuring a vertical accent pill, optional icon, bold uppercase typography, and a fading divider line on the right.
- **Dividers (`AddDivider`):** Fading gradient horizontal lines with a glowing diamond center node or an optional centered label badge.
- **Labels (`AddLabel`):** Dedicated status cards with an accent stripe on the left and a status icon for live readouts (`Label:Set(...)`).
- **Paragraphs (`AddParagraph`):** Structured info cards with a titled header, optional icon, internal separator line, and wrapped body text.

### Window, Navigation & Dragging
- **Long Tab Name Support:** Automatically adapts tab row sizing and sidebar width so long tab titles remain clear and readable.
- **Horizontal Sub-Tabs (`AddSubTab`):** Organizes complex tabs into clean sub-pages with pill-style tab buttons.
- **Live Element Search (`SearchBar`):** Filters matching controls across tabs in real time.
- **Live Stats Pill (`Stats`):** Displays real-time **FPS** and **Ping (`ms`)** in the top bar.
- **Bottom Translucent White Drag Bar & Topbar Drag:** Move the UI smoothly from the topbar or the translucent white bar underneath the window.
- **Minimize (`-`), Floating Collapse (`UI`), Toggle Key & Unload:** Minimize to topbar, collapse into a draggable floating `UI` pill, toggle visibility via keybind (e.g., `RightControl`), or unload cleanly.
- **Camera Glass Blur (`Blur`):** Smoothly blurs the camera while the window is open and clears when minimized, collapsed, or closed.

### Interactive Controls
- **Buttons (`AddButton`):** Supports icons, custom sound IDs/presets, hover animations, and timed `Cooldown` progress overlays.
- **Toggles (`AddToggle`):** Animated switch with `Flag` saving, optional default `Keybind`, tooltips, and programmatic `:Set(state)`.
- **Sliders (`AddSlider`):** Smooth draggable track with live value label, `KeyStep` increments, `Flag` saving, and `:Set(value)`.
- **Text Inputs (`AddInput`):** Supports placeholders, numeric-only mode (`Numeric = true`), `ClearOnFocus`, `Flag` saving, and `:Set(text)`.
- **Keybind Pickers (`AddKeybind`):** Interactive key capture badge with `Flag` persistence.
- **HSV Color Pickers (`AddColorPicker`):** Expandable Saturation/Value box and Hue bar with live color preview and `Flag` saving.
- **Progress Bars (`AddProgressBar`):** Animated progress bar with percentage or custom suffix text (`:Set(val, customText)`).
- **Dropdowns & Multi-Dropdowns (`AddDropdown`, `AddMultiDropdown`):** Smooth expand/collapse animations, clean icon badges (`Icon` and `OptionIcons`), single or multi-selection, and `Flag` persistence.

### Decorated Gear (`⚙`) Settings Panel
- **Function Keybinds Dropdown:** Lists registered bindable functions (`Toggle`, `Slider`, `Button`, etc.) inside the gear menu so users can assign, rebind, or clear keys with instant `UserInputService` execution and profile saving.
- **UI Viewport Scale:** Segmented slider with a rotating diamond knob and `0.75x`–`1.35x` scaling.
- **UI Theme Palette:** Interactive swatches to switch full themes immediately, plus **Camera Glass Blur**, **Haptic Feedback**, and **UI Sound Effects** toggles.
- **Sound Packs & Custom Audio:** Built-in presets (`Soft Pop`, `Mechanical`, `Bubble`, `Cyber`), custom sound packs (`Packs`), and named custom sounds (`Custom`).
- **Multi-Profile Config System (`SaveConfig`):** Save, load, and delete named JSON profiles (`Save`, `Load`, `Delete`), plus optional persistent key storage (`SaveKey`).

### Key System (`KeySystem`)
- Draggable verification card with a glowing red `X` close button.
- Dedicated **`Note:`** section (defaults to `"There is no note at this time."` when empty/omitted).
- Dedicated **`Info:`** paragraph section (defaults to `"There is no information at this time."` when omitted).
- **`Copy Key Link`** button (`GetKeyLink`) with clipboard support and notification feedback.

---

## Quick Start

```lua
local TryxzLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/gthsc51/TryxzLib-/refs/heads/main/Library/Tryxz?t=" .. tostring(os.time())))()

local Window = TryxzLib:CreateWindow({
    Title = "TryxzHub",
    Subtitle = "v3.9 | Full Showcase",
    Icon = "rbxassetid://10734950309",
    Theme = "Obsidian",
    Profile = true,
    Stats = true,
    SearchBar = true,
    Haptics = true,
    Blur = {
        Enabled = true,
        Size = 14
    },
    SaveConfig = {
        Enabled = true,
        SaveKey = false,
        DefaultProfile = "default",
        Folder = "TryxzLibConfigs",
        FileName = "TryxzHub_Config"
    },
    Sounds = {
        Enabled = true,
        Preset = "Soft Pop",
        Volume = 0.45,
        Custom = {
            ["AlertSound"] = "rbxassetid://4590657391"
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
        Enabled = false,
        Title = "TryxzHub Key System",
        Icon = "rbxassetid://10723407389",
        Note = "Enter your access key below or copy the link.",
        Info = {
            Title = "Access Info",
            Content = "Keys are verified automatically when SaveKey is enabled."
        },
        Keys = {"tryxz123"},
        ButtonText = "Verify & Enter",
        GetKeyLink = "https://github.com/gthsc51/TryxzLib-"
    }
})
```

---

## API Reference

<details>
<summary><strong>Tabs, Sub-Tabs & Structural Elements</strong></summary>

```lua
local MainTab = Window:CreateTab("Main Controls", "rbxassetid://10747373176")
local SubTab = MainTab:AddSubTab("General")

SubTab:AddSection("Player Status", "rbxassetid://10734950309")

local StatusLabel = SubTab:AddLabel("Status: Idle", "ℹ")
StatusLabel:Set("Status: Active")

SubTab:AddParagraph({
    Title = "Overview",
    Icon = "rbxassetid://10723407389",
    Content = "Configure movement, visuals, and keybinds from this tab."
})

SubTab:AddDivider("Actions")
```

</details>

<details>
<summary><strong>Buttons, Toggles, Sliders, Inputs, Keybinds, ColorPickers & ProgressBars</strong></summary>

```lua
SubTab:AddProgressBar({
    Name = "Stamina",
    Max = 100,
    Default = 50,
    Tooltip = "Live progress bar"
})

SubTab:AddButton({
    Name = "Run Action",
    Icon = "rbxassetid://10734933222",
    Cooldown = 2,
    Keybind = Enum.KeyCode.R,
    Tooltip = "Executes action with a 2s cooldown",
    Callback = function()
        TryxzLib:Notify({
            Title = "Executed",
            Text = "Action triggered successfully.",
            Duration = 3
        })
    end
})

SubTab:AddToggle({
    Name = "Enable Speed",
    Icon = "rbxassetid://10734950309",
    Flag = "SpeedToggle",
    Keybind = Enum.KeyCode.V,
    Default = false,
    Callback = function(state)
        print("Speed enabled:", state)
    end
})

SubTab:AddSlider({
    Name = "WalkSpeed",
    Flag = "WalkSpeedSlider",
    Min = 16,
    Max = 250,
    Default = 16,
    KeyStep = 20,
    Keybind = Enum.KeyCode.B,
    Callback = function(value)
        print("WalkSpeed:", value)
    end
})

SubTab:AddInput({
    Name = "Player Filter",
    Flag = "FilterInput",
    Placeholder = "Enter name...",
    Numeric = false,
    ClearOnFocus = false,
    Callback = function(text, enterPressed)
        print("Input:", text, enterPressed)
    end
})

SubTab:AddKeybind({
    Name = "Quick Keybind",
    Flag = "QuickKeybind",
    Default = Enum.KeyCode.G,
    Callback = function(key)
        print("Pressed key:", key.Name)
    end
})

SubTab:AddColorPicker({
    Name = "Accent Color",
    Flag = "AccentColorPicker",
    Default = Color3.fromRGB(115, 85, 255),
    Callback = function(color)
        TryxzLib:SetAccent(color)
    end
})
```

</details>

<details>
<summary><strong>Dropdowns, Multi-Dropdowns, Dialogs & Global Helpers</strong></summary>

```lua
SubTab:AddDropdown({
    Name = "Select Theme",
    Icon = "rbxassetid://10734950309",
    Flag = "ThemeSelector",
    Options = { "Obsidian", "Crimson Night", "Abyss Ocean", "Emerald Forest", "Solar Amber", "Sakura Dusk" },
    OptionIcons = {
        ["Obsidian"] = "💜",
        ["Crimson Night"] = "❤️",
        ["Abyss Ocean"] = "💙",
        ["Emerald Forest"] = "💚",
        ["Solar Amber"] = "💛",
        ["Sakura Dusk"] = "🩷"
    },
    Default = "Obsidian",
    Callback = function(selectedTheme)
        TryxzLib:SetTheme(selectedTheme)
    end
})

SubTab:AddMultiDropdown({
    Name = "Active Features",
    Icon = "rbxassetid://10734933222",
    Flag = "ActiveFeaturesMulti",
    Options = { "ESP", "Tracers", "Radar" },
    Default = { "ESP" },
    Callback = function(selectedList)
        print("Selected:", table.concat(selectedList, ", "))
    end
})

TryxzLib:Dialog({
    Title = "Confirm Reset",
    Icon = "rbxassetid://10734933222",
    Content = "Reset current settings to default?",
    ConfirmText = "Confirm",
    CancelText = "Cancel",
    OnConfirm = function()
        print("Confirmed")
    end
})

TryxzLib:SetTheme("Abyss Ocean")
TryxzLib:SetSoundPreset("Mechanical")
TryxzLib:RegisterSound("CustomPing", "rbxassetid://6895079853")
TryxzLib:PlaySound("CustomPing")
```

</details>

---

## Credits

Created and maintained by **[gthsc51](https://github.com/gthsc51)**. 
