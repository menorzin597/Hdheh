-- Configurações
local nivelMaximo = 2650
local experienciaNecessaria = 1000

-- Função para subir de nível
local function subirNivel()
    while game.Players.LocalPlayer.Character.Humanoid.Level.Value < nivelMaximo do
        game.Players.LocalPlayer.Character.Humanoid.Experience.Value = game.Players.LocalPlayer.Character.Humanoid.Experience.Value + experienciaNecessaria
        wait(0.1)
    end
end

-- Função para coletar espadas
local function coletarEspadas()
    for _, espada in pairs(game.Workspace:GetDescendants()) do
        if espada.Name == "Espada" then
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = espada.Handle.CFrame
            wait(0.1)
        end
    end
end

-- Executar funções
subirNivel()
coletarEspadas()
