# Pocket Introduce

**Pocket Introduce** 是一個 intro3d 風格的靜態首頁仿製頁，不是 intro3d 原站、官方產品程式碼或其服務。專案以單一 HTML 頁面重現首頁展示與部分互動，作為可自行修改的前端示例。

> **授權摘要：** 專案原創程式碼與自製 SVG 字標採 MIT License。專案負責人已確認 21 張 WebP 展示圖可公開散布，但這些圖片不屬於 MIT 授權；未使用的舊標誌 `assets/logo.webp` 不納入公開發布。公開 repo：[dengjingsheng20030609-bot/pocket-introduce](https://github.com/dengjingsheng20030609-bot/pocket-introduce)。

## 素材與範圍

圖片與 3D 模型若由使用者自行提供，其所有權與權利仍屬使用者；私人圖片、模型或其他內容不得提交到公開版本庫。

目前專案是**靜態首頁展示**，`assets/` 中的圖片是展示素材；專案尚未實作圖片／模型上傳、AI 生成、3D 編輯、帳號、付款或發布服務。頁面上的登入、開始使用、方案與支援連結仍指向原站。若要把專案擴展成實際處理使用者素材的應用，需另行實作相應功能與隱私／資料處理流程。

## 功能

- 純 HTML、CSS 與原生 JavaScript；沒有建置步驟或第三方 JavaScript 執行期依賴。
- 響應式首頁，包含角色展示跑馬燈、互動導覽預覽、角色風格選擇、月付／年付價格切換與 FAQ 手風琴。
- 靜態展示素材位於 `assets/`；未使用的舊標誌已排除於公開版本之外。

## 本機預覽

需要 Python 3。在專案根目錄執行：

```bash
python3 -m http.server 8000
```

接著開啟 <http://localhost:8000/>。要停止伺服器，按 `Ctrl+C`。也可以使用任何能提供靜態檔案的本機 HTTP 伺服器；不建議直接以 `file://` 開啟。

## Cloudflare Workers 部署

專案使用 `wrangler.jsonc` 部署靜態資產，目標 Worker 名稱為 `intro3d-clone`。部署前請在本機設定 `CLOUDFLARE_API_TOKEN` 與 `CLOUDFLARE_ACCOUNT_ID` 環境變數；Token 不要寫入程式碼或提交到版本庫。對既有 Worker，請使用資源範圍僅限該 Worker 的 `Editor` Token、設定短效期限，並在部署驗收後撤銷；避免使用「所有帳戶」範圍。

```bash
npx wrangler@latest deploy
```

`.assetsignore` 會排除專案文件、Wrangler 設定、字型授權文件、未使用的舊標誌與 Git／建置資料，避免它們被當成網站檔案部署；MIT `LICENSE` 仍會隨網站提供。

## 專案檔案

| 路徑 | 說明 |
| --- | --- |
| `index.html` | 單頁首頁與互動程式 |
| `assets/` | WebP 展示圖片、Bricolage Grotesque 字型與 Pocket Introduce SVG 字標 |
| `LICENSE` | 專案原創程式碼與 SVG 字標的 MIT 授權 |
| `licenses/OFL-Bricolage-Grotesque.txt` | 字型的 SIL Open Font License 1.1 副本 |
| `wrangler.jsonc` | Cloudflare Workers 靜態資產部署設定 |

## 驗證狀態

- 已檢查首頁的本機素材引用：**23 個唯一路徑，未發現缺少檔案**。
- 本機 HTTP 預覽正常；375px 手機寬度預覽已檢查。
- 公開 GitHub repo 已發布 **31 個檔案**，未包含未使用的舊 logo。
- 公開 Worker 預覽已更新：首頁與 23 個本地素材均回應 HTTP 200；README、部署設定與舊 logo 路徑不公開。
- 本專案沒有套件安裝或建置流程，因此沒有 package manager、build 或自動化測試命令。

## 授權範圍

專案原創程式碼及 `assets/pocket-introduce.svg` 字標依 [`LICENSE`](LICENSE) 採 MIT 授權。MIT **不自動涵蓋**原站或第三方的品牌／商標、文案、價格、圖片或其他媒體，也不涵蓋使用者提供的素材。21 張 WebP 展示圖的公開散布權由專案負責人確認，但不因此納入 MIT；請勿將其標示為 MIT 授權素材。

Bricolage Grotesque 字型採 SIL Open Font License 1.1，授權副本位於 `licenses/OFL-Bricolage-Grotesque.txt`。素材來源與權利說明見 [`ASSET-CREDITS.md`](ASSET-CREDITS.md)。

## 參考頁面

- 仿製參考原站：<https://intro3d.com/>
- 公開預覽：<https://intro3d-clone.nine-hippopotamus.workers.dev/>
