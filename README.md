local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("Slayer Tycoon", "Sentinel")

local Tab = Window:NewTab("Farming")
local Section = Tab:NewSection("Farming")


Section:NewToggle("Auto Mine Wood", "Auto Mines the Wood", function(state)
    if state then
        print("Toggle On")
        shared.Enabled = true

local plr = game.Players.LocalPlayer
local char = plr.Character
local hatchet = plr.Backpack.Hatchet or char.Hatchet


for i,v in pairs(workspace.Map:GetChildren())do
   if v:FindFirstChild("WoodHitPart") and v.Leaves.Transparency == 0 and shared.Enabled then
       repeat wait()
           char.Humanoid:EquipTool(hatchet)
           wait()
           hatchet:Activate()
           char:SetPrimaryPartCFrame(v.WoodHitPart.CFrame)
       until v.Leaves.Transparency == 1
   end
end
    else
        print("Toggle Off")
        shared.Enabled = false

local plr = game.Players.LocalPlayer
local char = plr.Character
local hatchet = plr.Backpack.Hatchet or char.Hatchet


for i,v in pairs(workspace.Map:GetChildren())do
   if v:FindFirstChild("WoodHitPart") and v.Leaves.Transparency == 0 and shared.Enabled then
       repeat wait()
           char.Humanoid:EquipTool(hatchet)
           wait()
           hatchet:Activate()
           char:SetPrimaryPartCFrame(v.WoodHitPart.CFrame)
       until v.Leaves.Transparency == 1
   end
end
    end
end)



Section:NewToggle("Auto Steal Money", "Steals/Mining the money", function(state)
    if state then
        print("Toggle On")
        getgenv().toggleison = true; --set this to false if you want to turn it off or true to turn on

while getgenv().toggleison do
   wait(1)
for i,v in pairs(game:GetService("Workspace").TycoonSets.Tycoons:GetDescendants()) do
   if v:IsA("TouchTransmitter") and v.Parent.Name == "Giver" then
      firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 0) 
      firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 1)
   end
end
end
    else
        print("Toggle Off")
        getgenv().toggleison = false; --set this to false if you want to turn it off or true to turn on

while getgenv().toggleison do
   wait(1)
for i,v in pairs(game:GetService("Workspace").TycoonSets.Tycoons:GetDescendants()) do
   if v:IsA("TouchTransmitter") and v.Parent.Name == "Giver" then
      firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 0) 
      firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart, v.Parent, 1)
   end
end
end
    end
end)



Section:NewToggle("AutoFarm Money", "Farming Money", function(state)
    if state then
        print("Toggle On")
        --https://www.roblox.com/games/6490016198/Slayer-Tycoon-v1-1


_G.Toggle = enabled--Change to enabled to enable the money farm, Change to anything to disable.

loadstring(game:HttpGet('https://raw.githubusercontent.com/MonkeyDLuffyx/Scripts/Slayer-Tycoon-(v1.1)/Slayer%20Tycoon%20Money%20Farm.lua', true))()
    else
        print("Toggle Off")
        --https://www.roblox.com/games/6490016198/Slayer-Tycoon-v1-1


_G.Toggle = disable--Change to enabled to enable the money farm, Change to anything to disable.

loadstring(game:HttpGet('https://raw.githubusercontent.com/MonkeyDLuffyx/Scripts/Slayer-Tycoon-(v1.1)/Slayer%20Tycoon%20Money%20Farm.lua', true))()
    end
end)


local Tab = Window:NewTab("Credits")
local Section = Tab:NewSection("Made by: rblx-scripts.com#0031")


