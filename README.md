local Material = loadstring(game:HttpGet("https://raw.githubusercontent.com/Kinlei/MaterialLua/master/Module.lua"))()
Crystal = {}
for i,v in pairs(workspace.mapCrystalsFolder:GetChildren()) do
    table.insert(Crystal,v.Name) 
end
local X = Material.Load({
	Title = "⚡ Ninja Legends 💨 | AppleScript001",
	Style = 2,
	SizeX = 360,
	SizeY = 360,
	Theme = "Dark",
	ColorOverrides = {
		MainFrame = Color3.fromRGB(0,9,55)
	}
})
local W = X.New({
	Title = "Main"
})
W.Toggle({
	Text = "Auto Swing",
	Callback = function(Value)
	_G.Swing = Value
	while _G.Swing do
	task.wait(0.1)
	game:GetService("Players").LocalPlayer:WaitForChild("ninjaEvent"):FireServer("swingKatana")	
end
end,
Enabled = false
})
W.Toggle({
	Text = "Auto Sell x35 Coins",
	Callback = function(Value)
	_G.Sell = Value
	while _G.Sell do
	task.wait(1)
	for _,v in pairs(workspace.sellAreaCircles:GetChildren()[20]:GetDescendants()) do
		if v:IsA("TouchTransmitter") then
		firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 0) --0 is touch
		firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 1) -- 1 is untouch
end
end
end
end,
Enabled = false
})
W.Toggle({
	Text = "Auto Collect Chi-Coins",
	Callback = function(Value)
	_G.Chi = Value
	while _G.Chi do
	task.wait(1)
	local plr = game.Players.LocalPlayer
	for _,v in pairs(workspace.Hoops:GetDescendants()) do
	if v.ClassName == "MeshPart" then
	v.touchPart.CFrame = plr.Character.HumanoidRootPart.CFrame
end
end
end
end,
Enabled = false
})
W.Button({
	Text = "KOTH",
	Callback = function()
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").kingOfTheHillPart.CFrame
	end,
})
local Cry = X.New({
	Title = "Crystals"
})
local cc = Cry.Dropdown({
	Text = "Select | Crystal",
	Callback = function(t)
        Crystals = t
	end,
	Options = Crystal
})
Cry.Button({
	Text = "Tp-Checks",
	Callback = function()
		for i,v in pairs(workspace.mapCrystalsFolder[Crystals]:GetDescendants()) do
			if v.Name == "containerNamePart" then
			game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
			end
		end
	end,
})
Cry.Toggle({
	Text = "Auto Buy x1",
	Callback = function(Value)
	_G.Crys = Value
	while _G.Crys do
	task.wait(0.1)
	game:GetService("ReplicatedStorage"):WaitForChild("rEvents"):WaitForChild("openCrystalRemote"):InvokeServer("openCrystal", Crystals)
	
end
end,
Enabled = false
})
Cry.Button({
	Text = "Pet Cloning ! [Rank Dragon Warrior]",
	Callback = function()
		for _,v in pairs(workspace.cloningAreaCircle.circleInner:GetDescendants()) do
			if v:IsA("TouchTransmitter") then
			firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 0) --0 is touch
			firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 1) -- 1 is untouch
			end
		end
	end,
})
local Tele = X.New({
	Title = "Training"
})
Tele.Button({
	Text = "Mystical Waters (Good)",
	Callback = function()
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(347.74881, 8824.53809, 114.271019)
	end,
})
Tele.Button({
	Text = "Sword of Legends (Good)",
	Callback = function()
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1834.15967, 38.704483, -141.375641)
	end,
})
Tele.Button({
	Text = "Lava Pit (Bad)",
	Callback = function()
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-116.631485, 12952.5381, 271.14624)
	end,
})
Tele.Button({
	Text = "Tornado (Bad)",
	Callback = function()
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(325.641174, 16872.0938, -9.9906435)
	end,
})
local Ele = X.New({
	Title = "Element"
})
Ele.Button({
	Text = "Blazing Entity",
	Callback = function()
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(812.851501, 839.573975, -6346.03076, -0.422592998, 0, -0.906319618, 0, 1, 0, 0.906319618, 0, -0.422592998)
	end,
})
Ele.Button({
	Text = "Electral Chaos",
	Callback = function()
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(420.927673, 494.97406, -6109.57129, 0.90629667, -0, -0.422642082, 0, 1, -0, 0.422642082, 0, 0.90629667)
	end,
})
Ele.Button({
	Text = "Eternity Storm",
	Callback = function()
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1010.81116, 674.252808, -6257.79736, -0.766061664, 0, -0.642767608, 0, 1, 0, 0.642767608, 0, -0.766061664)
	end,
})
Ele.Button({
	Text = "Frost",
	Callback = function()
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1082.81274, 252.674103, -5973.46631, -0.906296611, 0, 0.422642082, 0, 1, 0, -0.422642082, 0, -0.906296611)
	end,
})
Ele.Button({
	Text = "Inferno",
	Callback = function()
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(812.851501, 252.674057, -6346.03076, -0.422592998, 0, -0.906319618, 0, 1, 0, 0.906319618, 0, -0.422592998)
	end,
})
Ele.Button({
	Text = "Lightning",
	Callback = function()
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(420.927673, 252.674103, -6103.9707, 0.90629667, -0, -0.422642082, 0, 1, -0, 0.422642082, 0, 0.90629667)
	end,
})
Ele.Button({
	Text = "Masterful Wrath",
	Callback = function()
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(812.851501, 499.273926, -6346.03076, -0.422592998, 0, -0.906319618, 0, 1, 0, 0.906319618, 0, -0.422592998)
	end,
})
Ele.Button({
	Text = "Shadow Charge",
	Callback = function()
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1082.81274, 484.774078, -5973.46631, -0.906296611, 0, 0.422642082, 0, 1, 0, -0.422642082, 0, -0.906296611)
	end,
})
Ele.Button({
	Text = "Shadow Fire",
	Callback = function()
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(568.509033, 674.252808, -6309.98193, 0.258864343, -0, -0.965913713, 0, 1, -0, 0.965913713, 0, 0.258864343)
	end,
})
local U = X.New({
	Title = "Extra"
})
U.Button({
	Text = "Islands Unlocks [All]",
	Callback = function()
		task.wait(1)
		for _,v in pairs(workspace.islandUnlockParts:GetDescendants()) do
			if v:IsA("TouchTransmitter") then
			firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 0) --0 is touch
			firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 1) -- 1 is untouch
			end
		end
	end,
})
U.Button({
	Text = "Double Jumps [Max 999]",
	Callback = function()
		task.wait(0.1)
		game.Players.LocalPlayer.multiJumpCount.Value = "999"
	end,
})
U.Button({
	Text = "Hide-Name",
	Callback = function()
		task.wait(1)
		local plrname = game.Players.LocalPlayer.Name
		workspace[plrname].Head.nameGui:Destroy()
	end,
})
