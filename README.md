# VSCodium Arch Linux Binaries

Automated Arch Linux binary builds for VSCodium, built directly from official upstream releases and published via GitHub Releases.

No AUR.  
No pacman repo.  
No manual builds.

---

## 📦 Package

| Package | Description |
|----------|------------|
| codium | VSCodium built for Arch Linux |

Builds include:

- x86_64
- x86_64_v3 optimized builds (preferred)
- Built from official upstream tags
- Automatically released via GitHub Actions

---

# 🚀 Install / Update

```bash
curl -fLO https://raw.githubusercontent.com/Ravi-Kishor/vscodium/main/update-codium
chmod +x update-codium
sudo mv update-codium /usr/local/bin/update-codium
update-codium
```

---

## 🧠 What the updater does

- Checks installed version via pacman
- Fetches latest GitHub release
- Prefers x86_64_v3 build
- Falls back to generic x86_64
- Downloads and installs automatically

Interactive mode:
- Update only if newer
- Force reinstall

---

## 🏗 Build Info

- Built inside Arch container
- Stripped binaries
- Optimized for performance
- x86_64_v3 builds include AVX/FMA support

---

## ⚠ Requirements

Arch Linux only.

Requires:

- pacman
- curl
- jq
- sudo
