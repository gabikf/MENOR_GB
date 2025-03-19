local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

local Window = Rayfield:CreateWindow({
   Name = "FemWare's Hub",
   Icon = 0, -- Icon in Topbar. Can use Lucide Icons (string) or Roblox Image (number). 0 to use no icon (default).
   LoadingTitle = "OP FemWare's Hub",
   LoadingSubtitle = "CRACKED BY TCOAAL",
   Theme = "Bloom", -- Check https://docs.sirius.menu/rayfield/configuration/themes

   DisableRayfieldPrompts = false,
   DisableBuildWarnings = false, -- Prevents Rayfield from warning when the script has a version mismatch with the interface

   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Big Hub"
   },

   Discord = {
      Enabled = true, -- Prompt the user to join your Discord server if their executor supports it
      Invite = "3vvDZMG6bk", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },

   KeySystem = false, -- Set this to true to use our key system
   KeySettings = {
      Title = "OP SCRIPT | Superior's Hub",
      Subtitle = "Simple Key System (KEY CAN CHANGE EVERY 48+ HRS)",
      Note = "Join Discord 'discord.gg/NSjakYggqd'", -- Use this to tell the user how to get a key
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"superkey","fg35v","3islifetime"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})

local MainTab = Window:CreateTab("🏘️ Home", 4483362458) -- Title, Image
local UniversalTab = Window:CreateTab("🚀Universal", nil) -- Title, Image
local UniversalSection = UniversalTab:CreateSection("PLAYER CONTROLS")
local Section = MainTab:CreateSection("🎮 Game-Scripts")

local Button1 = MainTab:CreateButton({
   Name = "Fight In A School | OP Script",
   Callback = function()
loadstring(game:HttpGet("https://rawscripts.net/raw/fight-in-a-school-yn-Hub-Script-28121"))()
   end,
})

local Button2 = MainTab:CreateButton({
   Name = "Infinite Yield | Admin Cmds",
   Callback = function()
-- I DONT OWN THIS SCRIPT
loadstring(game:HttpGet(('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'),true))()
   end,
})

local Button3 = MainTab:CreateButton({
   Name = "Sword Reach + OP Universal Controls",
   Callback = function()
local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

local Window = Rayfield:CreateWindow({
   Name = "(VERY OP) Sword Reach + Universal Player Controls",
   Icon = 0, -- Icon in Topbar. Can use Lucide Icons (string) or Roblox Image (number). 0 to use no icon (default).
   LoadingTitle = "(VERY OP) Sword Reach + Universal Controls",
   LoadingSubtitle = "by Superior's Hub",
   Theme = "Bloom", -- Check https://docs.sirius.menu/rayfield/configuration/themes

   DisableRayfieldPrompts = false,
   DisableBuildWarnings = false, -- Prevents Rayfield from warning when the script has a version mismatch with the interface

   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Big Hub"
   },

   Discord = {
      Enabled = false, -- Prompt the user to join your Discord server if their executor supports it
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },

   KeySystem = false, -- Set this to true to use our key system
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided", -- Use this to tell the user how to get a key
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"Hello"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})

local MainTab = Window:CreateTab("🏘️ Home", nil) -- Title, Image
local MainSection = MainTab:CreateSection("SWORD REACH")

local Toggle = MainTab:CreateToggle({
   Name = "Sword REACH (KILL AURA)",
   CurrentValue = false,
   Flag = "Toggle1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
      -- The function that takes place when the toggle is pressed
      local Library = loadstring(Game:HttpGet("https://raw.githubusercontent.com/bloodball/-back-ups-for-libs/main/wizard"))()
local PhantomForcesWindow = Library:NewWindow("Universal sword reach")
local KillingCheats = PhantomForcesWindow:NewSection("Kill Options")

local hitboxSize = 30
local hitboxActive = false
local colors = {Color3.fromRGB(255, 0, 0), Color3.fromRGB(0, 255, 0), Color3.fromRGB(0, 0, 255), Color3.fromRGB(255, 255, 0)}

local function ModifyHitbox(size)
    local player = game:GetService("Players").LocalPlayer
    local char = player.Character
    if not char then return end

    local tool = nil
    for _, v in pairs(char:GetChildren()) do
        if v:IsA("Tool") then
            tool = v
            break
        end
    end

    if not tool then
        game.StarterGui:SetCore("SendNotification", {
            Title = "Need Tool";
            Text = "Need Tool";
            Duration = 5;
        })
        return
    end

    hitboxActive = size > 1

    if hitboxActive then
        local sound = Instance.new("Sound")
        sound.SoundId = "rbxassetid://413861777"
        sound.Parent = game:GetService("SoundService")
        sound:Play()

        local handle = tool:FindFirstChild("Handle")
        if handle then
            handle.Massless = true
            handle.Transparency = 1
            handle.Size = Vector3.new(size, size, size)

            local selectionBox = Instance.new("SelectionBox", handle)
            selectionBox.Adornee = handle

            spawn(function()
                local index = 1
                while hitboxActive do
                    selectionBox.Color3 = colors[index]
                    index = (index % #colors) + 1
                    wait(0.5)
                end
                selectionBox:Destroy()
            end)
        end
    else
        if tool and tool:FindFirstChild("Handle") then
            local handle = tool.Handle
            handle.Size = Vector3.new(1, 1, 1)
            for _, v in pairs(handle:GetChildren()) do
                if v:IsA("SelectionBox") then
                    v:Destroy()
                end
            end
        end
    end
end

KillingCheats:CreateButton("Increase Hitbox", function()
    hitboxSize = hitboxSize + 5
    ModifyHitbox(hitboxSize)
end)

KillingCheats:CreateButton("Decrease Hitbox", function()
    if hitboxSize > 5 then
        hitboxSize = hitboxSize - 5
        ModifyHitbox(hitboxSize)
    end
end)

KillingCheats:CreateButton("Reset Hitbox", function()
    hitboxSize = 1
    ModifyHitbox(hitboxSize)
end)
   end,
})

local Divider = MainTab:CreateDivider()
local Section = MainTab:CreateSection("AUTOCLICKER")

local Toggle = MainTab:CreateToggle({
   Name = "OP Autoclicker",
   CurrentValue = false,
   Flag = "Toggle2", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
loadstring(game:HttpGet("https://raw.githubusercontent.com/Hosvile/The-telligence/main/MC%20KSystem%202"))()
   end,
})

local Divider2 = MainTab:CreateDivider()
local Section2 = MainTab:CreateSection("Universal")

local Slider = MainTab:CreateSlider({
   Name = "WalkSpeed Changer",
   Range = {0, 200},
   Increment = 10,
   Suffix = "Speed",
   CurrentValue = 10,
   Flag = "Slider1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
      -- The function that takes place when the slider changes
      -- Set the player's walk speed to the value of the slider
      game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = Value
   end,
})

local Slider2 = MainTab:CreateSlider({
   Name = "Jumppower Changer",
   Range = {0, 300},
   Increment = 10,
   Suffix = "JumpPower",
   CurrentValue = 10,
   Flag = "Slider2", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
      -- The function that takes place when the slider changes
      -- Set the player's jump power to the value of the slider
      game.Players.LocalPlayer.Character.Humanoid.JumpPower = Value
   end,
})

local ButtonOn = MainTab:CreateButton({
   Name = "Infinite Jump (TURN ON)",
   Callback = function()
   -- Infinite Jump Script by Ashborn
-- Discord: ashbornthegoat

-- Services
local Players = game:GetService("Players")
local UserInputService = game:GetService("UserInputService")

-- Get the local player and their character
local localPlayer = Players.LocalPlayer
local character = localPlayer.Character or localPlayer.CharacterAdded:Wait()
local humanoid = character:WaitForChild("Humanoid")

-- Infinite jump logic
UserInputService.JumpRequest:Connect(function()
    if humanoid then
        humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
    end
end)
   end,
})

local ButtonOff = MainTab:CreateButton({
   Name = "Infinite Jump (TURN OFF 'will reset character')",
   Callback = function()
local function forceResetAction()
    local player = game.Players.LocalPlayer
    if player.Character and player.Character:FindFirstChild("Humanoid") then
        player.Character.Humanoid.Health = 0
    end
end
   end,
})

local FlyButton = MainTab:CreateButton({
   Name = "FLY GUI V3",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/XNEOFF/FlyGuiV3/main/FlyGuiV3.txt"))()
   end,
})

Rayfield:LoadConfiguration()
   end,
})

local Button4 = MainTab:CreateButton({
   Name = "LUCKY BLOCK Battlegrounds",
   Callback = function()
loadstring(game:HttpGet(('https://raw.githubusercontent.com/idkevenknowburh/c/refs/heads/main/d'),true))()
   end,
})

local Button5 = MainTab:CreateButton({
   Name = "(UPDATED) Legends of Speed V2 | OP",
   Callback = function()
loadstring(game:HttpGet(('https://raw.githubusercontent.com/idkevenknowburh/legends-of-speed/refs/heads/main/script'),true))()
   end,
})

local Button6 = MainTab:CreateButton({
   Name = "Murder Mystery 2 | OP!",
   Callback = function()
loadstring(game:HttpGet(('https://raw.githubusercontent.com/MarsQQ/ScriptHubScripts/master/MM2%20Admin%20Panel'), true))()
   end,
})

local Button7 = MainTab:CreateButton({
   Name = "Prison Life | OP!",
   Callback = function()
loadstring(game:HttpGet('https://raw.githubusercontent.com/devguy100/PrizzLife/main/Source/release_v0.8.1.lua'))()
   end,
})

local Button8 = MainTab:CreateButton({
   Name = "Fisch | OP!",
   Callback = function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/AhmadV99/Speed-Hub-X/main/Speed%20Hub%20X.lua", true))()
   end,
})

local Button9 = MainTab:CreateButton({
   Name = "KAT! | OP",
   Callback = function()
   loadstring(game:HttpGet(('https://raw.githubusercontent.com/idkevenknowburh/kat/refs/heads/main/s'),true))()
   end,
})

local ToggleOP = UniversalTab:CreateToggle({
   Name = "OP Autoclicker",
   CurrentValue = false,
   Flag = "Toggle2", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
loadstring(game:HttpGet("https://raw.githubusercontent.com/Hosvile/The-telligence/main/MC%20KSystem%202"))()
   end,
})

local Slider21 = UniversalTab:CreateSlider({
   Name = "WalkSpeed Changer",
   Range = {0, 200},
   Increment = 10,
   Suffix = "Speed",
   CurrentValue = 10,
   Flag = "Slider21", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
      -- The function that takes place when the slider changes
      -- Set the player's walk speed to the value of the slider
      game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = Value
   end,
})

local Slider22 = UniversalTab:CreateSlider({
   Name = "Jumppower Changer",
   Range = {0, 300},
   Increment = 10,
   Suffix = "JumpPower",
   CurrentValue = 10,
   Flag = "Slider22", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
      -- The function that takes place when the slider changes
      -- Set the player's jump power to the value of the slider
      game.Players.LocalPlayer.Character.Humanoid.JumpPower = Value
   end,
})

local ButtonOn1 = UniversalTab:CreateButton({
   Name = "Infinite Jump (TURN ON)",
   Callback = function()
   -- Infinite Jump Script by Ashborn
-- Discord: ashbornthegoat

-- Services
local Players = game:GetService("Players")
local UserInputService = game:GetService("UserInputService")

-- Get the local player and their character
local localPlayer = Players.LocalPlayer
local character = localPlayer.Character or localPlayer.CharacterAdded:Wait()
local humanoid = character:WaitForChild("Humanoid")

-- Infinite jump logic
UserInputService.JumpRequest:Connect(function()
    if humanoid then
        humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
    end
end)
   end,
})

local ButtonOff1 = UniversalTab:CreateButton({
   Name = "Infinite Jump (TURN OFF 'will reset character')",
   Callback = function()
local function forceResetAction()
    local player = game.Players.LocalPlayer
    if player.Character and player.Character:FindFirstChild("Humanoid") then
        player.Character.Humanoid.Health = 0
    end
end
   end,
})

local FlyButton2 = UniversalTab:CreateButton({
   Name = "FLY GUI V3",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/XNEOFF/FlyGuiV3/main/FlyGuiV3.txt"))()
   end,
})

local AimBotButton = UniversalTab:CreateButton({
   Name = "(FE) Aimbot GUI (WORKS IN ALL GAMES)",
   Callback = function()
   local Players = game:GetService("Players")
	local UserInputService = game:GetService("UserInputService")
	local RunService = game:GetService("RunService")
	local localPlayer = Players.LocalPlayer
	local camera = game:GetService("Workspace").CurrentCamera
	local lockOnActive = false
	local teamCheckActive = false
	local currentTouch = nil
	local fovRadius = 125
	local screenGui = Instance.new("ScreenGui")
	screenGui.Parent = game:GetService("CoreGui")
	local toggleButton = Instance.new("TextButton")
	toggleButton.Parent = screenGui
	toggleButton.Size = UDim2.new(0, 150, 0, 50)
	toggleButton.Position = UDim2.new(0, 100, 0, 100)
	toggleButton.Text = "Toggle Lock-On"
	toggleButton.Draggable = true
	local toggleTeamButton = Instance.new("TextButton")
	toggleTeamButton.Parent = screenGui
	toggleTeamButton.Size = UDim2.new(0, 150, 0, 50)
	toggleTeamButton.Position = UDim2.new(0, 100, 0, 160)
	toggleTeamButton.Text = "Toggle Team Check"
	toggleTeamButton.Draggable = true
	local fovCircleGui = Instance.new("ImageLabel")
	fovCircleGui.Parent = screenGui
	fovCircleGui.AnchorPoint = Vector2.new(0.5, 0.5)
	fovCircleGui.Size = UDim2.new(0, fovRadius * 2, 0, fovRadius * 2)
	fovCircleGui.Image = "rbxassetid://432312433"
	fovCircleGui.ImageTransparency = 0.5
	fovCircleGui.ImageColor3 = Color3.new(1, 1, 1)
	fovCircleGui.BackgroundTransparency = 1
	fovCircleGui.Visible = false
	fovCircleGui.ZIndex = 0
	local function isPlayerVisible(targetPlayer)
		if not targetPlayer.Character or not targetPlayer.Character:FindFirstChild("Head") then
			return false
		end
		if teamCheckActive and targetPlayer.Team == localPlayer.Team then
			return false
		end
		local targetHeadPosition = targetPlayer.Character.Head.Position
		local vectorToTarget = (targetHeadPosition - camera.CFrame.Position).unit
		local ray = Ray.new(camera.CFrame.Position, vectorToTarget * fovRadius)
		local part, position = game:GetService("Workspace"):FindPartOnRay(ray, localPlayer.Character, false, true)
		if part and part:IsDescendantOf(targetPlayer.Character) then
			local dotProduct = camera.CFrame.LookVector:Dot(vectorToTarget)
			local angle = math.deg(math.acos(dotProduct))
			return angle <= (fovRadius / 2)
		end
		return false
	end
	toggleButton.MouseButton1Click:Connect(function()
		lockOnActive = not lockOnActive
		toggleButton.Text = lockOnActive and "Lock-On Active" or "Toggle Lock-On"
		fovCircleGui.Visible = lockOnActive
	end)
	toggleTeamButton.MouseButton1Click:Connect(function()
		teamCheckActive = not teamCheckActive
		toggleTeamButton.Text = teamCheckActive and "Team Check Active" or "Toggle Team Check"
	end)
	local function onTouchStarted(touch)
		currentTouch = touch.Position
		fovCircleGui.Position = UDim2.new(0, touch.Position.X - fovRadius, 0, touch.Position.Y - fovRadius)
		fovCircleGui.Visible = true
	end
	local function onTouchEnded(touch)
		if currentTouch and currentTouch == touch.Position then
			currentTouch = nil
			fovCircleGui.Visible = false
		end
	end
	UserInputService.TouchStarted:Connect(onTouchStarted)
	UserInputService.TouchEnded:Connect(onTouchEnded)
	RunService.RenderStepped:Connect(function()
		if lockOnActive then
			for _, player in ipairs(Players:GetPlayers()) do
				if player ~= localPlayer and isPlayerVisible(player) then
					local head = player.Character.Head
					local direction = (head.Position - camera.CFrame.Position).unit
					camera.CFrame = CFrame.new(camera.CFrame.Position, camera.CFrame.Position + direction * 10)
					break
				end
			end
		end
	end)
   end,
})

Rayfield:LoadConfiguration()
