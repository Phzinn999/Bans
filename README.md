-- Interface do Script
local ScreenGui = Instance.new("ScreenGui")
local MinimizeButton = Instance.new("TextButton")
local ScrollingFrame = Instance.new("ScrollingFrame")
local Title = Instance.new("TextLabel")
local ESPButton = Instance.new("TextButton")
local SpeedHackButton = Instance.new("TextButton")
local CollectRareItemsButton = Instance.new("TextButton")
local SpeedSlider = Instance.new("TextBox")
local InstantKillButton = Instance.new("TextButton")

-- Propriedades da Interface
ScreenGui.Parent = game.CoreGui

MinimizeButton.Parent = ScreenGui
MinimizeButton.BackgroundColor3 = Color3.fromRGB(70, 70, 70)
MinimizeButton.Position = UDim2.new(0.05, 0, 0.05, 0)
MinimizeButton.Size = UDim2.new(0, 50, 0, 50)
MinimizeButton.Font = Enum.Font.SourceSans
MinimizeButton.Text = "O"
MinimizeButton.TextColor3 = Color3.fromRGB(255, 255, 255)
MinimizeButton.TextSize = 24

ScrollingFrame.Parent = ScreenGui
ScrollingFrame.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
ScrollingFrame.Position = UDim2.new(0.1, 0, 0.1, 0)
ScrollingFrame.Size = UDim2.new(0, 300, 0, 400)
ScrollingFrame.CanvasSize = UDim2.new(0, 0, 1.5, 0) -- Ajuste o valor conforme necessário
ScrollingFrame.ScrollBarThickness = 10
ScrollingFrame.Visible = false

Title.Parent = ScrollingFrame
Title.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
Title.Size = UDim2.new(1, 0, 0, 50)
Title.Font = Enum.Font.SourceSans
Title.Text = "Script Menu"
Title.TextColor3 = Color3.fromRGB(255, 255, 255)
Title.TextSize = 24

ESPButton.Parent = ScrollingFrame
ESPButton.BackgroundColor3 = Color3.fromRGB(70, 70, 70)
ESPButton.Position = UDim2.new(0, 0, 0.2, 0)
ESPButton.Size = UDim2.new(1, 0, 0, 50)
ESPButton.Font = Enum.Font.SourceSans
ESPButton.Text = "ESP (Ver Jogadores)"
ESPButton.TextColor3 = Color3.fromRGB(255, 255, 255)
ESPButton.TextSize = 20

SpeedHackButton.Parent = ScrollingFrame
SpeedHackButton.BackgroundColor3 = Color3.fromRGB(70, 70, 70)
SpeedHackButton.Position = UDim2.new(0, 0, 0.35, 0)
SpeedHackButton.Size = UDim2.new(1, 0, 0, 50)
SpeedHackButton.Font = Enum.Font.SourceSans
SpeedHackButton.Text = "Speed Hack"
SpeedHackButton.TextColor3 = Color3.fromRGB(255, 255, 255)
SpeedHackButton.TextSize = 20

SpeedSlider.Parent = ScrollingFrame
SpeedSlider.BackgroundColor3 = Color3.fromRGB(70, 70, 70)
SpeedSlider.Position = UDim2.new(0, 0, 0.45, 0)
SpeedSlider.Size = UDim2.new(1, 0, 0, 50)
SpeedSlider.Font = Enum.Font.SourceSans
SpeedSlider.Text = "Digite a Velocidade"
SpeedSlider.TextColor3 = Color3.fromRGB(255, 255, 255)
SpeedSlider.TextSize = 20

CollectRareItemsButton.Parent = ScrollingFrame
CollectRareItemsButton.BackgroundColor3 = Color3.fromRGB(70, 70, 70)
CollectRareItemsButton.Position = UDim2.new(0, 0, 0.6, 0)
CollectRareItemsButton.Size = UDim2.new(1, 0, 0, 50)
CollectRareItemsButton.Font = Enum.Font.SourceSans
CollectRareItemsButton.Text = "Coletar Itens Raros"
CollectRareItemsButton.TextColor3 = Color3.fromRGB(255, 255, 255)
CollectRareItemsButton.TextSize = 20

InstantKillButton.Parent = ScrollingFrame
InstantKillButton.BackgroundColor3 = Color3.fromRGB(70, 70, 70)
InstantKillButton.Position = UDim2.new(0, 0, 0.75, 0)
InstantKillButton.Size = UDim2.new(1, 0, 0, 50)
InstantKillButton.Font = Enum.Font.SourceSans
InstantKillButton.Text = "Morte Instantânea"
InstantKillButton.TextColor3 = Color3.fromRGB(255, 255, 255)
InstantKillButton.TextSize = 20

-- Função para minimizar e maximizar a interface
MinimizeButton.MouseButton1Click:Connect(function()
    ScrollingFrame.Visible = not ScrollingFrame.Visible
    MinimizeButton.Text = ScrollingFrame.Visible and "-" or "O"
end)

-- Função para conceder acesso premium ao jogador
local function concederAcessoPremium(jogador)
    -- Conceder acesso a todos os recursos premium
    print(jogador.Name .. " tem acesso premium!")
    -- Adicione aqui os recursos premium que você deseja conceder
    -- Exemplo: jogador:GiveTool(game.ServerStorage.PremiumTool)
end

-- Conectar a função ao evento de jogador adicionado
game.Players.PlayerAdded:Connect(function(jogador)
    -- Simular que o jogador tem assinatura premium
    jogador.MembershipType = Enum.MembershipType.Premium
    concederAcessoPremium(jogador)
end)
