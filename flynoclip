local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local UICorner = Instance.new("UICorner")
local TextButton = Instance.new("TextButton")
local TextButton_2 = Instance.new("TextButton")



ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(255, 44, 48)
Frame.BorderColor3 = Color3.fromRGB(0, 0, 0)
Frame.BorderSizePixel = 0
Frame.Position = UDim2.new(0.0511415526, 0, 0.307797372, 0)
Frame.Size = UDim2.new(0, 166, 0, 197)

UICorner.CornerRadius = UDim.new(0, 9)
UICorner.Parent = Frame

TextButton.Parent = Frame
TextButton.BackgroundColor3 = Color3.fromRGB(255, 0, 4)
TextButton.BorderColor3 = Color3.fromRGB(0, 0, 0)
TextButton.BorderSizePixel = 0
TextButton.Position = UDim2.new(0.216867477, 0, 0.131979689, 0)
TextButton.Size = UDim2.new(0, 94, 0, 50)
TextButton.Font = Enum.Font.SourceSans
TextButton.Text = "Noclip"
TextButton.TextColor3 = Color3.fromRGB(0, 0, 0)
TextButton.TextSize = 35.000

TextButton_2.Parent = Frame
TextButton_2.BackgroundColor3 = Color3.fromRGB(255, 0, 4)
TextButton_2.BorderColor3 = Color3.fromRGB(0, 0, 0)
TextButton_2.BorderSizePixel = 0
TextButton_2.Position = UDim2.new(0.216867477, 0, 0.568527937, 0)
TextButton_2.Size = UDim2.new(0, 94, 0, 50)
TextButton_2.Font = Enum.Font.SourceSans
TextButton_2.Text = "Fly"
TextButton_2.TextColor3 = Color3.fromRGB(0, 0, 0)
TextButton_2.TextSize = 35.000



local function NJOXIFU_fake_script() -- TextButton.LocalScript 
	local script = Instance.new('LocalScript', TextButton)

	local Player = game:GetService("Players").LocalPlayer 
	
	local RunService = game:GetService("RunService") 
	
	
	
	local isnoclipping = false 
	
	
	
	script.Parent.MouseButton1Click:Connect(function()
	
		if isnoclipping== true then
	
			isnoclipping=false
	
			script.Parent.Text = "No-Clip [OFF]" 
			
			script.Parent.BackgroundColor3 = Color3.new(1, 0, 0) 
	
		else	
	
			isnoclipping=true
	
			script.Parent.Text = "No-Clip [ON]" 
	
			script.Parent.BackgroundColor3 = Color3.new(0, 1, 0) 
	
		end
	
	end)
	
	
	
	RunService.Stepped:Connect(function()
	
		if Player.Character then
	
			if isnoclipping == true then
	
				for i,v in pairs(Player.Character:GetDescendants()) do
	
					if v:IsA("BasePart") then
	
						v.CanCollide = false
	
					end
	
				end
	
			end	
	
		end
	
	end)
end
coroutine.wrap(NJOXIFU_fake_script)()
local function ADEN_fake_script() -- TextButton_2.LocalScript 
	local script = Instance.new('LocalScript', TextButton_2)

	local button = script.Parent 
	local player = game.Players.LocalPlayer 
	local character = player.Character or player.CharacterAdded:Wait() 
	local humanoid = character:WaitForChild("Humanoid") 
	
	local flying = false 
	
	local function fly()
		flying = not flying 
	
		if flying then
			humanoid.PlatformStand = true 
			local bodyVelocity = Instance.new("BodyVelocity") 
			bodyVelocity.Velocity = Vector3.new(0, 0, 0) 
			bodyVelocity.MaxForce = Vector3.new(4000, 4000, 4000) 
			bodyVelocity.Parent = character.HumanoidRootPart 
	
			while flying do
				local camera = workspace.CurrentCamera 
				local direction = camera.CFrame.LookVector 
				bodyVelocity.Velocity = direction * 45 + Vector3.new(0, 15, 0) 
				wait(0.1) 
			end
	
			bodyVelocity:Destroy() 
			humanoid.PlatformStand = false 
		end
	end
	
	button.MouseButton1Click:Connect(fly) 
	
end
coroutine.wrap(ADEN_fake_script)()
local function FKYVEMD_fake_script() -- Frame.LocalScript 
	local script = Instance.new('LocalScript', Frame)

	local UIS = game:GetService('UserInputService')
	local frame = script.Parent
	local dragToggle = nil
	local dragSpeed = 0.25
	local dragStart = nil
	local startPos = nil
	
	local function updateInput(input)
		local delta = input.Position - dragStart
		local position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X,
			startPos.Y.Scale, startPos.Y.Offset + delta.Y)
		game:GetService('TweenService'):Create(frame, TweenInfo.new(dragSpeed), {Position = position}):Play()
	end
	
	frame.InputBegan:Connect(function(input)
		if (input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch) then 
			dragToggle = true
			dragStart = input.Position
			startPos = frame.Position
			input.Changed:Connect(function()
				if input.UserInputState == Enum.UserInputState.End then
					dragToggle = false
				end
			end)
		end
	end)
	
	UIS.InputChanged:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
			if dragToggle then
				updateInput(input)
			end
		end
	end)
end
coroutine.wrap(FKYVEMD_fake_script)()
