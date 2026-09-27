# blooms — 菇點明信片資料

## 用途

本倉庫存放「菇點」明信片座標資料，供 App 使用者下載匯入。

- `default_bookmarks.json`：內建預設書籤資料，格式與 App 的 `BackupCodec` 相容，可直接下載匯入使用。
- `postcard_bookmarks.json`：預留檔案（目前為空）。

## 資料來源

- **來源網站**：[talllkai 皮克敏明信片地圖](https://pikmin.talllkai.com/Postcard)
- **資料內容**：來源網站中「🍄 菇」類型（`typeFilter=1`）的明信片，每筆含名稱、座標（四捨五入至小數 6 位）與國家備註。
- **欄位對應**：名稱 → `name`、座標 → `points[0]`、國家 → `note`（格式 `菇點；<國家>`）。出於隱私與著作權考量，**不收錄**分享者暱稱、日期與站方描述原文。
- **授權**：站方明示「歡迎自由分享・轉載」，引用時請附上來源網站連結。

## 資料格式

```json
{
  "schemaVersion": 1,
  "exportedAt": 0,
  "books": [
    {
      "id": "default-mushroom-001",
      "name": "瑞士河畔建築",
      "type": "SINGLE",
      "points": [ { "lat": 46.204314, "lng": 6.135961 } ],
      "categories": ["postcard"],
      "note": "菇點；瑞士"
    }
  ]
}
```

- `books[].type` 一律 `SINGLE`，`points` 恰 1 點；`categories` 一律 `["postcard"]`。
- 檔案編碼 UTF-8。

