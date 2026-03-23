-- UI Fluent
local Fluent = loadstring(game:HttpGet("https://github.com/dawid-scripts/Fluent/releases/latest/download/main.lua"))()

local Window = Fluent:CreateWindow({
    Title = "Auto Sell",
    SubTitle = "Control Panel",
    TabWidth = 160,
    Size = UDim2.fromOffset(400, 300),
    Acrylic = true,
    Theme = "Dark"
})

local Tab = Window:AddTab({
    Title = "Main",
    Icon = "home"
})

-- =========================
-- โค้ดเดิมของคุณ (ไม่แก้)
-- =========================
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")
local RunService = game:GetService("RunService")

local Player = Players.LocalPlayer
local PlayerGui = Player:WaitForChild("PlayerGui")
local HouseEvent = ReplicatedStorage:WaitForChild("House")

local AutoSell = false
local loopConnection = nil

-- =========================
-- Fluent Toggle (คุมตัวแปรเดิม)
-- =========================
Tab:AddToggle("AutoSellToggle", {
    Title = "ปั้มเงิน",
    Default = false,
    Callback = function(Value)
        AutoSell = Value

        if AutoSell then
            loopConnection = RunService.Heartbeat:Connect(function()
                for i = 1, 20 do
                    HouseEvent:FireServer("Sell")
                end
                task.wait(0.00)
            end)
        else
            if loopConnection then
                loopConnection:Disconnect()
                loopConnection = nil
            end
        end
    end
})

-- =========================
-- SOCIAL BUTTONS
-- =========================

Tab:AddButton({
    Title = "Copy Discord",
    Description = "กดเพื่อคัดลอก Discord",
    Callback = function()
        setclipboard("https://discord.gg/W3ZJry6nTu") -- 🔁 ใส่ลิงก์จริง
        Fluent:Notify({
            Title = "Copied!",
            Content = "คัดลอก Discord แล้ว",
            Duration = 3
        })
    end
})

Tab:AddButton({
    Title = "Copy Instagram",
    Description = "กดเพื่อคัดลอก IG",
    Callback = function()
        setclipboard("https://www.instagram.com/ezmxyxii/") -- 🔁 ใส่ลิงก์จริง
        Fluent:Notify({
            Title = "Copied!",
            Content = "คัดลอก Instagram แล้ว",
            Duration = 3
        })
    end
})
