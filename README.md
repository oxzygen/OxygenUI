# Oxygen - Roblox UI Library  

![Roblox](https://img.shields.io/badge/Roblox-UI%20Library-red?style=flat-square&logo=roblox)  
![Lua](https://img.shields.io/badge/Made%20with-Lua-blue?style=flat-square)  
![Status](https://img.shields.io/badge/Status-Active-success?style=flat-square)  
![Icons](https://img.shields.io/badge/Icons%20used%20from-lucide.dev-red?style=flat-square)

---

## Features  
- Multiple tabs and sections  
- Toggles, sliders, dropdowns, and buttons  
- Smooth animations with TweenService  
- Built-in icons and logo support  
- Easy setup & usage  

---

# Installation  
```lua
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/oxzygen/OxygenUI/ui/oxygen.lua"))()
```

# Usage

## Create a Window
```lua
local Window = Library.new({
    Title = "My Hub",
    Description = "Best Hub Ever",
    Logo = "rbxassetid://1234567890", -- optional
    Keybind = Enum.KeyCode.LeftControl, -- default toggle
})
```

## Add a Tab
```lua
local Tab = Window:NewTab({
    Title = "Main",
    Description = "Main Features",
    Icon = "rbxassetid://7733964640"
})
```

## Add a Section
```lua
local Section = Tab:NewSection({
    Title = "Player Options",
    Position = "Left" -- "Left" or "Right"
})
```

# Components

## Toggle
```lua
Section:NewToggle({
    Title = "God Mode",
    Default = false,
    Callback = function(value)
        print("God Mode:", value)
    end
})
```

## Slider
```lua
Section:NewSlider({
    Title = "WalkSpeed",
    Min = 16,
    Max = 100,
    Default = 16,
    Callback = function(value)
        game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = value
    end
})
```

## Dropdown
```lua
Section:NewDropdown({
    Title = "Team Select",
    Options = {"Red", "Blue", "Green"},
    Default = "Red",
    Callback = function(selected)
        print("Selected team:", selected)
    end
})
```

## Button
```lua
Section:NewButton({
    Title = "Teleport",
    Callback = function()
        print("Teleported!")
    end
})
```

# API Reference

**Library.new(config: table)**

Creates a new window.

- Title (string) – Window title
- Description (string) – Subtitle / description
- Logo (string) – Image asset ID (optional)
- Keybind (Enum.KeyCode) – Toggle key (default: LeftControl)

**Window:NewTab(config: table)**

Creates a new tab inside the window.

- Title (string) – Tab name
- Description (string) – Tab description
- Icon (string) – Image asset ID

**Tab:NewSection(config: table)**

- Creates a section within a tab.
- Title (string) – Section title
-Position (string) – "Left" or "Right"

**Section:NewToggle(config: table)**

Creates a toggle switch.

- Title (string)
- Default (boolean)
- Callback(value: boolean)

**Section:NewSlider(config: table)**

Creates a slider.

- Title (string)
- Min (number)
- Max (number)
- Default (number)
- Callback(value: number)

**Section:NewDropdown(config: table)**

Creates a dropdown menu.

- Title (string)
- Options (table)
- Default (string)
- Callback(selected: string)

**Section:NewButton(config: table)**

Creates a button.

- Title (string)
- Callback()
