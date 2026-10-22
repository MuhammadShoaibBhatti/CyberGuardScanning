# CyberGuard Lab
Ethical cybersecurity dashboard for **authorized local-lab learning**. Metadata only: no payloads, passwords, cookies or tokens. Everything stays on your PC.

## Setup (Windows 10/11, PowerShell)
1. Install Python 3.12 and **Npcap** (https://npcap.com, tick "WinPcap API-compatible mode").
2. Run:
```
py -3.12 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
python main.py
```
Live capture needs PowerShell **Run as Administrator**. The app still opens without it.

## Roman Urdu (asaan steps)
1. Python 3.12 aur Npcap install karein.
2. Folder mein PowerShell kholein (Capture ke liye "Run as administrator").
3. Upar wali 5 commands ek ek karke chalayein.
4. App khulne ke baad "Network Sniffer" mein interface chunein, seconds likhein, Start dabayein.
5. Reports page se CSV/JSON/PDF export karein. Sirf apne ya authorized network par use karein.

## Port Scanner (pro)
Pick **Port Scanner**, enter a private IP (e.g. 127.0.0.1 or 192.168.1.1), choose Common / 1-1024 / Custom and press Scan. Public IPs are blocked on purpose. **ARP** finds devices on your own LAN (needs Npcap + Administrator). Sniffer now also shows ARP packets and top services (HTTP, HTTPS, FTP, DNS...).

## Tests
`python -m pytest -q`

## Troubleshooting
- "Permission denied": run PowerShell as Administrator.
- "No interface found": install/reinstall Npcap, restart PC.
- Empty tables: no traffic yet, or wrong interface.

## Build .exe (optional)
`python -m pip install pyinstaller` then `pyinstaller --noconfirm --windowed --collect-all customtkinter main.py`
