# Getting Started
Starting out with Lite is really easy. 

## Installation
To install Lite, there is really only one way. You will have to contact frames#4888 for permission to use the framwork.

## Configuration
Once you get the model, Import the model to your roblox game through the `toolbox`. No move both the main file `Lite` and the folder `LiteServices` to `ReplicatedStorage`

!!! warning
    I'd like to mention that the folder `LiteServices` is required to remain at `ReplicatedStorage` however the main module `Lite` isn't required to.

## Setup
### Server
Simply create a `Script` in `ServerScriptService` and then you will need to `require` your Lite module. This may not work if you have placed your copy of Lite somewhere other than `ReplicatedStorage`.
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Lite = require(ReplicatedStorage.Lite)
```
#### Starting on Server
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Lite = require(ReplicatedStorage.Lite)

Lite:Start() --> You can also use Lite.Start()
```
### Client
Again simply create a `LocalScript` in you client-side most commenly made in `StarterPlayerScripts`.This may not work if you have placed your copy of Lite somewhere other than `ReplicatedStorage`.
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Lite = require(ReplicatedStorage.Lite)
```
#### Starting on Client
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Lite = require(ReplicatedStorage.Lite)

Lite:Start() --> You can also use Lite.Start()
```
