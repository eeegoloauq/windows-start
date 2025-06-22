# Windows Setup Guide

This guide outlines my personal process for customizing and setting up a clean Windows installation.

## 1. Windows Installation

If Windows is not yet installed, I highly recommend using [Rufus](https://rufus.ie/en/) for creating a bootable USB drive. When installing, choose a local user account and skip the Microsoft account login.

For a specific Windows 11 Enterprise LTSC 2024 x64 ISO, you can find a torrent link here: [en-us_windows_11_enterprise_ltsc_2024_x64_dvd_965cfb00.iso [Torrent] [4.77 ГБ, EN-US, install.wim]](https://www.comss.ru/download/page.php?id=13359). During installation, select the LTSC N version to avoid pre-installed Microsoft programs, except for Edge.

## 2. Essential Software

*   **Google Chrome:** Download from [https://www.google.com/chrome/](https://www.google.com/chrome/)
*   **Custom Notepad:** [Notepads](https://github.com/0x7c13/Notepads)
*   **Microsoft Office:** Download from [https://www.microsoft.com/en-us/microsoft-365/download-office](https://www.microsoft.com/en-us/microsoft-365/download-office)
*   **qBittorrent:** Download from [https://www.qbittorrent.org/download](https://www.qbittorrent.org/download)

## 3. Activation (Windows and Office)

For Windows and Office activation, you can use the Microsoft Activation Scripts. More information can be found on their GitHub page: [https://github.com/massgravel/Microsoft-Activation-Scripts](https://github.com/massgravel/Microsoft-Activation-Scripts). A common method is to run the following command in PowerShell:
```powershell
irm https://get.activated.win | iex
```

## 4. Bypassing Geo-Restrictions and AI Blocks

### Cloudflare VPN (for bypassing geo-blocks)

1.  Generate a WARP configuration using [bash-warp-generator](https://github.com/ImMALWARE/bash-warp-generator).
2.  Download and install the [AmneziaWG Windows Client](https://github.com/amnezia-vpn/amneziawg-windows-client/releases).
3.  Import the generated WARP configuration into AmneziaWG.
4.  **Important:** You may need to adjust the `AllowedIPs` in the configuration to include specific IP ranges you need to bypass. A comprehensive list can be found here: [https://rockblack.su/vpn/dopolnitelno/diapazon-ip-adresov](https://rockblack.su/vpn/dopolnitelno/diapazon-ip-adresov).

### Bypassing AI Blocks

1.  Download and install [YogaDNS 1.21b (free)](https://www.comss.ru/download/page.php?id=7734).
2.  Set up a new DNS server in YogaDNS with the following details:
    *   Type: DOH
    *   IP: `176.99.11.77`
    *   URL: `https://xbox-dns.ru/dns-query`
3.  **Optional:** You can add specific rules to this DOH server for services like Google AI:
    *   `aistudio.google.com`
    *   `alkalimakersuite-pa.clients6.google.com`
    *   `waa-pa.clients6.google.com`
4.  For other AI services, you can use the trusted DNS server from [https://www.comss.ru/page.php?id=7315](https://www.comss.ru/page.php?id=7315) (`https://router.comss.one/dns-query`).

## 5. Development Tools

*   **Visual Studio Code (VSC):** Download from [https://code.visualstudio.com/download](https://code.visualstudio.com/download). After installing, you can download the RooCode extension and log in to [https://openrouter.ai/](https://openrouter.ai/).

## 6. Entertainment

*   **Spotify Ad Blocker:** Use [BlockTheSpot](https://github.com/mrpond/BlockTheSpot) to block ads on Spotify.
*   **Hola VPN (for Spotify Premium):** Use the [Hola VPN Chrome extension](https://chromewebstore.google.com/detail/hola-vpn-your-website-unb/gkojfkhlekighikafcpjkiklfbnlmeio?hl=ru) to log in from India every two weeks to potentially access free premium features.
*   **Games:** Check out [steamrip.com](https://steamrip.com/) and [Hydra Launcher](https://github.com/hydralauncher/hydra).
