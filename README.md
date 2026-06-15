# 🎬 語音極致壓縮工具 (網頁版) - 字幕優化專用

這是一個專為 AI 字幕辨識（如 Faster-Whisper、OpenAI Whisper）設計的**本地端音檔極致壓縮網頁工具**。

透過 **WebAssembly (FFmpeg.wasm)** 技術，本工具完全在**使用者瀏覽器本地端**進行運作。影片與音檔**絕對不會上傳到任何後端伺服器**，兼顧「零網路流量、100% 隱私保護、秒速處理」三大優勢。

👉 **完美搭配工作流**：在本地將 1GB 的影片秒速壓成 5MB 的語音專用 MP3，再上傳到雲端 Whisper 系統，省下 99% 的上傳等待時間！

---

## ✨ 核心特色

* 🔒 **絕對隱私**：所有轉檔皆在您本地電腦的瀏覽器內由 CPU 執行，檔案不落地、不上傳。
* 📉 **極致壓縮**：採用專為語音辨識優化的音訊參數：
    * **捨棄視訊軌**（`-vn`）
    * **變更為單聲道**（`-ac 1`）
    * **降低採樣率至 16,000Hz**（`-ar 16000`）
    * **位元率調至 64kbps**（`-b:a 64k`）
* 🚀 **GitHub Pages 友善**：純靜態網頁架構，已內建跨來源隔離（Cross-Origin Isolation）解法，可免費託管於 GitHub。

---

## 🛠️ 專案檔案結構

請確保您的 GitHub 儲存庫（Repository）包含以下核心檔案：

```text
├── index.html               # 網頁主要 UI 與 FFmpeg 轉檔核心邏輯
├── coi-serviceworker.js     # 關鍵應急腳本（用以繞過 GitHub Pages 的 SharedArrayBuffer 安全限制）
└── README.md                # 本說明文件
