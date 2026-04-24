<div align="center">

```
███████╗████████╗██╗  ██╗██╗███████╗██╗
██╔════╝╚══██╔══╝██║  ██║██║██╔════╝██║
█████╗     ██║   ███████║██║█████╗  ██║
██╔══╝     ██║   ██╔══██║██║██╔══╝  ██║
███████╗   ██║   ██║  ██║██║██║     ██║
╚══════╝   ╚═╝   ╚═╝  ╚═╝╚═╝╚═╝     ╚═╝
```

**Affordable WiFi Pentesting Platform for Testing & Learning**

🌐 **[haybnz.web.app](https://haybnz.web.app/)** &nbsp;·&nbsp; 📖 **[Wiki](https://github.com/h9zdev/EthiFi/wiki)** &nbsp;·&nbsp; 🐛 **[Issues](https://github.com/h9zdev/EthiFi/issues)**

[![License](https://img.shields.io/badge/license-MIT-00ff9f?style=flat-square)](LICENSE.md)
[![Platform](https://img.shields.io/badge/platform-ESP8266-ff6b35?style=flat-square)](https://www.espressif.com/)
[![Build](https://img.shields.io/badge/build-Arduino%20IDE-00b4d8?style=flat-square)](https://www.arduino.cc/)
[![GitHub Stars](https://img.shields.io/github/stars/h9zdev/EthiFi?style=flat-square&color=ffd60a)](https://github.com/h9zdev/EthiFi/stargazers)
[![Wiki](https://img.shields.io/badge/docs-wiki-blueviolet?style=flat-square)](https://github.com/h9zdev/EthiFi/wiki)

</div>

## 🧭 What is EthiFi?

**EthiFi** is a low-cost, open-source WiFi pentesting platform built on the **ESP8266** microcontroller. Designed for security researchers, students, and enthusiasts who want to learn about wireless network vulnerabilities — without spending a fortune.

> ⚠️ **Ethical Use Only** — EthiFi is intended strictly for **authorized testing and educational purposes**. Never use on networks you do not own or have explicit permission to test. Unauthorized access to networks is illegal.



## 📋 Table of Contents

- [✨ Features](#-features)
- [🔌 Supported Hardware](#-supported-hardware)
- [💾 Flash Size](#-flash-size)
- [🛠️ Installation](#️-installation)
- [🔧 Driver Installation](#-driver-installation)
- [🚀 Getting Started](#-getting-started)
- [🩺 Troubleshooting](#-troubleshooting)
- [📥 Quick Downloads](#-quick-downloads)
- [🤝 Contributing](#-contributing)
- [👨‍💻 Developer](#-developer)
- [⚖️ Disclaimer](#️-disclaimer)
- [📄 License](#-license)



## ✨ Features

| 🔧 Feature | 📝 Description |
|---|---|
| 📡 **Deauth Attacks** | Send deauthentication frames to disconnect clients from access points |
| 🔍 **Network Scanner** | Scan and list nearby WiFi networks and connected clients |
| 🎭 **Beacon Spam** | Flood the airspace with fake SSIDs |
| 🕵️ **Probe Request Monitor** | Capture and log probe requests from nearby devices |
| 💻 **Web UI** | Control everything from a browser — no app needed |
| 💾 **Affordable Hardware** | Runs on ~$3 ESP8266 boards |



## 🔌 Supported Hardware

EthiFi runs on any ESP8266-based board. Recommended options:

| 🖥️ Board | 💰 Approx. Cost | 📝 Notes |
|---|---|---|
| NodeMCU v1/v2/v3 | ~$3–5 | Most common, easiest to use |
| Wemos D1 Mini | ~$3–4 | Compact form factor |
| ESP-01 | ~$1–2 | Minimal, needs USB adapter |
| DSTIKE Deauther | ~$10–15 | Has OLED + dedicated design |



## 💾 Flash Size

> ⚠️ **The flash size is an important factor!** Choosing the wrong flash size setting will cause the firmware to fail or behave unexpectedly.

Make sure to select the correct flash size for your specific ESP8266 module before flashing. Different modules ship with different flash chip sizes — check your board's specs carefully.

![ESP8266 Module Flash Sizes](https://raw.githubusercontent.com/wiki/spacehuhn/esp8266_deauther/img/esp_modules.jpg)

| 📦 Module | 💾 Flash Size |
|---|---|
| ESP-01 (old) | 512 KB |
| ESP-01 (new) | 1 MB |
| ESP-07 | 1 MB |
| ESP-12E / NodeMCU | 4 MB |
| Wemos D1 Mini | 4 MB |

> 💡 When in doubt, try **4MB** — most modern NodeMCU and D1 Mini boards ship with 4MB flash.



## 🛠️ Installation

### Method 1 — ⚡ NodeMCU Flasher *(Easiest — Windows only)*

> Best for beginners. No coding required.

📥 **Download:** [NodeMCU Flasher](https://github.com/nodemcu/nodemcu-flasher) · [EthiFi Firmware (.bin)](https://github.com/h9zdev/EthiFi/releases)

**Steps:**
1. 🔌 Connect your ESP8266 and select the **COM port**
2. ⚙️ Go to the **Config** tab
3. 📂 Select your `.bin` file at address `0x000000`
4. ◀️ Switch back to **Operation**
5. ▶️ Click **Flash** and wait for it to complete

![NodeMCU Flasher Settings](https://raw.githubusercontent.com/wiki/spacehuhn/esp8266_deauther/img/flash_settings_nodemcu_flasher.jpg)

---

### Method 2 — ⚙️ Arduino IDE *(Full Source)*

> Best for developers who want to customize or contribute.

📥 **Download:** [Arduino IDE](https://www.arduino.cc/en/software) · [EthiFi Source (.zip)](https://github.com/h9zdev/EthiFi/archive/refs/tags/EthFi.zip)

**Steps:**

**1.** Install and open **Arduino IDE**

**2.** Download and extract the EthiFi source `.zip`

**3.** Open `esp8266_deauther.ino` from the extracted folder

**4.** Add the board URL — go to **File → Preferences** and paste into *Additional Boards Manager URLs*:
```
https://raw.githubusercontent.com/SpacehuhnTech/arduino/main/package_spacehuhn_index.json
```

**5.** Install the board — go to **Tools → Board → Boards Manager**, search `deauther`, install **Deauther ESP8266 Boards**

**6.** Select your board under **Tools → Board → Deauther ESP8266 Boards** *(not ESP8266 Modules!)*

**7.** *(Optional)* Configure via **Tools → Deauther Config**

**8.** *(Optional)* Reset prior install: **Tools → Erase Flash → All Flash Contents**

**9.** Hit **Upload** ✅

---

## 🔧 Driver Installation

Most ESP8266 boards use one of two USB-to-Serial chips: **CP2102** or **CH340**. If your board isn't detected when plugged in, you need to install the correct driver.

![NodeMCU Serial Module Types](https://raw.githubusercontent.com/wiki/spacehuhn/esp8266_deauther/img/nodemcu_serial_modules.jpg)

> 💡 **How to tell which chip you have:** Look at the small IC near the USB port on your board. It will be labeled `CP2102` or `CH340G`.



### 🔵 CP2102 Driver *(Silicon Labs)*

Used on many NodeMCU v1, DSTIKE boards, and others.

| 🖥️ OS | 📥 Download |
|---|---|
| Windows / macOS | [Silicon Labs — CP210x VCP Drivers](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers) |
| Linux | ✅ Built-in — no install needed |

**Steps (Windows):**
1. 📥 Download the driver `.zip` from the Silicon Labs link above
2. 📂 Extract and run `CP210xVCPInstaller_x64.exe` (use `x86` for 32-bit Windows)
3. ✅ Follow the installer prompts and complete installation
4. 🔌 Unplug and re-plug your board
5. Open **Device Manager → Ports (COM & LPT)** — you should see:
   `Silicon Labs CP210x USB to UART Bridge (COMx)`



### 🟢 CH340 / CH341 Driver *(WCH)*

Used on NodeMCU v3 (Lolin), Wemos D1 Mini, and many cheap clone boards.

| 🖥️ OS | 📥 Download |
|---|---|
| Windows | [WCH — CH341SER.EXE](https://www.wch-ic.com/downloads/CH341SER_EXE.html) |
| macOS | [WCH — CH341SER MAC](https://www.wch-ic.com/downloads/CH341SER_MAC_ZIP.html) |
| Linux | ✅ Built-in (kernel 2.6+) — no install needed |

**Steps (Windows):**
1. 📥 Download `CH341SER.EXE` from the WCH link above
2. ▶️ Run the installer and click **INSTALL**
3. ✅ Confirm the success message
4. 🔌 Unplug and re-plug your board
5. Open **Device Manager → Ports (COM & LPT)** — you should see:
   `USB-SERIAL CH340 (COMx)`



## 🚀 Getting Started

Once flashed:

1. 📶 Connect to the **EthiFi WiFi network** from your phone or laptop
   - Default SSID: `EthiFi`
   - Default Password: `deauther`

2. 🌐 Open your browser and navigate to:
   ```
   http://192.168.4.1
   ```

3. 🎛️ Use the **Web UI** to scan networks, select targets, and run tests



## 💻 Web UI

EthiFi is controlled entirely through a browser-based interface — no app needed.

<div align="center">

**Loading Screen**
![EthiFi Loader](https://raw.githubusercontent.com/H9yzz/H9yzz/main/ETHFI-LOADER.png)

**Home**
![EthiFi Home](https://raw.githubusercontent.com/H9yzz/H9yzz/main/HOME%20.png)

**Network Scan**
![EthiFi Scan](https://raw.githubusercontent.com/H9yzz/H9yzz/main/SCAN.png)

**SSID Manager**
![EthiFi SSID](https://raw.githubusercontent.com/H9yzz/H9yzz/main/SSID.png)

**Attacks**
![EthiFi Attacks](https://raw.githubusercontent.com/H9yzz/H9yzz/main/ATTCK.png)

**Settings**
![EthiFi Settings](https://raw.githubusercontent.com/H9yzz/H9yzz/main/SETTNG.png)

</div>


## 🩺 Troubleshooting

### ❌ Board not detected / No COM port shown

- Install the correct driver — [CP2102](#-cp2102-driver-silicon-labs) or [CH340](#-ch340--ch341-driver-wch)
- Try a different USB cable — many cables are **charge-only** and carry no data
- Try a different USB port on your computer
- On Windows: open **Device Manager** and look for unknown devices with ⚠️ icons


### ❌ Flash fails or board disconnects mid-flash

- Hold the **FLASH / BOOT** button on your board while initiating the flash
- Lower the baud rate in your flasher (try `115200` instead of `460800`)
- Make sure no other program (e.g. serial monitor) is using the COM port
- Try a shorter USB cable


### ❌ Wrong flash size selected

- If firmware crashes or the web UI doesn't load, you likely selected the wrong flash size
- Re-flash with the correct size — see the [Flash Size](#-flash-size) section above



### ❌ Web UI not loading at `192.168.4.1`

- Make sure you are connected to the **EthiFi** WiFi, not your home router
- Disable mobile data on your phone (it may silently switch away from EthiFi)
- Use `http://` explicitly — not `https://`
- Try a different browser or clear your cache



### ❌ Arduino IDE doesn't show Deauther boards

- Double-check the board manager URL was added correctly in **File → Preferences**
- Restart Arduino IDE after adding the URL
- Make sure you clicked **Install** in Boards Manager after searching



### ❌ Upload fails in Arduino IDE

- Select the correct **COM port** under **Tools → Port**
- Make sure no other app is using the port (close any open serial monitors)
- Press and hold the **BOOT** button on your board during upload, release when upload starts



> 📖 For more help, visit the **[EthiFi Wiki](https://github.com/h9zdev/EthiFi/wiki)** or open an **[Issue](https://github.com/h9zdev/EthiFi/issues)**.

---

## 📥 Quick Downloads

| 📦 Resource | 🔗 Link |
|---|---|
| ⚡ NodeMCU Flasher | [github.com/nodemcu/nodemcu-flasher](https://github.com/nodemcu/nodemcu-flasher) |
| 🛠️ Arduino IDE | [arduino.cc/en/software](https://www.arduino.cc/en/software) |
| 📦 EthiFi Releases | [github.com/h9zdev/EthiFi/releases](https://github.com/h9zdev/EthiFi/releases) |
| 📡 EthiFi Source | [github.com/h9zdev/EthiFi](https://github.com/h9zdev/EthiFi) |
| 🔵 CP2102 Driver | [silabs.com](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers) |
| 🟢 CH340 Driver | [wch-ic.com](https://www.wch-ic.com/downloads/CH341SER_EXE.html) |



## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

1. 🍴 Fork the repo
2. 🌿 Create a branch: `git checkout -b feature/my-feature`
3. 💾 Commit changes: `git commit -m 'Add my feature'`
4. 📤 Push: `git push origin feature/my-feature`
5. 🔁 Open a **Pull Request**



## 👨‍💻 Developer

<div align="center">

**EthiFi** is designed, developed, and maintained by **h9zdev**.

🌐 [haybnz.web.app](https://haybnz.web.app/) &nbsp;·&nbsp; 🐙 [github.com/h9zdev](https://github.com/h9zdev)

*Built with a passion for affordable, accessible cybersecurity education.*

</div>



## ⚖️ Disclaimer

> **EthiFi is developed strictly for educational and authorized security research purposes.**
>
> - ✅ **Do** use it on networks you own
> - ✅ **Do** use it with explicit written permission from the network owner
> - ✅ **Do** use it in controlled lab environments for learning
> - ❌ **Never** use it on public, corporate, or unauthorized networks
> - ❌ **Never** use it to disrupt services or harm others
>
> Misuse of this tool may violate laws including the **Computer Fraud and Abuse Act (CFAA)**, **EU Directive 2013/40/EU**, and equivalent legislation in your jurisdiction.
>
> **The developer (h9zdev) and all contributors accept no responsibility for any misuse, damage, legal consequences, or harm caused by this software. You are solely responsible for how you use EthiFi.**



## 📄 License

Distributed under the **MIT License**. See [`LICENSE.md`](LICENSE.md) for full details.



<div align="center">

Made with ❤️ by [h9zdev](https://github.com/h9zdev) &nbsp;·&nbsp; 🌐 [haybnz.web.app](https://haybnz.web.app/)

⭐ **If EthiFi helped you learn something, give it a star!** ⭐

</div>
