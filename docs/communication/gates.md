# Gates
Gates are a simple way of communicating to the client or the server.

## Creating a Gate
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Lite = require(ReplicatedStorage:WaitForChild("Lite"))

Lite.Gate.New("ExampleGate")
```

## Wait for Gate
**NOTE!**
    Wait is used for a single time, it's not used to recieve data constantly.

#### Client 
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Lite = require(ReplicatedStorage:WaitForChild("Lite"))

Lite.Gate.Wait("ExampleGate") --> Outputs: Hello from server!
```

#### Server
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Lite = require(ReplicatedStorage:WaitForChild("Lite"))

Lite.Gate.Send("ExampleGate", "Hello from server!")
```

## Constant Communication
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Lite = require(ReplicatedStorage:WaitForChild("Lite"))

Lite.Gate.Recieve("ExampleGate", function(...)
	--> Do Stuff
end) 
```

