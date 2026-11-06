# 金門 3D 暗空與光影足跡地圖

> Kinmen 3D Dark-Sky Light-Trace Map
>
> 現代軟體工程 — HW7

以 Three.js 打造的金門 3D 互動地形地圖，結合「暗空觀測」與「攝影光影足跡」兩大主題。整個專案是單一 `index.html`，免安裝、免建置，直接用瀏覽器開啟即可使用。

## 線上瀏覽

- 原始碼：<https://github.com/Chifeng-chiu/_se-HW7>
- 本機使用：下載後直接以瀏覽器開啟 `index.html`（需連網載入 CDN 資源）

## 功能特色

### 3D 金門地形
- 以 Three.js 建構金門本島與烈嶼的 3D 地形
- 標示金城、金寧、金湖、金沙、烈嶼等鄉鎮
- 左鍵旋轉、右鍵平移、滾輪縮放，並可一鍵重置為鳥瞰視角
- 即時地形游標座標（WGS84）與羅盤方位 HUD

### 光影足跡
- 內建 5 個金門知名攝影點：
  - 昔果山海灘（日出／飛機）
  - 太武山（制高點／星空）
  - 慈湖（夕陽／星空）
  - 建功嶼（潮汐／藍調）
  - 模範街（街拍／燈火）
- 點選足跡清單即可飛往該地點並開啟資訊面板
- 支援自行新增光影足跡：點擊地形放置光點、命名、上傳照片
- 自動讀取照片的 EXIF 與 GPS 資訊（相機、鏡頭、焦距、光圈、快門、ISO）
- 自訂足跡儲存在瀏覽器 `localStorage`，可隨時刪除

### 暗空觀測面板
- 觀測評分（0–100）
- 雲量、Bortle 暗空等級、月相資訊
- 觀星條件評語與更新時間
- 目前為前端模擬資料（Simulated / Frontend Only）

### 視覺與互動
- 深空星空、星雲、掃描線與暈影等電影感視覺效果
- GSAP 動畫、載入動畫與平滑鏡頭轉場
- 繁體中文介面，支援桌機與行動裝置

## 使用技術

| 技術 | 用途 |
| --- | --- |
| HTML5 / CSS3 / JavaScript (ES Modules) | 單檔前端應用 |
| [Three.js](https://threejs.org/) 0.160 | 3D 地形、星空與光跡 |
| [Tailwind CSS](https://tailwindcss.com/)（CDN） | 介面樣式 |
| [GSAP](https://gsap.com/) 3.12 | 動畫與轉場 |
| [exif-js](https://github.com/exif-js/exif-js) | 讀取照片 EXIF / GPS |
| Google Fonts | Noto Sans TC、Space Grotesk、JetBrains Mono |

## 專案結構

```
_se-HW7/
└── index.html   # 完整應用程式（HTML + CSS + JS）
```

## 執行方式

### 方式一：直接開啟
在檔案總管中雙擊 `index.html`，以瀏覽器開啟即可。

### 方式二：本機靜態伺服器（建議）
部分瀏覽器對 `file://` 載入 ES Module 較嚴格，可改用靜態伺服器：

```bash
# 使用 Python
python -m http.server 8000

# 或使用 Node.js
npx serve .
```

再開啟 <http://localhost:8000>。

> 首次載入需從 CDN 取得 Three.js、Tailwind、GSAP 與字型，請保持網路連線。

## 資料儲存說明

- 自訂光影足跡、照片與座標僅儲存在**瀏覽器的 LocalStorage**。
- 不會上傳到任何伺服器；清除網站資料後即會消失。
- 暗空觀測數值為前端模擬資料，非即時氣象或天文資料。

## 授權

本專案為課程作業用途。如需轉載或再利用，請先聯絡作者。
