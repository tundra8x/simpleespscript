local function addNameTagEsp(targetPlayer)
	local character = targetPlayer.Character
	if character then
		local head = character:FindFirstChild("Head")
		if head then
			local billboardGui = Instance.new("BillboardGui")
			billboardGui.Name = "NameTag"
			billboardGui.ExtentsOffset = Vector3.new(0, 2, 0)
			billboardGui.AlwaysOnTop = true
			billboardGui.MaxDistance = 1000000000
			billboardGui.Size = UDim2.new(7, 0, 2, 0)
			billboardGui.Adornee = head
			billboardGui.Parent = head

			local textLabel = Instance.new("TextLabel")
			textLabel.Name = "NameTagLabel"
			textLabel.Size = UDim2.new(1,0,1,0)
			textLabel.TextScaled = true
			textLabel.BackgroundTransparency = 1
			textLabel.AnchorPoint = Vector2.new(0.5, 0.5)
			textLabel.Position = UDim2.new(0.5,0,0.5,0)
			textLabel.TextStrokeColor3 = Color3.new(0, 0, 0)
			textLabel.TextColor3 = Color3.new(1, 1, 1)
			textLabel.TextStrokeTransparency = 0
			textLabel.Text = targetPlayer.Name
			textLabel.Parent = billboardGui
			targetPlayer.CharacterAdded:Connect(function(newCharacter)
				addNameTagEsp(targetPlayer)
			end)
			targetPlayer.CharacterRemoving:Connect(function()
				billboardGui:Destroy()
			end)
		end
	end
end

local function addTagToAllPlayers()
	for _, otherPlayer in ipairs(game.Players:GetPlayers()) do
		if otherPlayer ~= player then
			addNameTagEsp(otherPlayer)
		end
	end
end
