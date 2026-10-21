# 育華國小 六年忠班 教學網站

彰化縣芳苑鄉育華國民小學「六年忠班」班級教學網站（純靜態 HTML/CSS/JS，離線也能開啟）。

## 檔案結構

```
個人網頁/
├─ index.html                          網站主頁（所有內容都在這個檔案）
├─ logo.png                            校徽 / 網站 Logo（珍珠牡蠣圖）
├─ qrcode_yhes.chc.edu.tw.png          育華國小全球資訊網 QR Code（450×450）
├─ css/
│  └─ style.css                        網站樣式（所有版面、配色、RWD 都在這裡）
├─ assets/icons/
│  ├─ bootstrap-icons.min.css          免費圖示：Bootstrap Icons（MIT 授權）
│  └─ fonts/                           圖示字型（woff2 / woff）
└─ okpng/                              預留資料夾（可放活動照片）
```

## 使用方式

直接用瀏覽器開啟 `index.html` 即可。若要放到網站空間（例如 GitHub Pages、
校園網站伺服器），把整個資料夾上傳即可，不需要安裝任何程式。

## 常見修改位置

| 想改什麼 | 位置 |
| --- | --- |
| 公告內容 | `index.html` → 搜尋 `id="annList"`，複製一段 `<li class="ann-item">` 貼在最前面即可新增 |
| 班導師姓名／聯絡方式 | `index.html` → 搜尋 `teacher-card` |
| 每週課表 | `index.html` → 搜尋 `<table class="tt">` |
| 學習資源連結 | `index.html` → 搜尋 `class="res-grid"` |
| 活動相簿 | `index.html` → 搜尋 `class="gal-grid"` |
| 畢業典禮倒數日期 | `index.html` → 搜尋 `GRADUATION_DATE` |
| 顏色、圓角、陰影、字體 | `css/style.css` 最上方 `:root` 變數區 |
| QR Code 尺寸 | `css/style.css` → `.qr-box img`（目前為 450×450） |

### 換上真實活動照片

把照片放進 `okpng/` 資料夾，然後把相簿的色塊換成圖片：

```html
<figure class="gal-item gal-item--1 reveal">
  <img src="okpng/activity-01.jpg" alt="校慶運動會活動照片">
</figure>
```

（`.gal-item` 已設定 4:3 比例與 `overflow:hidden`，照片會自動裁切填滿。）

### 更換 QR Code

直接覆蓋 `qrcode_yhes.chc.edu.tw.png` 檔案即可，名稱與尺寸（450×450）不用改。

## 設計說明

- **主題**：珍珠之光（Pearl of Knowledge），呼應校徽的珍珠意象，
  主色為深海藍 → 湖水藍 → 薄荷綠，輔以珍珠金作為重點色。
- **圖示**：全站使用 [Bootstrap Icons](https://icons.getbootstrap.com/)（MIT 授權，可免費商用），
  字型已下載到本機 `assets/icons/fonts/`，離線也能正常顯示。
- **互動功能**：
  - 頂部導覽列捲動時自動置底並高亮目前區段（Scroll Spy）
  - 手機 / 平板自動切換為 hamburger 選單
  - 區塊進場動畫（IntersectionObserver），支援 `prefers-reduced-motion`
  - 畢業典禮即時倒數、頂部即時日期
  - 回到頂端按鈕
- **無障礙**：Lighthouse 審核「無障礙 / 最佳做法 / SEO」三項皆為 100 分。
- **響應式**：390px（手機）～ 1440px（桌機）皆已實測無橫向捲動。

## 校園資訊

- 校名：彰化縣芳苑鄉育華國民小學
- 地址：50448 彰化縣芳苑鄉永興村太平路 300 號
- 電話：04-8933261 / 04-8934246　傳真：04-8935311
- 網站：https://yhes.chc.edu.tw/
- 班級網頁：https://sites.google.com/view/iloveyhes
