local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("xdd Hub", "DarkTheme")
local Tab = Window:NewTab("Auto Farm")
local Section = Tab:NewSection("Mon")
 
MONS = {}
 
for i,v in pairs(game:GetService("Workspace").Monster.Mon:GetChildren()) do
    table.insert(MONS,v.Name)
end
 
Section:NewToggle("Auto Farm", "", function(state)
    _G.AutoFarm = state
    while _G.AutoFarm do wait()
game:GetService('Workspace').Lives[Select].HumanoidRootPart.CFrame * CFrame.new(0,0,5)
end
end)
 
Section:NewDropdown("Please Select Monster", "", MONS, function(currentOption)
    Select = currentOption
end)
 
Section:NewButton("Refresh", "", function()
    table.clear(MONS)
for i,v in pairs(game:GetService('Workspace').Lives:GetChildren()) do
    table.insert(MONS,v.Name)
end
end)
