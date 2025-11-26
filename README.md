--(F1 to Toggle Speed, Execute the Script Below!)--

-- [ Variables ]
local Player = game.Players.LocalPlayer
local Humanoid = Player.Character:WaitForChild("Humanoid")
local OriginalSpeed = Humanoid.WalkSpeed
local SpeedToggled = false

-- [ Toggle Speed ]
game.UserInputService.InputBegan:Connect(function(inp, gp)
if Humanoid and not gp and inp.KeyCode == Enum.KeyCode.F1 then
if not SpeedToggled then
Humanoid.WalkSpeed = 40
else
Humanoid.WalkSpeed = OriginalSpeed
end
SpeedToggled = not SpeedToggled
end
end)
Player.CharacterAdded:Connect(function()
Humanoid = Player.Character:WaitForChild("Humanoid")
end)
