# NetworkX

[![Swift](https://img.shields.io/badge/Swift-5.10+-orange.svg)](https://swift.org)
[![iOS](https://img.shields.io/badge/iOS-16.0+-blue.svg)](https://developer.apple.com/ios/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## 🌐 Introduction / 專案簡介 / 项目简介 / はじめに

* **English:** A lightweight, high-performance iOS speed test utility built with SwiftUI and URLSession. It serves as a pure memory-based client for LibreSpeed endpoints, designed to benchmark network throughput without harming device flash storage.
* **繁體中文:** 一款基於 SwiftUI 與 URLSession 的 iOS 高效能測速工具。作為純記憶體運作的 LibreSpeed 客戶端，本專案專為測試網路吞吐量而設計，完全不傷裝置的快閃記憶體壽命。
* **简体中文:** 一款基于 SwiftUI 与 URLSession 的 iOS 高性能测速工具。作为纯内存运作的 LibreSpeed 客户端，本项目专为测试网络吞吐量而设计，完全不伤设备的闪存寿命。
* **日本語:** SwiftUI と URLSession で構築された軽量・高性能な iOS 向けスピードテストツールです。LibreSpeed エンドポイント用の完全メモリベースのクライアントであり、ストレージ（フラッシュメモリ）に負荷をかけずにネットワークスループットを測定できます。

---

## ⚠️ DISCLAIMER / 免責聲明 / 免責事項

* **English:** This project is for **educational, research, and personal benchmarking purposes only**. It relies entirely on volunteer-hosted public LibreSpeed nodes. Because public servers can experience unpredictable downtime or bandwidth saturation, this app **WILL NOT** be published to the App Store. Use at your own risk.
* **繁體中文：** 本專案僅供**個人測試、學術研究與網路優化**使用。測試節點完全依賴 LibreSpeed 全球志願者提供的免費公共伺服器。鑑於公共節點隨時可能離線或頻寬飽和，本專案**絕不上架 App Store**。使用者須自行承擔相關風險。
* **简体中文：** 本项目仅供**个人测试、学术研究与网络优化**使用。测试节点完全依赖 LibreSpeed 全球志愿者提供的免费公共服务器。鉴于公共节点随时可能离线或带宽饱和，本项目**绝不上架 App Store**。用户须自行承担相关风险。
* **日本語：** 本プロジェクトは**個人利用、学術研究、およびネットワークのベンチマーク目的のみ**のツールです。ボランティアがホストする公開 LibreSpeed ノードに完全に依存しています。公開サーバーは予期せぬダウンタイムや帯域飽和が発生する可能性があるため、本アプリの **App Store への公開は行いません**。ご利用は自己責任でお願いします。

---

## 🚀 Features / 專案特點 / 项目特点 / 主な機能

### English
* **Zero I/O Wear (Flash-Safe):** Uses `URLSessionDataTask` streams entirely in RAM. No file writing to disk during spikes, guaranteeing 0 TBW wear on device storage.
* **Auto Nearest Node Finder:** Pings global LibreSpeed endpoints via concurrent `getIP.php` lightweight probes to dynamically lock onto the optimal routing node.
* **LibreSpeed Protocol Compliant:** Utilizes native `garbage` and `empty` data endpoints with random timestamp cache-busters to prevent gateway caching interference.
* **Custom Endpoints:** Supports manually inputting private LibreSpeed or dedicated test servers for closed-network (LAN/Intranet) benchmarking.

### 繁體中文
* **零硬碟磨損（保護快閃記憶體）：** 測速數據完全在記憶體（RAM）中以資料流形式吞吐。下載與上傳期間絕不寫入任何暫存檔，保證對裝置硬碟造成 0 TBW 磨損。
* **自動鄰近節點探針：** 透過並行發送輕量化的 `getIP.php` 請求探測全球 37 個 LibreSpeed 節點，在毫秒內自動鎖定路由與回應最快的最佳節點。
* **標準協定相容：** 嚴格遵循官方的 `garbage` 與 `empty` 端點規範，並引入隨機時間戳記防快取機制，確保測速數據真實不失真。
* **自訂伺服器端點：** 支援手動輸入私有 LibreSpeed 或特定測試伺服器網址，方便進行區域網路（LAN）或內網環境的壓測與極限測試。

### 简体中文
* **零硬盘磨损（保护闪存）：** 测速数据完全在内存（RAM）中以数据流形式吞吐。下载与上传期间绝不写入任何暂存文件，保证对设备硬盘造成 0 TBW 磨损。
* **自动邻近节点探针：** 通过并行发送轻量化的 `getIP.php` 请求探测全球 37 个 LibreSpeed 节点，在毫秒内自动锁定路由与响应最快的最佳节点。
* **标准协议兼容：** 严格遵循官方的 `garbage` 与 `empty` 端点规范，并引入随机时间戳防缓存机制，确保测速数据真实不失真。
* **自定义服务器端点：** 支持手动输入私有 LibreSpeed 或特定测试服务器网址，方便进行局域网（LAN）或内网环境的压测与极限测试。

### 日本語
* **ゼロ I/O 摩耗（フラッシュ安全）：** `URLSessionDataTask` を使用し、すべてのストリームを RAM 上のみで処理します。ディスクへの書き込みが一切発生しないため、ストレージの寿命（TBW）を縮めません。
* **最寄りノードの自動検出：** 並行して軽量な `getIP.php` プロブを送信し、世界 37 箇所の LibreSpeed エンドポイントから最も応答速度が速い最適なルーティングノードを自動的にロックします。
* **LibreSpeed プロトコル準拠：** ネイティブの `garbage` および `empty` エンドポイントを使用し、プロキシやゲートウェイによるキャッシュ干渉を防ぐためのランダムタイムスタンプ（キャッシュバスター）を実装。
* **カスタムエンドポイント：** プライベートな LibreSpeed サーバーや専用のテストサーバーを手動で入力可能。ローカルネットワーク（LAN）や社内網のベンチマークにも対応しています。

---

## 📦 Credits & Dependencies / 致謝與依賴 / 致谢与依赖 / 謝辞と依存関係

* **English:** This project interacts with backend servers adhering to the amazing open-source speed test standard created by:
* **繁體中文：** 本專案之測速流程與後端架構，高度致謝並遵循以下開源項目所建立之標準協定：
* **简体中文：** 本项目之测速流程与后端架构，高度致谢并遵循以下开源项目所建立之标准协定：
* **日本語：** 本プロジェクトの測定プロセスおよびバックエンド連携は、以下の素晴らしいオープンソース規格に基づき実装されています：

👉 **[LibreSpeed](https://github.com/librespeed/speedtest)** (LGPL v3 License)

---

## 📄 License / 授權條款 / 授权条款 / ライセンス

* **English:** This project is open-sourced under the [MIT License](LICENSE).
* **繁體中文：** 本專案採用 [MIT 授權條款](LICENSE) 開源。
* **简体中文：** 本项目采用 [MIT 授权条款](LICENSE) 开源。
* **日本語：** 本プロジェクトは [MIT ライセンス](LICENSE) のもとでオープンソースとして公開されています。
