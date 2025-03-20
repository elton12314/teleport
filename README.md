local player = game.Players.LocalPlayer
local userInputService = game:GetService("UserInputService")

local teleportLocation = CFrame.new(-313, 221, 274)

local function teleportar()
    local character = player.Character or player.CharacterAdded:Wait()
    local hrp = character:WaitForChild("HumanoidRootPart")
    hrp.CFrame = teleportLocation
end

userInputService.InputBegan:Connect(function(input, gameProcessedEvent)
    if gameProcessedEvent then return end
    if input.UserInputType == Enum.UserInputType.Keyboard and input.KeyCode == Enum.KeyCode.N then
        teleportar()
    end
end)
