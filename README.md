# ParkNow.TW 🚗

台灣停車場查詢網站，支援高雄、台南、嘉義三個城市，提供即時停車場資訊、費率篩選、地圖定位與導航功能。

🔗 **線上版本**
- 桌機版（v2）：[parking_v2.html](https://farchioni18.github.io/parkingMap/parking_v2.html)
- 手機版（v2）：[parking_mobile_v2.html](https://farchioni18.github.io/parkingMap/parking_mobile_v2.html)

---

## 功能介紹

### 共同功能（桌機版 & 手機版）

| 功能 | 說明 |
|------|------|
| 城市切換 | 支援高雄、台南、嘉義 |
| 地址搜尋 | 輸入地址後自動定位並顯示附近停車場（使用 OpenStreetMap Nominatim） |
| GPS 定位 | 頁面載入時自動取得目前位置，預設顯示 1km 內停車場 |
| 行政區篩選 | 下拉選單選擇行政區，地圖自動移至該區中心 |
| 計時費率篩選 | 依每半小時費率上限篩選 |
| 月租費用篩選 | 依月租費用上限篩選 |
| 距離篩選 | 1km / 2km / 5km / 不限 |
| 類型篩選 | 平面 / 立體 / 全部 |
| 快篩 | 有空位 / 月租 / 立體（一鍵切換） |
| 平日/假日費率 | 自動判斷今日是否為假日（含國定假日），顯示對應費率 |
| 日夜配色切換 | 支援淺色/深色模式，深色模式使用 Stadia Maps 底圖 |

---

## 版本差異

### v1（`parking.html` / `parking_mobile.html`）

原始版本，功能完整但介面較為傳統。

- 桌機版：左側固定側欄（篩選 + 列表）+ 右側地圖
- 手機版：獨立的手機版頁面，無地圖，只顯示列表
- 城市切換在 Header 頂端
- 篩選項目以 chip 標籤呈現
- 無日夜配色切換
- 無地址搜尋功能
- 費率只顯示平日費率

### v2（`parking_v2.html` / `parking_mobile_v2.html`）

全新設計，視覺與功能大幅升級。

- 全新版面：Navbar + Filter Bar + 全版地圖 + 底部橫向卡片列
- 城市切換移至 Filter Bar，與其他篩選項目並排
- 所有篩選改為下拉選單，介面更整潔
- 新增地址搜尋（Nominatim API）
- 新增 GPS 自動定位
- 新增日夜配色切換（深色模式使用 Stadia Maps alidade_smooth_dark 底圖）
- 新增平日/假日費率自動判斷（串接台灣政府開放資料）
- 新增地圖收合功能（收合後顯示完整垂直列表）
- 底部卡片列與地圖 pin 雙向連動
- 選取行政區時地圖自動移至該區中心

---

## 桌機版 vs 手機版

| 功能 | 桌機版 | 手機版 |
|------|--------|--------|
| 地圖 | ✅ 全版 Leaflet 地圖 | ❌ 不顯示地圖 |
| 底部卡片列 | ✅ 橫向滾動卡片 | ❌ |
| 地圖收合 | ✅ 可收合切換為垂直列表 | ❌ |
| 停車場列表 | 底部卡片列（橫向） | 垂直卡片列表 |
| 地圖 pin 互動 | ✅ 點擊 pin 高亮對應卡片 | ❌ |
| 導航連結 | ✅ | ✅ |
| 篩選功能 | ✅ 完整 | ✅ 完整 |
| 日夜切換 | ✅ | ✅ |
| GPS 定位 | ✅ | ✅ |
| 地址搜尋 | ✅ | ✅ |

---

## 資料來源

- 停車場資料：高雄市、台南市、嘉義市政府開放資料
- 地理編碼：[OpenStreetMap Nominatim](https://nominatim.openstreetmap.org)（免費，無需 API key）
- 國定假日：[TaiwanCalendar](https://github.com/ruyut/TaiwanCalendar)（整理自政府資料開放平台，免費）
- 地圖底圖（日間）：[CartoDB Voyager](https://carto.com)
- 地圖底圖（夜間）：[Stadia Maps alidade_smooth_dark](https://stadiamaps.com)

---

## 本地開發

```bash
cd kaohsiung-parking
python3 -m http.server 3000
```

開啟瀏覽器：
- 桌機版 v2：http://localhost:3000/parking_v2.html
- 手機版 v2：http://localhost:3000/parking_mobile_v2.html
- 桌機版 v1：http://localhost:3000/parking.html
- 手機版 v1：http://localhost:3000/parking_mobile.html
