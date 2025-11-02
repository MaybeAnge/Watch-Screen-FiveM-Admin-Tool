# 🎥 Watch Screen – FiveM Admin Tool
Live screen viewing in FiveM for administrators, enabling **real-time observation** of a player’s gameplay for RP moderation and anti-cheat purposes.

---

## 📹 Demonstration

<p align="center">
  <a href="https://youtu.be/FAlQM9gc0AI">
    <img src="https://img.youtube.com/vi/FAlQM9gc0AI/0.jpg" alt="Vidéo YouTube" width="480"/>
  </a>
</p>

## 📹 Demonstration V2 In Prod

<p align="center">
  <a href="https://youtu.be/QAnAt_eD2yQ">
    <img src="https://img.youtube.com/vi/QAnAt_eD2yQ/0.jpg" alt="Vidéo YouTube" width="480"/>
  </a>
</p>

---

## 🛠 Description

**Watch Screen** is an **advanced FiveM resource** that allows administrators to see a player’s screen **live**, directly from the game, using **WebRTC** technology.

Unlike delayed screenshot tools or external solutions such as *screenshot-basic*, this system offers:
- **Instant visibility** of the player’s POV.
- **Ultra-low latency** streaming.
- **Integration directly into the game world** for maximum immersion and practicality.

```lua
if playerPower >= 200 then
    local playerName = GetPlayerName(NetworkGetPlayerIndexFromPed(GetPlayerPed(GetPlayerFromServerId(selectedPlayer)))) or "Inconnu"
    local buttonLabel = isScreenSharing and "Arrêter de regarder d'écran" or "Regarder l'écran"
    RageUI.Button(buttonLabel, nil, {}, true, {
        onSelected = function()
            if isScreenSharing then
                TriggerServerEvent('admin:stopScreenShare', selectedPlayer)
                isScreenSharing = false
            else
                TriggerServerEvent('admin:requestScreenShare', selectedPlayer)
                isScreenSharing = true
            end
        end
    })
end
```
