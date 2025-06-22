🪟 Windows Fresh Install Setup Guide
This is my personal method for configuring a clean Windows installation with useful tools, privacy tweaks, and AI access bypass. Steps are organized in the proper order.

✅ 1. Basic Setup
🌐 Install Browser
Download and install Chrome — the first thing you’ll need:

Download Chrome

📝 Better Notepad
Replace the default Windows Notepad with a modern alternative:

Notepads by 0x7c13

📦 Install Office
Get Microsoft Office from:

Download Microsoft Office

🔓 Activate Windows & Office
Use Microsoft Activation Scripts (MAS):

powershell
Copy
Edit
irm https://get.activated.win | iex
🌐 2. VPN & Geo-unblocking
🛡️ Cloudflare WARP (Russian Route Bypass)
Use this to bypass geo-blocks via WARP.

Generate config with this script:

bash-warp-generator

Use with:

Amnezia WireGuard Client

Important: Set the following in your WireGuard config:

nginx
Copy
Edit
AllowedIPs = 0.0.0.0/32, 8.8.4.0/24, 8.8.8.0/24, ...
Or generate a specific range here:

IP Ranges Tool

🤖 3. AI & DNS Bypass
🧠 AI DNS Unblock with YogaDNS
Install YogaDNS (free):

YogaDNS 1.21 Beta

Add a custom DoH server:

makefile
Copy
Edit
Type: DoH  
IP: 176.99.11.77  
URL: https://xbox-dns.ru/dns-query
Personal blocklist for this DoH (add manually):

Copy
Edit
aistudio.google.com  
alkalimakersuite-pa.clients6.google.com  
waa-pa.clients6.google.com  
🔒 Global DoH DNS for Most AI Services
If you prefer a trusted setup:

Comss Trusted DNS

Direct DoH: https://router.comss.one/dns-query

🛠️ 4. Developer Tools
🧑‍💻 Visual Studio Code
Download VS Code

🔐 OpenRouter AI Access
Create an account at openrouter.ai

Download the roocode extension for VS Code.

🎵 5. Media & Streaming
🎧 Spotify (Ad-Free)
Block Spotify ads:

BlockTheSpot

🌍 Bypass Spotify Premium with Hola VPN
Hola VPN Chrome Extension

Log in from India every 2 weeks to keep free Premium.

📁 6. Torrents & Games
📦 qBittorrent
Download qBittorrent

🎮 Game Resources
SteamRIP

Hydra Launcher (GitHub)
