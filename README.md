# Tom's Dotfiles & System Setup

Private documentation of my Linux environment and dotfiles.

---

## 🖥️ System Setup

- **OS:** CachyOS (Arch-based)
- **DE:** KDE Plasma
- **Terminal:** Kitty
- **Shell:** Fish + [Tide Prompt](https://github.com/IlanCosman/tide)
- **VPN:** NordVPN (with subnet whitelist for KDE Connect)
- **File Transfer:** KDE Connect + SSHFS

---

## 📂 Included Dotfiles

- `~/.config/fish/` – Fish Shell + Tide Prompt
- `~/.config/kitty/` – Kitty Terminal
- Optional:
  - `~/.gitconfig`
  - other configurations

---

## ⚡ Setup Steps

### 1️⃣ KDE Connect & VPN Configuration

1. **Configure UFW for KDE Connect**
```bash
sudo ufw allow 1714:1764/tcp
sudo ufw allow 1714:1764/udp
sudo ufw reload
```

2. **Whitelist local subnet for NordVPN**
```bash
nordvpn whitelist add subnet 192.168.xx.xx/24
```

---

### 2️⃣ SSHFS for Dolphin

KDE Connect requires SSHFS for browsing the phone in Dolphin:

```bash
sudo pacman -S sshfs
```

Then restart Dolphin → the phone should be browsable via KDE Connect.

---

### 4️⃣ Useful Test Commands

- List all visible devices:
```bash
kdeconnect-cli --list-available
```
- Test ping to the phone:
```bash
ping 192.168.xx.xxx
```
