Loadstring's Library

Making the Library

local Library = {
	Elements = {},
	Created = {},
}

function Library:MakeWindow(text)
	local Gui = Instance.new("ScreenGui")
	local Frames = Instance.new("Frame")
	local UICorner = Instance.new("UICorner")
	local Title = Instance.new("TextLabel")
	local UICorner_2 = Instance.new("UICorner")
	
	Gui.Name = "Gui"
	Gui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
	Gui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

	Frames.Name = "Frames"
	Frames.Parent = Gui
	Frames.BackgroundColor3 = Color3.fromRGB(85, 85, 85)
	Frames.Position = UDim2.new(0.386949897, 0, 0.248695642, 0)
	Frames.Size = UDim2.new(0, 435, 0, 289)
	Frames.Active = true
	Frames.Draggable = true


	UICorner.Parent = Frames

	Title.Name = "Title"
	Title.Parent = Frames
	Title.BackgroundColor3 = Color3.fromRGB(195, 0, 0)
	Title.Position = UDim2.new(0.0183908045, 0, 0.0207612459, 0)
	Title.Size = UDim2.new(0, 418, 0, 20)
	Title.Font = Enum.Font.SourceSans
	Title.TextColor3 = Color3.fromRGB(0, 0, 0)
	Title.TextSize = 14.000
	Title.Text = text


	UICorner_2.Parent = Title
	
	local function FuntionFinder(ElementAdded)
		print("AddedElement")
	end
	
	local function CreatedAdded()
		local funtionFinded = FuntionFinder
		print(funtionFinded())
		print("Added")
	end
	
	local ButtonCore = {}
	
	function ButtonCore:CreateButton(buttonName, Setposition, CallBack)
		local Button = Instance.new("TextButton")
		local UICorner_3 = Instance.new("UICorner")
		
		CreatedAdded()
		
		local callback = CallBack or function() end
		
		Button.Name = "Button"
		Button.Parent = Frames
		Button.BackgroundColor3 = Color3.fromRGB(195, 0, 0)
		Button.Position = Setposition
		Button.Size = UDim2.new(0, 131, 0, 30)
		Button.Font = Enum.Font.SourceSans
		Button.Text = buttonName
		Button.TextColor3 = Color3.fromRGB(0, 0, 0)
		Button.TextSize = 14.000

		UICorner_3.Parent = Button
		
		Button.MouseButton1Click:Connect(function()
			pcall(callback)
		end)
	end
	return ButtonCore
end

--[[You can make it a loadstring]]

Making a Window
local Window = Library:MakeWindow("WindowName")
--[[Window Name]]

Making a Button
Window:MakeButton("ButtonName", UDim2.new(0, 0, 0, 0), function(Value)
    print("Value")
end)
