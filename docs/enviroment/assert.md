# Instance

## Usage
`Assert` is a simple replacment for the default function `assert()`.

!!! note
    Lite will check if the first @parm that is passed is true, if not it will run the second @parm, a function.

```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Lite = require(ReplicatedStorage:WaitForChild("Lite"))
local Assert = Lite.env.Assert

local MyTable = {}

Assert(type(MyTable) == "table", function()
	print("MyTable is not a table")
end)
```