local Players = game:GetService("Players")
local UserInputService = game:GetService("UserInputService")
local RunService = game:GetService("RunService")

local player = Players.LocalPlayer
local camera = workspace.CurrentCamera
local mouse = player:GetMouse()

local AIM_RADIUS = 80 -- pixels de distância da mira
local AIM_STRENGTH = 0.15 -- suavidade da rotação (0.05 fraco / 0.3 forte)

local function getClosestTarget()
	local closest = nil
	local shortest = AIM_RADIUS

	
end

RunService.RenderStepped:Connect(function()
	if UserInputService:IsMouseButtonPressed(Enum.UserInputType.MouseButton2) then -- botão direito
		local target = getClosestTarget()
		if target then
			local direction = (target.Position - camera.CFrame.Position).Unit
			camera.CFrame = camera.CFrame:Lerp(CFrame.new(camera.CFrame.Position, camera.CFrame.Position + direction), AIM_STRENGTH)
		end
	end
end)
