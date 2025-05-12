local UIS = game:GetService("UserInputService")
local VirtualInputManager = game:GetService("VirtualInputManager")
local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local LocalPlayer = Players.LocalPlayer

local ScreenGui = Instance.new("ScreenGui", game.CoreGui)
ScreenGui.Name = "WaveAutoEGui"
ScreenGui.ResetOnSpawn = false

local Frame = Instance.new("Frame", ScreenGui)
Frame.Size = UDim2.new(0, 260, 0, 220)
Frame.Position = UDim2.new(0, 100, 0, 100)
Frame.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
Frame.BorderSizePixel = 0

local UICorner = Instance.new("UICorner", Frame)
UICorner.CornerRadius = UDim.new(0, 8)

local UIStroke = Instance.new("UIStroke", Frame)
UIStroke.Color = Color3.fromRGB(0, 170, 255)
UIStroke.Thickness = 2

local Title = Instance.new("TextLabel", Frame)
Title.Size = UDim2.new(1, 0, 0, 20)
Title.Position = UDim2.new(0, 0, 0, 0)
Title.BackgroundTransparency = 1
Title.Text = "made by moni"
Title.TextColor3 = Color3.fromRGB(180, 180, 180)
Title.Font = Enum.Font.Code
Title.TextSize = 14

local function makeButton(text, positionY, color)
	local btn = Instance.new("TextButton", Frame)
	btn.Size = UDim2.new(0, 220, 0, 30)
	btn.Position = UDim2.new(0, 20, 0, positionY)
	btn.Text = text
	btn.BackgroundColor3 = color
	btn.TextColor3 = Color3.new(1,1,1)
	btn.Font = Enum.Font.Gotham
	btn.TextSize = 16
	local corner = Instance.new("UICorner", btn)
	corner.CornerRadius = UDim.new(0, 6)
	return btn
end

local ToggleE = makeButton("Auto E: OFF", 30, Color3.fromRGB(0, 170, 255))
local ToggleSpeed = makeButton("Speed: OFF", 70, Color3.fromRGB(255, 85, 0))
local ToggleNoclip = makeButton("Noclip: OFF", 110, Color3.fromRGB(170, 0, 255))
local ToggleJump = makeButton("InfJump: OFF", 150, Color3.fromRGB(0, 85, 255))

local CloseButton = Instance.new("TextButton", Frame)
CloseButton.Size = UDim2.new(0, 20, 0, 20)
CloseButton.Position = UDim2.new(1, -25, 0, 2)
CloseButton.Text = "X"
CloseButton.BackgroundColor3 = Color3.fromRGB(255, 50, 50)
CloseButton.TextColor3 = Color3.new(1, 1, 1)
CloseButton.Font = Enum.Font.GothamBold
CloseButton.TextSize = 14

local CloseCorner = Instance.new("UICorner", CloseButton)
CloseCorner.CornerRadius = UDim.new(0, 4)

CloseButton.MouseButton1Click:Connect(function()
	ScreenGui:Destroy()
end)

local dragging, dragInput, dragStart, startPos

Frame.InputBegan:Connect(function(input)
	if input.UserInputType == Enum.UserInputType.MouseButton1 then
		dragging = true
		dragStart = input.Position
		startPos = Frame.Position
		input.Changed:Connect(function()
			if input.UserInputState == Enum.UserInputState.End then dragging = false end
		end)
	end
end)

Frame.InputChanged:Connect(function(input)
	if input.UserInputType == Enum.UserInputType.MouseMovement then dragInput = input end
end)

UIS.InputChanged:Connect(function(input)
	if input == dragInput and dragging then
		local delta = input.Position - dragStart
		Frame.Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y)
	end
end)

local autoE, speedOn, noclip, infJump = false, false, false, false

ToggleE.MouseButton1Click:Connect(function()
	autoE = not autoE
	ToggleE.Text = autoE and "Auto E: ON" or "Auto E: OFF"
	ToggleE.BackgroundColor3 = autoE and Color3.fromRGB(0, 255, 127) or Color3.fromRGB(0, 170, 255)
end)

ToggleSpeed.MouseButton1Click:Connect(function()
	speedOn = not speedOn
	local char = LocalPlayer.Character
	if char and char:FindFirstChild("Humanoid") then
		char.Humanoid.WalkSpeed = speedOn and 75 or 16
	end
	ToggleSpeed.Text = speedOn and "Speed: ON" or "Speed: OFF"
	ToggleSpeed.BackgroundColor3 = speedOn and Color3.fromRGB(0, 255, 127) or Color3.fromRGB(255, 85, 0)
end)

ToggleNoclip.MouseButton1Click:Connect(function()
	noclip = not noclip
	ToggleNoclip.Text = noclip and "Noclip: ON" or "Noclip: OFF"
	ToggleNoclip.BackgroundColor3 = noclip and Color3.fromRGB(127, 0, 255) or Color3.fromRGB(170, 0, 255)
end)

ToggleJump.MouseButton1Click:Connect(function()
	infJump = not infJump
	ToggleJump.Text = infJump and "InfJump: ON" or "InfJump: OFF"
	ToggleJump.BackgroundColor3 = infJump and Color3.fromRGB(0, 255, 255) or Color3.fromRGB(0, 85, 255)
end)

RunService.Stepped:Connect(function()
	if noclip and LocalPlayer.Character then
		for _, v in pairs(LocalPlayer.Character:GetDescendants()) do
			if v:IsA("BasePart") then v.CanCollide = false end
		end
	end
end)

task.spawn(function()
	while true do
		if autoE then
			VirtualInputManager:SendKeyEvent(true, Enum.KeyCode.E, false, game)
			VirtualInputManager:SendKeyEvent(false, Enum.KeyCode.E, false, game)
		end
		task.wait(0.005)
	end
end)

UIS.JumpRequest:Connect(function()
	if infJump and LocalPlayer.Character and LocalPlayer.Character:FindFirstChild("Humanoid") then
		LocalPlayer.Character.Humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
	end
end)
