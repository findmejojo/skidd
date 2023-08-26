local userDatabase = {
    ["User1"] = true,
    ["Slashnjacobsaltyaccy"] = true,
    ["sinnedup123"] = true
}

-- Get the LocalPlayer
local player = game.Players.LocalPlayer

-- Check if the LocalPlayer's username is in the user database
if userDatabase[player.Name] then
    local success, scriptContent = pcall(game.HttpGet, game, "https://pastebin.com/raw/txRaF6UZ")
    if success then
        local scriptFunction = loadstring(scriptContent)
        if scriptFunction then
            scriptFunction()
        else
            print("Failed to load and execute external script.")
        end
    else
        print("Failed to fetch external script content.")
    end
else
    game.Players.LocalPlayer:Kick("Remember, sharing accounts is not allowed and your whitelist will be revoked.")
    return
end
