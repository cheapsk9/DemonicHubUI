# Progress UI Documentation

cat
loasd
adssd

## Loading
```lua
local UI = loadstring(game:HttpGet("https://raw.githubusercontent.com/cheapsk9/DemonicHubUI/main/main.lua"))()
UI:SetKeyUIVisible(true)
UI:OpenWindow()
UI.LoginRequest:Connect(function(key)
    -- key validation here, THIS IS JUST AN EXAMPLE DONT MAKE FUN OF ME LOL
    if key == "secret" then
        -- success!
        print(success)
        -- For now, we will use CloseWindow until we implement the rest of the hub
        UI:CloseWindow()
        proceed() -- proceed with whatever
    else
        -- failure
        UI:ShowMessage("Error", "Could not validate key. Please ensure you have entered it correctly.")
    end
end)
```
`test` ```testy``` `test`

# Window

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

# Login

## Methods
**SetVisible** (visible: __bool__) : **void**  
By default, the login UI is not visible. When set, it will determine if the login UI is visible within the window.

**Destroy** () : __void__  
Removes (calls :Destroy() on) the login UI, freeing it from memory. Use when the login UI is no longer needed.

## Events
**LoginRequest** (key: __string__) : __RBXScriptSignal__  
Fires when the user enters the key in the login UI.
