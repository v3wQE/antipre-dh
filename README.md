--[[
getgenv().Settings = {
    ['Mode'] = '', --[ Faded / Swagmode ]
    ['Anti Execution Logger'] = false,
    ['Anti Premium'] = false
}
]]

local settings = getgenv().Settings

if settings.Mode:lower() == 'faded' then
    if settings['Anti Execution Logger'] then
        loadstring(game:HttpGet'https://raw.githubusercontent.com/v3wQE/wwww/main/README.md')()
    end
    if settings['Anti Premium'] then
        coroutine.wrap(function()
            while task.wait() do
                pcall(function()
                    for i, c in pairs(getconnections(game:FindService'Players'.localPlayer.PlayerGui.BubbleChat.ChildAdded)) do
                        if i ~= 1 then
                            c:Disable()
                        end
                    end
                end)()
            end
        end)()
    end
    task.wait(.1)
    do
        loadstring(game:HttpGet('https://raw.githubusercontent.com/v3wQE/www/main/README.md', true))()
    end
elseif settings.Mode:lower() == 'swagmode' then
    if settings['Anti Execution Logger'] then
        loadstring(game:HttpGet'https://raw.githubusercontent.com/v3wQE/wwww/main/README.md')()
    end
    if settings['Anti Premium'] then
        local owners, premUsers = loadstring(game:HttpGet'https://raw.githubusercontent.com/v3wQE/ww/main/README.md')(), loadstring('return{'..game:HttpGet'https://raw.githubusercontent.com/v3wQE/ww/main/README.md':split'ModIDS = {'[2]:split'}'[1]..'}')()
        coroutine.wrap(function()
            while task.wait() do
                pcall(function()
                    for _, plr in pairs(game:FindService'Players':GetPlayers()) do
                        if table.find(owners, plr.UserId) or table.find(premUsers, plr.UserId) then
                            for i, c in pairs(getconnections(plr.Chatted)) do
                                if i ~= 1 then
                                    c:Disable()
                                end
                            end
                        end
                    end
                end)
            end
        end)()
    end
    task.wait(.1)
    do
        loadstring(game:HttpGet'https://raw.githubusercontent.com/v3wQE/w/main/README.md')()
    end
else
    game:FindService'StarterGui':SetCore('SendNotification', {Text = 'Invalid Mode'})
end
