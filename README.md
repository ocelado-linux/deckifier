# deckifier (Ocelado Linux)

Game Mode / Desktop Mode switching for gamescope-session, as used by
[Ocelado Linux](https://github.com/ocelado-linux) (SteamOS-like openSUSE
Tumbleweed for handhelds). Packaged on OBS:
`home:Luthenis:ogc-handheld/deckifier`.

Fork of [YugaLinux/deckifier](https://github.com/YugaLinux/deckifier) at
5624f905. Ocelado changes, one commit each:

- SDDM instead of LightDM: `steamos-session-select` sets the SDDM autologin
  session through a root helper (`steamos-polkit-helpers/steamos-set-autologin`,
  pkexec) and ends the session; SDDM `Relogin=true` logs into the new one
- autologin user detected at runtime instead of the hardcoded `deck`
- generic `steamos-polkit-helpers` for handhelds other than the Steam Deck
- trup: update check with `zypper dup --dry-run`
- Return to Gaming Mode: single instance, no `loginctl terminate-session`,
  Steam game shortcuts kept

---

Upstream:

A script for gamescope-session on Yuga Linux

Based on https://github.com/lostalejandro/deckifier

Also contains bits of https://github.com/ChimeraOS/gamescope-session-steam
