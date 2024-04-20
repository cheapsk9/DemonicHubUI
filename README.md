# Progress UI Documentation

cat
loasd
adssd

## Loading
```lua
local UI = loadstring(game:HttpGet("https://raw.githubusercontent.com/cheapsk9/progress/main/main.lua"))()
UI.Login:SetVisible(true)
UI.Window:Open()
UI.LoginRequest:Connect(function(key)
    -- key validation here, THIS IS JUST AN EXAMPLE DONT MAKE FUN OF ME LOL
    if key == "secret" then
        -- success!
        print(success)
        -- For now, we will use CloseWindow until we implement the rest of the hub
        UI.Window:Close()
        proceed() -- proceed with whatever
    else
        -- failure
        UI.Window:ShowMessage("Error", "Could not validate key. Please ensure you have entered it correctly.")
    end
end)
```
`test` ```testy``` `test`

# Self-references

## `Screen`
The screen `ScreenGui` object.

## `Renderer`
The `BasePart` that the GUI `SurfaceGui` is adorned to.

## `Gui`
The GUI `SurfaceGui` itself.

# `Window`

## Properties
**IsMinimized** : __bool__  
Whether the window is currently minimized. Ignores playing transitions.

**IsSmall** :  __bool__  
Whether the window is currently small (50%) or normal (100%) size. Ignores playing transitions.

## Methods

**ShowMessage** (title: __string__, text: __string__) : __void__  
Displays a message within the window.

**SetMinimized** (minimized: __bool__, transition: __bool__) : __void__  
Sets whether the window is minimized.

**SetSmall** (small: __bool__, transition: __bool__) : __void__  
Sets whether the window is small (50%) or normal (100%) size.

**Open** (transition: __bool__) : __void__  
Opens the window, showing the visible content.

**Close** (transition: __bool__) : __void__  
Forces the window to close and cleans up everything.

# `Login`

## Methods
**SetVisible** (visible: __bool__) : __void__  
By default, the login UI is not visible. When set, it will determine if the login UI is visible within the window.

**Destroy** () : __void__  
Removes (calls :Destroy() on) the login UI, freeing it from memory. Use when the login UI is no longer needed.

**SetKeyLink** (text: __string__) : __void__  
Sets the key link text that is copied/displayed when the user presses the "Get Key" button.

**SetDiscordLink** (text: __string__) : __void__  
Sets the Discord link text in the help message which shows when the user presses the "Need help?" button.

## Events
**LoginRequest** (key: __string__) : __RBXScriptSignal__  
Fires when the user enters the key in the login UI.
