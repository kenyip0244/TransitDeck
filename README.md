# TransitDeck — 行車記錄片與模擬遊戲片雲端影片庫

**TransitDeck** 是一款專為拍巴士、鐵路行車記錄片，以及錄製 OMSI 2、報站機模擬遊戲片的創作者設計的雲端影片與封面管理工具（PWA）。支援手機、平板及電腦跨裝置即時同步，並可連接 YouTube 頻道自動讀取過往所有已發佈影片。

🔗 **線上使用網址**：[https://kenyip0244.github.io/TransitDeck/](https://kenyip0244.github.io/TransitDeck/)

---

## 核心功能

* **影片製作進度追蹤**：清晰劃分「未傳入電腦」、「已傳入待剪」、「已剪待上載」及「已上載 YouTube」四個階段，隨時掌握記憶卡與硬碟素材進度。
* **一鍵匯出 CSV 本地備份**：直接從前端快取生成 UTF-8 編碼 CSV 表格（含拍攝日期、營運商／遊戲分類、路線／標題名、影片標題、車型／地圖、車牌／備註、製作狀態、YouTube 連結與 Video ID），可用 Excel 直接開啟。
* **自動生成與複製 YouTube 標題**：根據營運商標籤、路線、目的地、車型與車牌自動組裝標準 YouTube 標題，點擊即可複製到剪貼簿。
* **1005.idv.hk 車牌資料查詢**：輸入車牌或車隊編號即可自動查詢並填入對應營運商與車型。
* **交通營運商與模擬遊戲分類**：內置九巴（KMB）、城巴（CTB）、龍運（LWB）、嶼巴（NLB）、港鐵（MTR）色標，並設有 **OMSI 2** 及 **報站機模擬（PIDS）** 專屬分類。
* **YouTube 頻道全量自動讀取與儲存**：輸入公開頻道的 `@Handle` 或 `UC...` Channel ID，自動讀取過往全部公開影片並寫入影片庫（根據 Video ID 自動去重）。
* **多用戶雲端隔離與 PWA 安裝**：透過 Firebase Authentication（Google 登入）與 Firestore 安全規則實現用戶資料完全隔離；支援本機離線儲存及 JSON 備份還原。

---

## 更新日誌（Changelog）

* **2026-11-17**
  * 新增 **一鍵匯出 CSV 備份** 功能，優先讀取前端記憶體快取（無快取時才向 Firestore 讀取一次），並加入 UTF-8 BOM 支援 Excel 繁體中文顯示。
  * 新增 **一鍵生成並複製 YouTube 標題** 功能（支援列表卡片快捷複製及編輯視窗一鍵產生）。
  * 整合 `1005.idv.hk` 車牌／車隊編號自動查詢功能，並將「路線編號」調整為「標題名」。
  * 升級 YouTube 頻道抓取邏輯，支援讀取總上傳播放清單（`UU...`）獲取過往全部公開影片。

---

## 專案檔案結構

```text
TransitDeck/
├── index.html      # 產品介紹頁（Landing Page）
├── app.html        # 主影片庫管理應用程式（PWA & Firebase Sync）
├── 404.html        # 自訂 404 錯誤頁面（Route Not In Service）
└── README.md       # 專案說明與更新日誌
```
© 2026 TransitDeck | Powered by SZPTF
