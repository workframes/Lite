# Table
Table includes multiple functions such as to clone, filter, and clean a table that is passed through

## Filter
The first @parm of is the table you want to pass. The seconds parm includes the object you want to filter for.

!!! note
    The filter(Second @parm) can be either a `string` or a `table`, Example: `"a"` or `{"a", "b"}`
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Lite = require(ReplicatedStorage:WaitForChild("Lite"))
local Table = Lite.env.Table

local MyTable = {"a", "b", "c", "d", "e", "f", "g", "a", "b", "c", "d", "e", "f", "g"}

Table.Filter(MyTable, "a") --> Output: {"a", "a"}
```

## Clean
The first @parm of is the table you want to pass. The seconds parm includes the object you want to filter out.

!!! note
    The filter(Second @parm) can be either a `string` or a `table`, Example: `"a"` or `{"a", "b"}`
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Lite = require(ReplicatedStorage:WaitForChild("Lite"))
local Table = Lite.env.Table

local MyTable = {"a", "b", "c", "d", "e", "f", "g", "a", "b", "c", "d", "e", "f", "g"}

print(Table.Clean(MyTable, "a")) --> Output: {"b", "c", "d", "e", "f", "g", "b", "c", "d", "e", "f", "g"}
```

## Clone
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Lite = require(ReplicatedStorage:WaitForChild("Lite"))
local Table = Lite.env.Table

local MyTable = {"a", "b", "c", "d", "e", "f", "g", "a", "b", "c", "d", "e", "f", "g"}

Table.Clone(MyTable) --> Output: {"a", "b", "c", "d", "e", "f", "g", "a", "b", "c", "d", "e", "f", "g"}

```

