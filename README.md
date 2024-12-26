
```
-- Configurações
local infinitoDinheiro = true
local veiculosGratuitos = true
local velocidadeJogo = 2

-- Serviços
local Players = game:GetService("Players")
local player = Players.LocalPlayer

-- Dinheiro infinito
if infinitoDinheiro then
    while true do
        player.leaderstats.Money.Value = 999999999
        wait(1)
    end
end

-- Veículos gratuitos
if veiculosGratuitos then
    local veiculos = game:GetService("Workspace"):WaitForChild("Vehicles")
    for _, veiculo in pairs(veiculos:GetChildren()) do
        if veiculo:IsA("Model") then
            veiculo.Price.Value = 0
        end
    end
end

-- Velocidade do jogo
if velocidadeJogo > 1 then
    game:GetService("RunService").RenderStepped:Connect(function()
        game:GetService("Workspace").SimulationSpeed = velocidadeJogo
    end)
end
```
