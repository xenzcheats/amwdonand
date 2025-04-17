-- Lista de keys válidas
local validKeys = {
    "xenzhub123",
    "itachi"
}

-- Verifica se a key existe na lista
local function isKeyValid(key)
    for _, k in pairs(validKeys) do
        if k == key then
            return true
        end
    end
    return false
end

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
    if isKeyValid(userKey) then
        venyxKey:Notify("Sucesso", "Key correta! Carregando script...")
        venyxKey:toggle()

        wait(0.5)

        -- Carrega seu script principal aqui
        loadstring(game:HttpGet("https://raw.githubusercontent.com/xenzcheats/KMAMWD0MAWO/refs/heads/main/README.md"))()
    else
        venyxKey:Notify("Erro", "Key incorreta!")
    end
end)

venyxKey:SelectPage(venyxKey.pages[1], true)
