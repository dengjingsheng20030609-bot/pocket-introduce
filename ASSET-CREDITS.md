# 素材與授權盤點

本文件描述的是 Pocket Introduce 靜態首頁仿製專案，不是 intro3d 原站或其官方產品程式碼。

## 授權範圍

專案原創程式碼採用 [MIT License](LICENSE)，不涵蓋原站或第三方品牌／商標、文案、價格資料、圖片、3D 模型或其他媒體，也不適用於使用者自行提供的私人內容。專案負責人已確認下列 21 張 WebP 展示圖片可公開散布；圖片仍不屬於本專案 MIT 授權範圍。

## 使用者提供的圖片／3D 模型

按專案需求，實際使用的圖片或 3D 模型由各使用者自行提供。本專案不取得或主張使用者內容的所有權，也不把使用者內容納入專案授權。使用者的私人圖片、模型與其他內容不得提交至公開版本庫。

目前仿製頁只呈現靜態首頁，並**未實作**圖片／模型上傳或處理流程。以下 `assets/` 路徑是頁面所需的靜態展示素材，不是使用者上傳資料庫。

## 專案素材

| 專案路徑／內容 | 用途 | 權利與發布備註 |
| --- | --- | --- |
| `assets/logo.webp` | 舊首頁標誌，現已不再引用 | 未使用；排除於公開 repo 與 Worker 部署之外 |
| `assets/pocket-introduce.svg` | Pocket Introduce 自製字母標誌與 favicon | 專案原創，納入 MIT 授權範圍 |
| `assets/banner/*.webp`（12 張） | 首屏角色展示 | 專案負責人確認可公開散布；不屬於 MIT |
| `assets/home/labelman.webp` | 人像展示 | 專案負責人確認可公開散布；不屬於 MIT |
| `assets/steps/*.webp`（4 張） | 流程步驟示意 | 專案負責人確認可公開散布；不屬於 MIT |
| `assets/styles/*.webp`（4 張） | 角色風格示意 | 專案負責人確認可公開散布；不屬於 MIT |
| `assets/bricolage-500.woff2` | 頁面字型 | Bricolage Grotesque；上游採 SIL Open Font License 1.1，見下方 |
| `index.html` 中的文案、價格和連結 | 仿製首頁內容 | 參考原站製作；不屬於 MIT，價格、政策與功能不代表本專案提供或保證最新 |

## 字型授權來源

- 作者／上游倉庫：[ateliertriay/bricolage](https://github.com/ateliertriay/bricolage)
- 上游授權檔：[OFL.txt](https://github.com/ateliertriay/bricolage/blob/main/OFL.txt)
- 本專案隨附的字型授權副本：[`licenses/OFL-Bricolage-Grotesque.txt`](licenses/OFL-Bricolage-Grotesque.txt)

字型的 OFL-1.1 僅涵蓋字型檔，不涵蓋專案程式碼、文案、圖像或品牌素材。

## 參考原站與非官方說明

本專案重現的是靜態首頁，不是原站服務的完整實作。頁面中的登入、開始使用、方案、隱私政策及支援連結會連至 [intro3d.com](https://intro3d.com/)。頁面所呈現的價格與服務功能不代表本專案提供這些服務，也不保證資訊仍是最新版本。

公開 GitHub repo：[dengjingsheng20030609-bot/pocket-introduce](https://github.com/dengjingsheng20030609-bot/pocket-introduce) 已發布本清單所列的 31 個專案檔案，且未包含未使用的 `assets/logo.webp`。公開 Worker 預覽：[intro3d-clone.nine-hippopotamus.workers.dev](https://intro3d-clone.nine-hippopotamus.workers.dev/) 已更新並通過存取檢查。

## 公開發布檢查

- [x] 專案負責人確認 21 張 WebP 展示圖片可公開散布；它們不標示為 MIT 授權。
- [x] 未使用的 `assets/logo.webp` 排除於公開 repo 與 Worker 部署之外。
- [x] 保留字型 OFL-1.1 授權副本；專案原創程式碼與 SVG 字標採 MIT。
- [x] README 說明專案為靜態仿製頁，並非原站官方產品。
- [x] 公開 repo 的 31 個檔案與 Worker 預覽均已驗收；首頁與 23 個素材路徑回應 HTTP 200。
- [x] 本次部署使用的 Cloudflare API Token 已於驗收後撤銷。
