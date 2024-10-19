local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoid = character:WaitForChild("Humanoid")
local canPunch = false
local punching = false
local punchCooldown = 0.60 -- 


local function togglePunch()
    canPunch = not canPunch
    if canPunch then
        print("Socos ativados")
    else
        
    end
end

local function punch()
    if canPunch and not punching then
        punching = true
        print("Soco!")
        
        wait(punchCooldown)
        punching = false
    end
end

game:GetService("UserInputService").InputBegan:Connect(function(input)
    if input.KeyCode == Enum.KeyCode.P then
        togglePunch()
    end
end)

game:GetService("UserInputService").InputBegan:Connect(function(input)
    if input.KeyCode == Enum.KeyCode.E then
        punch()
    end
end)
