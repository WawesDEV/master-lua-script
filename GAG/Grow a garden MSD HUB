local UserInputService = game:GetService("UserInputService")
local Players = game:GetService("Players")
local player = Players.LocalPlayer
local mouse = player:GetMouse()
local enabled = false

-- mobile support
local function createButton()
    local screenGui = Instance.new("ScreenGui")
    screenGui.Parent = player:WaitForChild("PlayerGui")
    
    local button = Instance.new("TextButton")
    button.Parent = screenGui
    button.Size = UDim2.new(0, 100, 0, 50)
    button.Position = UDim2.new(0.85, 0, 0.9, 0)
    button.Text = "On/Off"
    button.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
    
    button.MouseButton1Click:Connect(function()
        enabled = not enabled
        if enabled then
            button.BackgroundColor3 = Color3.fromRGB(0, 255, 0)
        else
            button.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
        end
    end)
end

createButton()

-- CTRL
local isCtrlHeld = false
UserInputService.InputBegan:Connect(function(input, gameProcessed)
    if input.KeyCode == Enum.KeyCode.LeftControl then
        isCtrlHeld = true
    end
end)

UserInputService.InputEnded:Connect(function(input, gameProcessed)
    if input.KeyCode == Enum.KeyCode.LeftControl then
        isCtrlHeld = false
    end
end)

-- delete part
mouse.Button1Down:Connect(function()
    if isCtrlHeld or enabled then
        if mouse.Target then
            mouse.Target:Destroy()
        end
    end
end)
