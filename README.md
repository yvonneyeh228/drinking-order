# 🥤 辦公室飲料訂購系統

辦公室同仁每日飲料點單的統計與管理介面，支援雲端 Google Sheets 同步及本地離線模式。

## 功能特色

- 📋 **即時點單** — 填寫姓名、選擇飲品、設定甜度與冰塊
- 🔍 **飲品搜尋 & 分類篩選** — 快速找到想喝的飲料
- 📊 **統計總覽** — 即時顯示總杯數、總金額、跟單人數及熱門飲品
- ✏️ **編輯 / 刪除點單** — 彈性修改已登記的訂單
- ☁️ **Google Sheets 雲端同步** — 透過 Google Apps Script 儲存資料
- 💾 **離線本地模式** — 網路斷線時自動切換，資料儲存於 localStorage

## 技術架構

純前端單頁應用，**無需任何建置工具或伺服器**，直接以瀏覽器開啟即可執行。

| 技術 | 用途 |
|------|------|
| React 18 (CDN) | UI 元件與狀態管理 |
| Tailwind CSS (CDN) | 樣式設計 |
| Babel Standalone | 瀏覽器內 JSX 編譯 |
| Google Apps Script | 後端 API / Google Sheets 整合 |

## 使用方式

### 直接開啟（本地）

直接用瀏覽器開啟 `index.html` 即可，無需安裝任何套件。

### 部署至 GitHub Pages

1. Fork 或 clone 此專案
2. 進入 Repository → **Settings → Pages**
3. Source 選擇 `Deploy from a branch`，Branch 選 `main`，資料夾選 `/ (root)`
4. 儲存後稍待片刻，GitHub 會提供一個公開網址

> **注意：** 預設選單為內建示範資料。若要啟用 Google Sheets 雲端同步，  
> 請將 `index.html` 第 88 行的 `API_URL` 替換為您自己的 Google Apps Script 網址。

## Google Apps Script 設定（選用）

若要使用雲端同步功能：

1. 建立一份 Google Sheets，建立 `Menu`（菜單）與 `Orders`（訂單）兩個工作表
2. 在 Google Sheets → **擴充功能 → Apps Script** 貼上對應的後端程式碼
3. 部署為 **網路應用程式**（存取權限設為「任何人」）
4. 複製部署網址，取代 `index.html` 中的 `API_URL`

## 專案結構

```
drinking-order/
├── index.html   ← 完整應用程式（單一檔案）
└── .gitignore
```

## License

MIT
