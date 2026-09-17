# 🎥 Watch Screen – FiveM Admin Tool
Live screen viewing in FiveM for administrators, enabling **real-time observation** of a player’s gameplay for RP moderation and anti-cheat purposes.

---

## 📹 Demonstration

<p align="center">
  <a href="https://youtu.be/NlZDExWIMPs">
    <img src="https://img.youtube.com/vi/NlZDExWIMPs/0.jpg" alt="Vidéo YouTube" width="480"/>
  </a>
</p>

More information and purchase: https://discord.com/invite/YcBngexpjr

---

## 🛠 Description

**Watch Screen** is an **advanced FiveM resource** that allows administrators to see a player’s screen **live**, directly from the game, using **WebRTC** technology.

Unlike delayed screenshot tools or external solutions such as *screenshot-basic*, this system offers:
- Performance: The script runs at 0.00 ms, even in action.
- Security & Discretion: 0% chance of detection by cheaters zero possibility for them to know you are watching them.
- Compatibility: Works on all frameworks (Standalone, ESX, QBCore, etc.) utilizing ACE permissions.
- Display: 30 FPS real-time stream. RageUI-style cheats or in-game integrations like DrawText are visible. External cheats like Susano (which use other methods outside the game itself) will not be visible, but everything the cheaters do such as NoClip, Freecam, Aimbot, and much more will be fully visible.

```lua
RageUI.Button("Watch Player Screen", "Look at the target player's screen.", {}, true, {
    onSelected = function()
        TriggerServerEvent('inw:toggle', playerSessionID)
    end
})
```
