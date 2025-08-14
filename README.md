#  ESP32 SPIFFS File Downloader (HTTPS)

This project is a **speed test + file downloader** for ESP32 using **HTTPS**.  
It fetches a file from a given URL and saves it into **SPIFFS** (ESP32 internal flash filesystem).  
Perfect for testing **download speeds, SPIFFS write performance**, and **HTTPS connectivity**.

## Features

-  **HTTPS support** – works with secure URLs (`https://`)
-  **Saves files into SPIFFS** for later use
-  **Measures and displays download speed** in Kbps
- **Progress updates** in real-time over Serial Monitor
-  Supports **large test files** to push ESP32 to its limits

## Requirements

- ESP32 board (any variant)
- Arduino IDE with ESP32 board support
- Partition scheme with **enough SPIFFS space** (Tools → Partition Scheme)
- Stable internet connection

##  Large File URLs for Testing

Here are some ready-to-use **HTTPS test files**:

### Hetzner Speed Test Files  
- `https://speed.hetzner.de/10MB.bin`  
- `https://speed.hetzner.de/100MB.bin`

### GitHub Raw File Example  
- `https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json` (~325 KB)

---

**Note:**  
SPIFFS is not meant for *huge* files. If your partition is **4 MB SPIFFS**, a 10 MB file won’t fit.  
In that case, just test speed without saving full file, or use smaller files.


## Internet Speed Note

-> The download speed depends heavily on your internet connection and WiFi signal strength.

-> On high-speed internet, you can achieve the desired ~400 KB/s speed.

-> In low-speed conditions, you might see variations like 230 KB/s average or even 30 KB/s.

-> Highly recommended: Test this project on a stable and fast WiFi network for consistent results.

------------EXPECTED OUTPUT----------------
WiFi Connected! IP: 192.168.1.69
Using URL: https://speed.hetzner.de/10MB.bin
Connecting to https://speed.hetzner.de/10MB.bin
File size: 10485760 bytes
Download started...
Downloaded: 10485760 bytes in 27 seconds
Average speed: 388.06 KB/s
File saved to SPIFFS successfully!

