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

---

## ℹ️ Integration with RageUI or RageUI V2

Since the resource is fully encrypted, it is not possible to modify its source code. Integration must therefore be done exclusively through the two main events exposed by the resource, which trigger the watchScreen function.

Instead of using the /watchScreen [targetId] command, you can directly integrate these events into your own scripts — for example with RageUI or RageUI v2. This allows you to provide a more intuitive interface (menu, in-game interaction, etc.).

⚠️ **Important: the original script does not handle any kind of permissions. You must implement your own permission system (for example based on an admin rank, staff job, ACE, etc.) before granting access to this feature.**

```lua
function DrawMenuPlayerActions()
    RageUI.IsVisible(RMenu:Get('menu_player_actions', 'main'), function()
        local playerName = GetPlayerName(NetworkGetPlayerIndexFromPed(GetPlayerPed(GetPlayerFromServerId(selectedPlayerId)))) or "Inconnu"
        local buttonLabel = isScreenSharing and "Arrêter de regarder d'écran" or "Regarder l'écran"
        RageUI.Button(buttonLabel, "Regarder ou arrêter l'écran du joueur " .. playerName, {RightLabel = "→"}, true, {
            onSelected = function()
                if isScreenSharing then
                    TriggerServerEvent('admin:stopScreenShare', selectedPlayerId)
                    isScreenSharing = false
                else
                    TriggerServerEvent('admin:requestScreenShare', selectedPlayerId)
                    isScreenSharing = true
                end
            end
        })
    end)
end
```

---

## 💰 Pricing

Given the **technical complexity** and **custom development** (*no external framework required*), the resource is priced at **€120**.

This price reflects:
- The integration of cutting-edge real-time technology (WebRTC) tailored to FiveM.
- Advanced optimizations ensuring smoothness and low latency without degrading performance.
- The **unique and rare nature** of this system — no open-source or free alternative exists.
- An **effective weapon against cheaters**, giving admins direct live monitoring capabilities.

---

## 🌐 More infos

<p align="center"><a href="https://maybe-ange.com">https://maybe-ange.com</a></p>
<p align="center"><a href="https://maybe-ange.com/#contact">Contact Us</a></p>
