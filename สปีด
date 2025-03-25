local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoid = character:WaitForChild("Humanoid")

-- ค่า WalkSpeed เริ่มต้น
local baseSpeed = 16 
local isSpeedOn = false  -- สถานะเปิด/ปิด

-- GUI
local screenGui = Instance.new("ScreenGui", player:WaitForChild("PlayerGui"))
local frame = Instance.new("Frame", screenGui)
frame.Size = UDim2.new(0, 200, 0, 150)
frame.Position = UDim2.new(0.5, -100, 0.2, 0)
frame.BackgroundColor3 = Color3.fromRGB(50, 50, 50)

local title = Instance.new("TextLabel", frame)
title.Size = UDim2.new(1, 0, 0, 30)
title.Text = "Speed GUI"
title.TextColor3 = Color3.new(1, 1, 1)
title.BackgroundTransparency = 1

local multiplierBox = Instance.new("TextBox", frame)
multiplierBox.Size = UDim2.new(1, -20, 0, 30)
multiplierBox.Position = UDim2.new(0, 10, 0, 40)
multiplierBox.Text = "Enter Multiplier"
multiplierBox.TextScaled = true
multiplierBox.BackgroundColor3 = Color3.fromRGB(100, 100, 100)
multiplierBox.TextColor3 = Color3.new(1, 1, 1)

local toggleButton = Instance.new("TextButton", frame)
toggleButton.Size = UDim2.new(1, -20, 0, 30)
toggleButton.Position = UDim2.new(0, 10, 0, 80)
toggleButton.Text = "Enable Speed"
toggleButton.BackgroundColor3 = Color3.fromRGB(0, 150, 0)
toggleButton.TextColor3 = Color3.new(1, 1, 1)

local statusLabel = Instance.new("TextLabel", frame)
statusLabel.Size = UDim2.new(1, 0, 0, 30)
statusLabel.Position = UDim2.new(0, 0, 0, 120)
statusLabel.Text = "Current Speed: " .. humanoid.WalkSpeed
statusLabel.TextColor3 = Color3.new(1, 1, 1)
statusLabel.BackgroundTransparency = 1

-- ฟังก์ชันเปิด/ปิด Speed
local function toggleSpeed()
    local multiplier = tonumber(multiplierBox.Text)  -- รับค่าจาก TextBox
    if multiplier and multiplier > 0 then
        if isSpeedOn then
            humanoid.WalkSpeed = baseSpeed -- กลับเป็นปกติ
            toggleButton.Text = "Enable Speed"
            toggleButton.BackgroundColor3 = Color3.fromRGB(0, 150, 0)
        else
            humanoid.WalkSpeed = baseSpeed * multiplier -- คูณตามที่เลือก
            toggleButton.Text = "Disable Speed"
            toggleButton.BackgroundColor3 = Color3.fromRGB(150, 0, 0)
        end
        isSpeedOn = not isSpeedOn
        statusLabel.Text = "Current Speed: " .. humanoid.WalkSpeed
    else
        multiplierBox.Text = "Invalid Number"
    end
end

toggleButton.MouseButton1Click:Connect(toggleSpeed)
