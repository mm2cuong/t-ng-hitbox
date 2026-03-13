-- HITBOX KIỂU BUDDHA / DRAGON (RẤT TO) + MENU BẬT/TẮT + KHÔNG MẤT KHI RESET

local player = game.Players.LocalPlayer

local gui = Instance.new("ScreenGui")
gui.Name = "HitboxMenu"
gui.ResetOnSpawn = false
gui.Parent = player:WaitForChild("PlayerGui")

local button = Instance.new("TextButton")
button.Size = UDim2.new(0,200,0,50)
button.Position = UDim2.new(0,20,0,80)
button.Text = "BUDDHA HITBOX : OFF"
button.Parent = gui

local enabled = false
local size = 120 -- kích thước kiểu Buddha / Dragon

local function applyHitbox()
	for _,v in pairs(workspace:GetDescendants()) do
		
		if v:IsA("Humanoid") then
			
			local hrp = v.Parent:FindFirstChild("HumanoidRootPart")
			
			if hrp and v.Parent ~= player.Character then
				
				hrp.Size = Vector3.new(size,size,size)
				hrp.Transparency = 0.4
				hrp.CanCollide = false
				
			end
			
		end
		
	end
end

local function resetHitbox()
	for _,v in pairs(workspace:GetDescendants()) do
		
		if v:IsA("Humanoid") then
			
			local hrp = v.Parent:FindFirstChild("HumanoidRootPart")
			
			if hrp then
				hrp.Size = Vector3.new(2,2,1)
				hrp.Transparency = 1
			end
			
		end
		
	end
end

button.MouseButton1Click:Connect(function()
	enabled = not enabled
	
	if enabled then
		button.Text = "BUDDHA HITBOX : ON"
	else
		button.Text = "BUDDHA HITBOX : OFF"
		resetHitbox()
	end
	
end)

while true do
	if enabled then
		applyHitbox()
	end
	task.wait(0.5)
end
