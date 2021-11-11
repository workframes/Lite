# Services
Services are premade functions that can be reused throughout the whole game, depending on if the `client-side` or `server-side` can access it.

## Creating a Service
To create a service simply create a `ModuleScript` in `LiteServices` and follow this structure.
!!! warning
    Make sure to name the `ModuleScript` the same name as the service.
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Lite = require(ReplicatedStorage.Lite)

return Lite.Service.New("ExampleService")
.Structure({
	Server = {},
	Client = {},
	Shared = {},
})
.Finish()
```

## Requiring a Service
To require a service on either the `client-side` or `server-side` is simple as doing this.
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Lite = require(ReplicatedStorage:WaitForChild("Lite"))
local ExampleService = Lite.Service.Require("ExampleService")
```

## Building Functions
To implement functions to your service, you will be require to structure them like this.
!!! note
    If you would like to create the function just for the `server-side` create the function inside the `Server` table in your structure or if you would like to create it just for the `client-side` create the function inside the `Client` table.
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Lite = require(ReplicatedStorage.Lite)

function RunOnServer()
	return print("Running on the server")
end

return Lite.Service.New("ExampleService")
.Structure({
	Server = {
		RunOnServer = RunOnServer
	},
	Client = {},
	Shared = {},
})
.Finish()
```
#### Running a Function
To run your function simply require your service and call the function just like this.
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Lite = require(ReplicatedStorage:WaitForChild("Lite"))
local ExampleService = Lite.Service.Require("ExampleService")

ExampleService.RunOnServer() --> Outputs: Running on the server
```
## Client-Server Boundary 
We can use the `.Expose()` function when creating a service to let the `client-side` or `server-side` use functions on the client or the server.
As an example we are going to let the client use the functions on the server.
!!! note
    You can also let the server use functions on the client. You can also expose a specific function instead of the whole server, Example: `.Expose("Server.RunOnServer", "Client")`.
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Lite = require(ReplicatedStorage.Lite)

function RunOnServer()
	return print("Running on the server")
end

return Lite.Service.New("ExampleService")
.Structure({
	Server = {
		RunOnServer = RunOnServer
	},
	Client = {},
	Shared = {},
})
.Expose("Server", "Client")
.Finish()
```
## Duplicate Functions
Lite already handles duplicate functions. If you have 2 functions with the same name on the server and the client, and the server is exposed to the client it will not error. Instead it will run both functions at the same time.
