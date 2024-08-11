-- Obfuscated Script

_G["\72\101\97\100\83\105\122\101"] = 3.5
_G["\68\105\115\97\98\108\101\100"] = true

local A, B, C, D = game:GetService("\85\115\101\114\73\110\112\117\116\83\101\114\118\105\99\101"), game:GetService("\82\117\110\83\101\114\118\105\99\101"), game:GetService("\80\108\97\121\101\114\115"), game:GetService("\80\108\97\121\101\114\115")["\76\111\99\97\108\80\108\97\121\101\114"]

local E = Instance.new("\83\99\114\101\101\110\71\117\105")
E["\80\97\114\101\110\116"] = game.CoreGui

local F = Instance.new("\70\114\97\109\101")
F["\83\105\122\101"] = UDim2.new(0, 200, 0, 150)
F["\80\111\115\105\116\105\111\110"] = UDim2.new(0, 10, 0, 10)
F["\66\97\99\107\103\114\111\117\110\100\67\111\108\111\114\51"] = Color3.new(0.1, 0.1, 0.1)
F["\86\105\115\105\98\108\101"] = false
F["\80\97\114\101\110\116"] = E

local G = Instance.new("\84\101\120\116\66\117\116\116\111\110")
G["\83\105\122\101"] = UDim2.new(0, 180, 0, 50)
G["\80\111\115\105\116\105\111\110"] = UDim2.new(0, 10, 0, 10)
G["\84\101\120\116"] = "\84\111\103\103\108\101\32\104\101\97\100"
G["\80\97\114\101\110\116"] = F

local H = Instance.new("\84\101\120\116\76\97\98\101\108")
H["\83\105\122\101"] = UDim2.new(0, 180, 0, 30)
H["\80\111\115\105\116\105\111\110"] = UDim2.new(0, 10, 0, 70)
H["\84\101\120\116"] = "\72\101\97\100\32\83\105\122\101\58\32" .. _G["\72\101\97\100\83\105\122\101"]
H["\80\97\114\101\110\116"] = F

local I = Instance.new("\84\101\120\116\66\117\116\116\111\110")
I["\83\105\122\101"] = UDim2.new(0, 180, 0, 30)
I["\80\111\115\105\116\105\111\110"] = UDim2.new(0, 10, 0, 110)
I["\84\101\120\116"] = "\65\100\106\117\115\116\32\72\101\97\100\32\83\105\122\101"
I["\80\97\114\101\110\116"] = F

A.InputBegan:Connect(function(J, K)
    if not K and J.KeyCode == Enum.KeyCode.K then
        F.Visible = not F.Visible
    end
end)

G.MouseButton1Click:Connect(function()
    _G["\68\105\115\97\98\108\101\100"] = not _G["\68\105\115\97\98\108\101\100"]
end)

I.MouseButton1Click:Connect(function()
    if _G["\72\101\97\100\83\105\122\101"] < 25 then
        _G["\72\101\97\100\83\105\122\101"] = _G["\72\101\97\100\83\105\122\101"] + 0.5
    else
        _G["\72\101\97\100\83\105\122\101"] = 0.5
    end
    H["\84\101\120\116"] = "\72\101\97\100\32\83\105\122\101\58\32" .. _G["\72\101\97\100\83\105\122\101"]
end)

B.RenderStepped:Connect(function()
    if not _G["\68\105\115\97\98\108\101\100"] then
        for L, M in next, C:GetPlayers() do
            if M ~= D then
                pcall(function()
                    if M.Character and M.Character:FindFirstChild("\72\101\97\100") then
                        M.Character.Head.Size = Vector3.new(_G["\72\101\97\100\83\105\122\101"], _G["\72\101\97\100\83\105\122\101"], _G["\72\101\97\100\83\105\122\101"])
                        M.Character.Head.Transparency = 0.4
                        M.Character.Head.BrickColor = BrickColor.new("\82\101\100")
                        M.Character.Head.Material = "\78\101\111\110"
                        M.Character.Head.CanCollide = false
                        M.Character.Head.Massless = true
                    end
                end)
            end
        end
    end
end)

local N = {}

function N.Create(O)
    if O == D then return end
    if N[O] then return end

    local P = O.Character
    if P and P:IsDescendantOf(workspace) and P:FindFirstChild("\72\117\109\97\110\111\105\100") and P.Humanoid.Health > 0 then
        local Q = Drawing.new("\83\113\117\97\114\101")
        Q.Visible = false
        Q.Color = Color3.fromRGB(255, 255, 255)
        Q.Filled = false
        Q.Thickness = 1

        local R = Drawing.new("\83\113\117\97\114\101")
        R.Visible = false
        R.Color = Color3.fromRGB(0, 255, 0)
        R.Filled = true
        R.Thickness = 1

        local S
        S = B.RenderStepped:Connect(function()
            if P and P:IsDescendantOf(workspace) and P:FindFirstChild("\72\117\109\97\110\111\105\100") and P.Humanoid.Health > 0 then
                local T, U = workspace.CurrentCamera:WorldToViewportPoint(P.HumanoidRootPart.Position)
                local V = 1 / (T.Z * math.tan(math.rad(workspace.CurrentCamera.FieldOfView * 0.5)) * 2) * 100
                local W, X = math.floor(40 * V), math.floor(62 * V)

                if U then
                    Q.Size = Vector2.new(W, X)
                    Q.Position = Vector2.new(T.X - Q.Size.X / 2, T.Y - Q.Size.Y / 2)
                    Q.Visible = true

                    local Y = P.Humanoid.Health / P.Humanoid.MaxHealth
                    R.Size = Vector2.new(4, math.floor(X * Y))
                    R.Position = Vector2.new(Q.Position.X - 6, Q.Position.Y + (X - R.Size.Y))
                    R.Color = Color3.fromRGB(255 * (1 - Y), 255 * Y, 0)
                    R.Visible = true
                else
                    Q.Visible = false
                    R.Visible = false
                end
            else
                Q:Destroy()
                R:Destroy()
                S:Disconnect()
                N[O] = nil
            end
        end)

        N[O] = {
            ["\66\111\120"] = Q,
            ["\72\101\97\108\116\104\66\97\114"] = R,
            ["\67\111\110\110\101\99\116\105\111\110"] = S
        }
    end
end

local function Z()
    for _, O in pairs(C:GetPlayers()) do
        if O.Character then
            N.Create(O)
        end
    end
end

B.RenderStepped:Connect(Z)

C.PlayerRemoving:Connect(function(O)
    if N[O] then
        N[O].Box:Destroy()
        N[O].HealthBar:Destroy()
        N[O].Connection:Disconnect()
        N[O] = nil
    end
end)

D.CharacterAdded:Connect(function()
    if N[D] then
        N[D].Box:Destroy()
        N[D].Connection:Disconnect()
        N[D] = nil
    end
end)

local function _()
    if Drawing == nil then
        return "\78\111"
    else
        return "\89\101\115"
    end
end

local a = _()

if a == "\78\111" then
    game:GetService("\83\116\97\114\116\101\114\71\117\105"):SetCore("\83\101\110\100\78\111\116\105\102\105\99\97\116\105\111\110",{
        ["\84\105\116\108\101"] = "\69\120\117\110\121\115\32\68\101\118\101\108\111\112\101\114";
        ["\84\101\120\116"] = "\67\114\111\115\115\104\97\105\114\32\115\99\114\105\112\116\32\99\111\117\108\100\32\110\111\116\32\98\101\32\108\111\97\100\101\100\32\98\101\99\97\117\115\101\32\121\111\117\114\32\101\120\112\108\111\105\116\32\105\115\32\117\110\115\117\112\112\111\114\116\101\100\46";
        ["\68\117\114\97\116\105\111\110"] = math.huge;
        ["\66\117\116\116\111\110\49"] = "\79\75"
    })

    return
end

local b, c, d, e = game:GetService("\80\108\97\121\101\114\115"), game:GetService("\82\117\110\83\101\114\118\105\99\101"), game:GetService("\85\115\101\114\73\110\112\117\116\83\101\114\118\105\99\101"), workspace.CurrentCamera

local f = false

local g = e.ViewportSize / 2
local h, i = g.X, g.Y

local j = Drawing.new("\76\105\110\101")
local k = Drawing.new("\76\105\110\101")

_G["\83\101\110\100\78\111\116\105\102\105\99\97\116\105\111\110\115"] = true
_G["\68\101\102\97\117\108\116\83\101\116\116\105\110\103\115"] = false
_G["\84\111\77\111\117\115\101"] = false

_G["\67\114\111\115\115\104\97\105\114\86\105\115\105\98\108\101"] = true
_G["\67\114\111\115\115\104\97\105\114\83\105\122\101"] = 20
_G["\67\114\111\115\115\104\97\105\114\84\104\105\99\107\110\101\115\115"] = 1
_G["\67\114\111\115\115\104\97\105\114\67\111\108\111\114"] = Color3.fromRGB(255, 0, 0)
_G["\67\114\111\115\115\104\97\105\114\84\114\97\110\115\112\97\114\101\110\99\121"] = 1

_G["\68\105\115\97\98\108\101\75\101\121"] = Enum.KeyCode.Q

d.RenderStepped:Connect(function()
    local l = _G["\67\114\111\115\115\104\97\105\114\83\105\122\101"] / 2

    j.Color = _G["\67\114\111\115\115\104\97\105\114\67\111\108\111\114"]
    j.Thickness = _G["\67\114\111\115\115\104\97\105\114\84\104\105\99\107\110\101\115\115"]
    j.Visible = _G["\67\114\111\115\115\104\97\105\114\86\105\115\105\98\108\101"]
    j.Transparency = _G["\67\114\111\115\115\104\97\105\114\84\114\97\110\115\112\97\114\101\110\99\121"]
    
    k.Color = _G["\67\114\111\115\115\104\97\105\114\67\111\108\111\114"]
    k.Thickness = _G["\67\114\111\115\115\104\97\105\114\84\104\105\99\107\110\101\115\115"]
    k.Visible = _G["\67\114\111\115\115\104\97\105\114\86\105\115\105\98\108\101"]
    k.Transparency = _G["\67\114\111\115\115\104\97\105\114\84\114\97\110\115\112\97\114\101\110\99\121"]
    
    if _G["\84\111\77\111\117\115\101"] == true then
        j.From = Vector2.new(c:GetMouseLocation().X - l, c:GetMouseLocation().Y)
        j.To = Vector2.new(c:GetMouseLocation().X + l, c:GetMouseLocation().Y)
        
        k.From = Vector2.new(c:GetMouseLocation().X, c:GetMouseLocation().Y - l)
        k.To = Vector2.new(c:GetMouseLocation().X, c:GetMouseLocation().Y + l)
    elseif _G["\84\111\77\111\117\115\101"] == false then
        j.From = Vector2.new(h - l, i)
        j.To = Vector2.new(h + l, i)
    
        k.From = Vector2.new(h, i - l)
        k.To = Vector2.new(h, i + l)
    end
end)

if _G["\68\101\102\97\117\108\116\83\101\116\116\105\110\103\115"] == true then
    _G["\67\114\111\115\115\104\97\105\114\86\105\115\105\98\108\101"] = true
    _G["\67\114\111\115\115\104\97\105\114\83\105\122\101"] = 25
    _G["\67\114\111\115\115\104\97\105\114\84\104\105\99\107\110\101\115\115"] = 1
    _G["\67\114\111\115\115\104\97\105\114\67\111\108\111\114"] = Color3.fromRGB(40, 90, 255)
    _G["\67\114\111\115\115\104\97\105\114\84\114\97\110\115\112\97\114\101\110\99\121"] = 0.15
    _G["\68\105\115\97\98\108\101\75\101\121"] = Enum.KeyCode.Q
end

c.TextBoxFocused:Connect(function()
    f = true
end)

c.TextBoxFocusReleased:Connect(function()
    f = false
end)

c.InputBegan:Connect(function(Input)
    if Input.KeyCode == _G["\68\105\115\97\98\108\101\75\101\121"] and f == false then
        _G["\67\114\111\115\115\104\97\105\114\86\105\115\105\98\108\101"] = not _G["\67\114\111\115\115\104\97\105\114\86\105\115\105\98\108\101"]
        
        if _G["\83\101\110\100\78\111\116\105\102\105\99\97\116\105\111\110\115"] == true then
            game:GetService("\83\116\97\114\116\101\114\71\117\105"):SetCore("\83\101\110\100\78\111\116\105\102\105\99\97\116\105\111\110",{
                ["\84\105\116\108\101"] = "\69\120\117\110\121\115\32\68\101\118\101\108\111\112\101\114";
                ["\84\101\120\116"] = "\84\104\101\32\99\114\111\115\115\104\97\105\114\39\115\32\118\105\115\105\98\105\108\105\116\121\32\105\115\32\110\111\119\32\115\101\116\32\116\111\32"..tostring(_G["\67\114\111\115\115\104\97\105\114\86\105\115\105\98\108\101"])..".";
                ["\68\117\114\97\116\105\111\110"] = 5;
            })
        end
    end
end)
