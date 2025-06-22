# 💻 Windows Setup Guide

This guide outlines my personal process for customizing and setting up a clean Windows installation.

## 💿 1. Windows Installation

If Windows is not yet installed, I highly recommend using [Rufus](https://rufus.ie/en/) for creating a bootable USB drive. When installing, choose a local user account and skip the Microsoft account login.

For a specific Windows 11 Enterprise LTSC 2024 x64 ISO, you can find a torrent link here: [en-us_windows_11_enterprise_ltsc_2024_x64_dvd_965cfb00.iso [Torrent] [4.77 ГБ, EN-US, install.wim]](https://comss.cloud/en-us_windows_11_enterprise_ltsc_2024_x64_dvd_965cfb00.iso.torrent). During installation, select the LTSC N version to avoid pre-installed Microsoft programs, except for Edge.


## ✨ 2. Essential Software

Here are some essential software installations using `winget`:

```powershell
# Install Windows Terminal
winget install Microsoft.WindowsTerminal -e --accept-source-agreements --accept-package-agreements
# Install Notepads
winget install "Notepads App"
# Install Google Chrome
winget install Google.Chrome -e --accept-source-agreements --accept-package-agreements
# Install Visual Studio Code
winget install Microsoft.VisualStudioCode -e --accept-source-agreements --accept-package-agreements
# Install Git
winget install Git.Git -e --accept-source-agreements --accept-package-agreements
# Install NVM for Windows
winget install -e --id CoreyButler.NVMforWindows
# Install Microsoft Office
winget install --id=Microsoft.Office  -e
# Install OBS Studio
winget install --id=OBSProject.OBSStudio  -e
# Install qBittorrent
winget install --id=qBittorrent.qBittorrent  -e

# Install and use Node.js version 24 using NVM
Start-Process -FilePath "cmd.exe" -ArgumentList "/k nvm i 24"
Start-Process -FilePath "cmd.exe" -ArgumentList "/k nvm use 24"
```

If winget isn't working because of the LTSC N version ('winget' is not recognized as an internal or external command, operable program or batch file.)
```powershell
wget "https://github.com/microsoft/winget-cli/releases/latest/download/Microsoft.DesktopAppInstaller_8wekyb3d8bbwe.msixbundle" -OutFile "$env:USERPROFILE\Downloads\winget.msixbundle"
Add-AppxPackage "$env:USERPROFILE\Downloads\winget.msixbundle"
```

## 🔑 3. Activation (Windows and Office)

**⚠️ Warning:** Running scripts directly from the internet can be risky. Ensure you trust the source before executing any commands.

For Windows and Office activation, you can use the Microsoft Activation Scripts. More information can be found on their GitHub page: [https://github.com/massgravel/Microsoft-Activation-Scripts](https://github.com/massgravel/Microsoft-Activation-Scripts). A common method is to run the following command in PowerShell:
```powershell
irm https://get.activated.win | iex
```

## 🌍 4. Bypassing Geo-Restrictions (e.g., for YouTube in Russia)

### 🛡️ Cloudflare VPN (for bypassing geo-blocks)

1.  Generate a WARP configuration using [bash-warp-generator](https://github.com/ImMALWARE/bash-warp-generator).
2.  Download and install the [AmneziaWG Windows Client](https://github.com/amnezia-vpn/amneziawg-windows-client/releases).
```powershell
wget "https://github.com/amnezia-vpn/amneziawg-windows-client/releases/download/1.0.2/amneziawg-amd64-1.0.2.msi" -OutFile "$env:TEMP\amneziawg.msi"
Start-Process "msiexec.exe" -ArgumentList "/i `"$env:TEMP\amneziawg.msi`" /quiet" -Wait
```
4.  Import the generated WARP configuration into AmneziaWG.
5.  **Important:** You may need to adjust the `AllowedIPs` in the configuration to include specific IP ranges you need to bypass. A comprehensive list can be found here: [https://rockblack.su/vpn/dopolnitelno/diapazon-ip-adresov](https://rockblack.su/vpn/dopolnitelno/diapazon-ip-adresov).

### 🤖 Bypassing AI Blocks in any country
1.  For most AI services, you can use the trusted DNS server from [https://www.comss.ru/page.php?id=7315](https://www.comss.ru/page.php?id=7315) (`https://router.comss.one/dns-query`) and set it up in your browser or router.
2.  Download and install [YogaDNS 1.21b (free)](https://www.comss.ru/download/page.php?id=7734).
3.  Set up a new DNS server (for aistudio.google.com) in YogaDNS with the following details:
    *   Type: DOH
    *   IP: `176.99.11.77`
    *   URL: `https://xbox-dns.ru/dns-query`
4.  **Optional:** You can add specific rules to this DOH server for services like Google AI:
    *   `aistudio.google.com`
    *   `alkalimakersuite-pa.clients6.google.com`
    *   `waa-pa.clients6.google.com`


## 🎮 5. Entertainment

*   🎵 **Spotify Ad Blocker:** Use [BlockTheSpot](https://github.com/mrpond/BlockTheSpot) to block ads on Spotify.
    ```powershell
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; Invoke-Expression "& { $(Invoke-WebRequest -UseBasicParsing 'https://raw.githubusercontent.com/mrpond/BlockTheSpot/master/install.ps1') } -UninstallSpotifyStoreEdition -UpdateSpotify"
    ```
*   🇮🇳 **Hola VPN (for Spotify Premium):** Use the [Hola VPN Chrome extension](https://chromewebstore.google.com/detail/hola-vpn-your-website-unb/gkojfkhlekighikafcpjkiklfbnlmeio?hl=ru) to log in spotify from India every two weeks to potentially access free premium features.
*   🎮 **Games:** Check out [steamrip.com](https://steamrip.com/) and [Hydra Launcher](https://github.com/hydralauncher/hydra).
