# Http
Http is a simple API wrapper made for `HttpService`

# Request
This uses the function `RequestAsync` built into `HttpService`.
!!! warning
    Http is in it's beta versions right now, so expect a lot of bugs as sometimes it does break.
```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Lite = require(ReplicatedStorage:WaitForChild("Lite"))
local Http = Lite.env.Http

local PayLoad = {
	Url = "https://youtube.com",
	Method = "GET",
	Headers = {},
	Body = nil,
}

local Fetch = Http.Request(PayLoad)

Fetch:Then(function(Response)
	print(Response) --> Output: Response
end):Catch(function(Error)
	error(Error) --> Output: Error
end):Await()
```