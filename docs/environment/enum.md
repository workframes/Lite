# Enum
Enums are basically constants, just like the default enums however this just gives you the ability to create your own.

## New
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Lite = require(ReplicatedStorage:WaitForChild("Lite"))
local Enum = Lite.env.Enum

local NewEnum = Enum.New("NewEnum", {"ChickenNuggets", "Shrimp", "Burger",})
```

#### Example
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Lite = require(ReplicatedStorage:WaitForChild("Lite"))
local Enum = Lite.env.Enum

local NewEnum = Enum.New("NewEnum", {"ChickenNuggets", "Shrimp", "Burger",})

local MainDish = game.workspace.MainDish

if(MainDish.Value == NewEnum.ChickenNuggets)then
	print("Main Dish is chicken nuggets") --> Outputs: Main Dish is chicken nuggets
elseif(MainDish.Value == NewEnum.Shrimp)then
	print("Main Dish is shrimp") --> Outputs: Main Dish is shrimp
elseif(MainDish.Value == NewEnum.Burger)then
	print("Main Dish is burger") --> Outputs: Main Dish is burger
end
```