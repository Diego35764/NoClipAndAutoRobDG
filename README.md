local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local noclipEnabled = true

-- Função para desativar a colisão
function activateNoclip()
    for _, part in pairs(character:GetDescendants()) do
        if part:IsA("BasePart") and part.CanCollide then
            part.CanCollide = false
        end
    end
end

-- Atualiza o estado do noclip a cada tick
game:GetService("RunService").Stepped:Connect(function()
    if noclipEnabled then
        activateNoclip()
    end
end)
loadstring(game:HttpGet("https://raw.githubusercontent.com/Diego35764/DgDiego/refs/heads/main/README.md"))()
