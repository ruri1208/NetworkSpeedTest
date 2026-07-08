# LibreSpeedClient

[![Swift](https://img.shields.io/badge/Swift-5.10+-orange.svg)](https://swift.org)
[![iOS](https://img.shields.io/badge/iOS-16.0+-blue.svg)](https://developer.apple.com/ios/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

A lightweight, high-performance iOS speed test utility built with SwiftUI and URLSession. It serves as a pure memory-based client for LibreSpeed endpoints, designed to benchmark network throughput without harming device flash storage.

> **⚠️ DISCLAIMER / 免責聲明**
> 
> **English:** This project is an open-source tool intended for **personal testing, research, and network benchmarking**. It relies entirely on volunteer-hosted public LibreSpeed nodes. Because public servers can experience downtime or bandwidth saturation, this app **WILL NOT** be published to the App Store to avoid maintenance issues. Use at your own risk.
> 
> **中文：** 本專案為開源網路測速工具，僅供**個人測試、學術研究與網路優化**使用。測試節點完全依賴 LibreSpeed 全球志願者提供的免費公共伺服器。鑑於公共節點隨時可能離線或頻寬飽和，本專案**絕不上架 App Store**。請勿用於商業用途，使用者須自行承擔相關風險。

---

## Features / 專案特點

* **Zero I/O Wear (Flash-Safe):** Uses `URLSessionDataTask` streams entirely in RAM. No file writing to disk (`tmp/` or `Caches/`) during download or upload spikes, guaranteeing 0 TBW wear on your device storage.
* **Auto Nearest Node Finder:** Automatically pings 37 global LibreSpeed endpoints via concurrent `getIP.php` lightweight probes to dynamically lock onto the optimal routing node.
* **LibreSpeed Protocol Compliant:** Utilizes native `garbage` and `empty` data endpoints with random timestamp cache-busters to prevent ISP/iOS gateway caching interference.
* **Custom Endpoints:** Supports manually inputting private LibreSpeed or dedicated test servers for closed-network (LAN/Intranet) benchmarking.
* **Built-in Storage Janitor:** Includes a manual cache and temporary directory monitor/cleaner module to optimize host container storage health.

## Technical Stack / 技術棧

* **UI Framework:** SwiftUI
* **Networking Engine:** URLSession (`URLSessionDataDelegate`, `URLSessionTaskMetrics` for low-level latency sampling)
* **Concurrency & Safety:** NSLock-gated parallel network probes & Grand Central Dispatch (`DispatchQueue`)

---

## Requirements / 運行環境

* iOS 16.0+
* Xcode 15.0+
* Swift 5.10+

---

## Setup Instructions / 如何在本地運行

To run this project on your personal iOS device or side-load it via tools like LiveContainer/TrollStore:

1. Clone this repository to your local machine.
2. Open the project in Xcode.
3. Select your project target, go to **Signing & Capabilities**, and select your personal development team.
4. (Optional) Run the app on an iOS Simulator or connect your real iPhone and press **Run (Cmd + R)**.

---

## Credits & References / 致謝與參考項目

This project interacts with backend servers adhering to the open-source speed test standard created by:

* **[LibreSpeed](https://github.com/librespeed/speedtest)** - Self-hosted speedtest backend with no Flash, no Java, no Websocket, pure HTTP.

Special thanks to the worldwide volunteers and sponsors hosting the 37 infrastructure nodes embedded in this application.

---

## License / 授權條款

This project is open-sourced under the [MIT License](LICENSE).
