-- Sistema de múltiplas keys funcional (client-side)
-- Coloque no seu executor (KRNL, Fluxus, etc)

-- Lista de keys válidas
local keysValidas = {
    "itachi",
    "hollyisback",
    "DISTANCIA777",
    "ESPON",
    "CHATGPTTOP"
}

-- Função para verificar se a key existe
local function isKeyValida(key)
    for _, k in pairs(keysValidas) do
        if key == k then
            return true
        end
    end
    return false
end

-- UI para digitar a key
local sg = Instance.new("ScreenGui", game.CoreGui)
local frame = Instance.new("Frame", sg)
frame.Size = UDim2.new(0, 300, 0, 150)
frame.Position = UDim2.new(0.5, -150, 0.5, -75)
frame.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
frame.BorderSizePixel = 0

local titulo = Instance.new("TextLabel", frame)
titulo.Size = UDim2.new(1, 0, 0.2, 0)
titulo.Position = UDim2.new(0, 0, 0, 0)
titulo.BackgroundTransparency = 1
titulo.Text = "🔐 Sistema de Key"
titulo.TextColor3 = Color3.new(1,1,1)
titulo.Font = Enum.Font.GothamBold
titulo.TextSize = 20

local txtBox = Instance.new("TextBox", frame)
txtBox.Size = UDim2.new(0.8, 0, 0.3, 0)
txtBox.Position = UDim2.new(0.1, 0, 0.3, 0)
txtBox.PlaceholderText = "Digite sua Key aqui"
txtBox.Text = ""
txtBox.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
txtBox.TextColor3 = Color3.new(1,1,1)
txtBox.BorderSizePixel = 0

local btn = Instance.new("TextButton", frame)
btn.Size = UDim2.new(0.6, 0, 0.25, 0)
btn.Position = UDim2.new(0.2, 0, 0.7, 0)
btn.Text = "Verificar"
btn.BackgroundColor3 = Color3.fromRGB(0, 120, 255)
btn.TextColor3 = Color3.new(1, 1, 1)
btn.Font = Enum.Font.Gotham
btn.TextSize = 18

local status = Instance.new("TextLabel", frame)
status.Size = UDim2.new(1, 0, 0.2, 0)
status.Position = UDim2.new(0, 0, 0.8, 0)
status.BackgroundTransparency = 1
status.Text = ""
status.TextColor3 = Color3.new(1, 1, 1)
status.Font = Enum.Font.Gotham
status.TextSize = 14

-- Lógica de verificação
btn.MouseButton1Click:Connect(function()
    local keyDigitada = txtBox.Text
    if isKeyValida(keyDigitada) then
        status.Text = "✅ Key válida. Carregando script..."
        wait(1.5)
        sg:Destroy()

        -- Coloque seu script aqui (pode ser link externo)
        loadstring(game:HttpGet("https://raw.githubusercontent.com/sillageeee/espzao/refs/heads/main/README.md"))()
    else
        status.Text = "❌ Key inválida. Tente novamente."
    end
end)
