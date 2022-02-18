# FixedVRRorilla
This is a fixed version of saucekid's Rorilla VR Script.

saucekid's Rorilla VR Script Net was outdated, so if you have a new net, you can just insert net script into options.Net :)

# Script

```lua
options = {}
options.HeadScale = 2          -- Headscale of camera (Does not change actual head size)
options.FakeHandsTransparency = 1  -- Transparency of Arm Hitboxes
options.Bubblechat = true     -- Force Bubblechat

options.PointerRange = 10    -- Range you can click buttons with your arm

options.TurnDelay = 0.05       -- Delay in sec. for how fast you can turn left and right
options.TurnAngle = 15       -- Change in angle left/right (degrees)

options.ChatEnabled = true    -- See chat on your left hand in-game
options.ChatLocalRange = 70  -- Local chat range

options.Net = function()
--net here
settings().Physics.AllowSleep = false
settings().Physics.PhysicsEnvironmentalThrottle = Enum.EnviromentalPhysicsThrottle.Disabled
for i,v in next, game:GetService("Players").LocalPlayer.Character:GetDescendants() do
   if v:IsA("BasePart") and v.Name ~="HumanoidRootPart" then
       game:GetService("RunService").Heartbeat:connect(function()
           v.Velocity = Vector3.new(35,0,0)
       end)
   end
end
end




loadstring(game:HttpGet("https://raw.githubusercontent.com/saucekid/sauceVR/main/extra/ROrilla.lua"))();
```
