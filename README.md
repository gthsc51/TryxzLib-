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

# TryxzLib v4.5 | by gthsc51 

### Futuristic Sci-Fi HUD & Modular Luau UI Library for Roblox Executors

[![Version](https://img.shields.io/badge/Version-v4.5-7355FF?style=for-the-badge&logo=lua&logoColor=white)](https://github.com/gthsc51/TryxzLib-)
[![Language](https://img.shields.io/badge/Language-Luau-3898FF?style=for-the-badge)](https://luau-lang.org/)
[![Author](https://img.shields.io/badge/Architect-gthsc51-FFD741?style=for-the-badge&logo=github&logoColor=black)](https://github.com/gthsc51)
[![Status](https://img.shields.io/badge/HUD-Sci--Fi%20Core-2ECC71?style=for-the-badge)](https://github.com/gthsc51/TryxzLib-)

---

![Futuristic Sci-Fi HUD Banner](https://images.unsplash.com/photo-1550751827-4bd374c3f58b?auto=format&fit=crop&w=1400&q=80)

</div>

> **TryxzLib v4.5** is a high-visual-impact, futuristic Sci-Fi HUD UI library engineered in Luau for Roblox executors. It features **dual-gradient rotating neon borders**, an **ambient particle constellation canvas**, **holographic scanlines with vertical laser sweeps**, **cyber-decode text animations**, **click ripple waves**, a **sound & FPS reactive pulse aura**, an ordered **4-section Gear (`⚙`) Settings Menu** with a **glowing gold Architect Credits card**, and a rich suite of interactive and structural components.

---

## Dual-Gradient Color Themes

Every built-in theme dynamically updates the entire HUD palette—including dual-tone gradients (`Accent` $\rightarrow$ `AccentSecondary`), borders, particles, scanlines, cards, and typography.

| Theme Name | Primary Accent | Secondary Glow | Background | Sidebar | Aesthetic |
| :--- | :---: | :---: | :---: | :---: | :--- |
| **Obsidian** | `#7355FF` | `#B96EFF` | `#0D0D12` | `#13131A` | Deep void dark with electric violet |
| **Crimson Night** | `#EE4158` | `#FF825A` | `#120C0E` | `#1A1014` | Charcoal shadow with crimson plasma |
| **Abyss Ocean** | `#3498FF` | `#32E6EE` | `#0B1018` | `#101722` | Midnight trench with cyan-blue neon |
| **Emerald Forest** | `#2CD073` | `#73F2A0` | `#0B1410` | `#101C16` | Dark bio-grid with emerald mint |
| **Solar Amber** | `#F8B42A` | `#FF763A` | `#14110C` | `#1C1811` | Warm obsidian with solar gold |
| **Sakura Dusk** | `#F05CBC` | `#A566FF` | `#140D16` | `#1C121F` | Twilight plum with neon magenta |

---

## Visual Engine & Architecture

![Modular Sci-Fi Architecture](https://images.unsplash.com/photo-1518770660439-4636190af475?auto=format&fit=crop&w=1400&q=80)

### Futuristic HUD Effects
* **Particle Constellation Canvas (`ParticleCanvas`):** Subtle floating luminous micro-particles drifting inside the main window and key system modal.
* **Holographic Scanlines & Laser Sweep (`HoloGrid`):** Fine HUD horizontal grid lines paired with a continuous vertical scanning laser beam.
* **Cyber-Decode Text (`ScrambleText`):** Rapid glyph-decoding animation when switching tabs, rendering sections, or launching the window.
* **Click Ripple Waves (`SpawnRipple`):** Expanding translucent ripples originating from the exact tap/click coordinates on buttons and tabs.
* **Reactive Pulse Aura (`PulseAura`):** Outer ambient glow behind the window that breathes with live FPS and pulses whenever UI audio cues trigger.
* **Diagonal Shimmer Sweeps (`AttachShimmer`):** Periodic light beams across the topbar, primary action buttons, and credits card.

### Structural & Interactive Controls
* **Layout Hierarchy:** `AddSection` (with accent pill & gradient trail), `AddDivider` (with glowing diamond node or centered label), `AddLabel` (live status card), and `AddParagraph` (structured info card).
* **Navigation:** Long tab name auto-scaling, glowing tab badges (`Tab:SetBadge("v4.5")`), horizontal sub-tabs (`AddSubTab`), live element `SearchBar`, real-time FPS/Ping pill, floating `UI` collapse pill, minimize `-`, and a translucent white bottom drag bar.
* **Interactive Controls:**
  * `AddButton` (with icons, custom sound IDs, and timed `Cooldown` progress bar) & `AddButtonRow` (2–4 compact buttons in one row)
  * `AddToggle` (with `Flag` saving and bindable `Keybind`)
  * `AddSlider` & `AddRangeSlider` (dual-thumb `Min`/`Max` range selector)
  * `AddInput` (text & `Numeric` modes) & `AddKeybind`
  * `AddColorPicker` (HSV picker + editable `#HEX` input + automatic `Rainbow` mode)
  * `AddProgressBar` (animated bar with percentage or custom text)
  * `AddDropdown`, `AddMultiDropdown`, and `AddPlayerDropdown` (auto-syncing live server players with avatar thumbnails and search filtering)
  * `AddConsole` (embedded terminal with timestamps, color-coded log levels, auto-scroll, and `Clear`)
  * **Control Modifiers:** `Element:SetLocked(true, "Reason")` and dynamic `VisibleIf = function() ... end`.

### Ordered Sci-Fi Gear (`⚙`) Settings Menu
* **Glowing Gold Architect Credits Card:** Dedicated holographic card with animated gold gradient borders, golden particles, and creator badge for **`gthsc51`**.
* **`01 // VISUALS & THEMES`:** Neural Theme Matrix swatches + HUD Viewport Scale (`0.75x`–`1.35x`) with `-`/`+` buttons and diamond knob.
* **`02 // KEYBINDS MATRIX`:** Expandable Function Keybinds list to bind, rebind, or clear keys for script toggles, sliders, and buttons.
* **`03 // SYSTEM & AUDIO`:** Diamond toggles for Camera Glass Blur, Haptic Feedback, UI Sound Effects, and cyclic Sound Pack switcher (`Soft Pop`, `Mechanical`, `Bubble`, `Cyber`).
* **`04 // PROFILES & SESSION`:** Local multi-profile JSON manager (`Save`, `Load`, `Delete`) and `Unload / Destroy UI`.

---

## Quick Start

```lua
local TryxzLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/gthsc51/TryxzLib-/refs/heads/main/Library/Tryxz?t=" .. tostring(os.time())))()

local Window = TryxzLib:CreateWindow({
    Title = "TryxzHub",
    Subtitle = "v4.5 | Sci-Fi HUD",
    Icon = "rbxassetid://10734950309",
    Theme = "Obsidian",
    NotifPosition = "BottomRight",
    Profile = true,
    Stats = true,
    SearchBar = true,
    Haptics = true,
    Blur = { Enabled = true, Size = 14 },
    SaveConfig = {
        Enabled = true,
        SaveKey = false,
        AutoLoadPlaceId = false,
        DefaultProfile = "default",
        Folder = "TryxzLibConfigs",
        FileName = "TryxzHub_Config"
    },
    ToggleKey = Enum.KeyCode.RightControl,
    KeySystem = {
        Enabled = true,
        Title = "TryxzHub Key System",
        Icon = "rbxassetid://10723407389",
        Note = "Use key tryxz123 or copy the link below.",
        Info = {
            Title = "Access Info",
            Content = "Enter your key to unlock the Sci-Fi HUD."
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
<summary><strong>Tabs, Badges, Sub-Tabs & Structural Elements</strong></summary>

```lua
local MainTab = Window:CreateTab("General", "rbxassetid://10747373176")
MainTab:SetBadge("NEW")

local SubA = MainTab:AddSubTab("Controls")

SubA:AddSection("Player Telemetry", "rbxassetid://10734950309")

local StatusLbl = SubA:AddLabel("Status: Ready")
StatusLbl:Set("Status: Active")

SubA:AddParagraph({
    Title = "System Notice",
    Icon = "rbxassetid://10723407389",
    Content = "Structured card with internal separator."
})

SubA:AddDivider("Actions")
```

</details>

<details>
<summary><strong>Interactive Controls, RangeSlider, PlayerDropdown & Console</strong></summary>

```lua
local SelectedPlr = ""
SubA:AddPlayerDropdown({
    Name = "Target Player",
    Flag = "TargetPlrDrop",
    Callback = function(name)
        SelectedPlr = name
    end
})

SubA:AddButtonRow({
    { Name = "Teleport", Icon = "rbxassetid://10734950309", Accent = true, Callback = function() end },
    { Name = "Alert", Icon = "rbxassetid://10723407389", Callback = function()
        TryxzLib:Banner({ Text = "Target: " .. SelectedPlr, Duration = 3 })
    end }
})

local ShowRange = false
SubA:AddToggle({
    Name = "Enable Random Delay",
    Flag = "DelayToggle",
    Keybind = Enum.KeyCode.V,
    Default = false,
    Callback = function(v) ShowRange = v end
})

SubA:AddRangeSlider({
    Name = "Delay Range (ms)",
    Flag = "DelayRange",
    Min = 50,
    Max = 1000,
    DefaultMin = 150,
    DefaultMax = 450,
    VisibleIf = function() return ShowRange end,
    Callback = function(low, high)
        print("Delay:", low, high)
    end
})

SubA:AddColorPicker({
    Name = "Highlight Color",
    Flag = "ColorFlag",
    Default = Color3.fromRGB(115, 85, 255),
    Callback = function(col) end
})

local Console = SubA:AddConsole({ Name = "Terminal", Height = 130 })
Console:Log("System initialized.", "Success")
```

</details>

<details>
<summary><strong>Dialogs, Interactive Notifications & Global Methods</strong></summary>

```lua
TryxzLib:Dialog({
    Title = "Confirm Action",
    Icon = "rbxassetid://10734933222",
    Content = "Proceed with this operation?",
    ConfirmText = "Confirm",
    CancelText = "Cancel",
    OnConfirm = function()
        TryxzLib:Notify({
            Title = "Confirmed",
            Text = "Action executed.",
            Duration = 4,
            Actions = {
                { Text = "OK", Callback = function() end }
            }
        })
    end
})

TryxzLib:SetTheme("Abyss Ocean")
TryxzLib:SetSoundPreset("Cyber")
TryxzLib:RegisterSound("CustomPing", "rbxassetid://6895079853")
TryxzLib:PlaySound("CustomPing")
```

</details>

---

## Credits

Crafted and engineered by **[gthsc51](https://github.com/gthsc51)**. 
