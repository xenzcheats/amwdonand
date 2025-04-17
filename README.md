-- Defina sua chave aqui
local requiredKey = "xenzhub123"

-- Interface de verificação
local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/zxciaz/VenyxUI/main/Reuploaded"))()
local venyxKey = library.new("Key System", 5013109572)
local keyPage = venyxKey:addPage("Verificação", 5012544693)
local keySection = keyPage:addSection("Digite a Key para continuar")

local userKey = ""

keySection:addTextbox("Insira a Key", "Digite aqui...", function(value)
    userKey = value
end)

keySection:addButton("Verificar Key", function()
    if userKey == requiredKey then
        venyxKey:Notify("Sucesso", "Key correta! Carregando script...")
        venyxKey:toggle()

        -- Aguarda a UI desaparecer
        wait(0.5)

        -- Agora carrega seu script principal (ESP + Aimbot)
        loadstring(game:HttpGet("https://raw.githubusercontent.com/xenzcheats/KMAMWD0MAWO/refs/heads/main/README.md"))()

    else
        venyxKey:Notify("Erro", "Key incorreta!")
    end
end)

venyxKey:SelectPage(venyxKey.pages[1], true)
