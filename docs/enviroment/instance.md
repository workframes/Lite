# Instance

## Usage
`Instance` is a replacement of the default function `Instance.new()`. It lets you edit the properties of the object without calling the variable.

!!! warning
    `.Finish()` has to be called everytime when you done editing the properties of the object.
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Lite = require(ReplicatedStorage:WaitForChild("Lite"))
local Instance = Lite.env.Instance

local Part = Instance.New("Part")
.Parent(workspace)
.Finish()
```