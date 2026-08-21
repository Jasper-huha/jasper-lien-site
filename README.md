# 連書賢 Jasper Lien｜電子名片網站

## 檔案

```
index.html      主頁（單頁，33 KB）
images/         38 張作品圖（WebP，共 1.2 MB）
zbpack.json     Zeabur 靜態站設定
```

---

## 部署到 Zeabur

### 方法 A：GitHub（推薦，之後改動自動更新）

1. 在 GitHub 開一個新 repo，例如 `jasper-lien-site`
2. 把 `index.html`、`images/`、`zbpack.json` 三個東西丟進去，commit push
3. 到 Zeabur → **Create Project** → **Deploy New Service** → **Git**
4. 選剛剛那個 repo，Zeabur 會自動判斷是靜態網站，直接開始 build
5. Build 完成後 → **Networking** → **Generate Domain**，先拿一個 `xxx.zeabur.app` 網址測試
6. 測試沒問題後綁自訂網域（見下方）

### 方法 B：直接上傳（最快，但之後改要重傳）

1. Zeabur → **Create Project** → **Deploy New Service** → **Upload**
2. 把 `deploy` 整個資料夾壓成 zip 上傳
3. **Networking** → **Generate Domain**

---

## 綁自訂網域

1. Zeabur 服務頁 → **Networking** → **Add Domain** → 輸入你的網域
2. Zeabur 會給你一組 CNAME 紀錄
3. 到網域商（Gandi / Cloudflare / GoDaddy…）後台的 DNS 設定，新增那筆 CNAME
4. 等 5–30 分鐘生效，SSL 憑證 Zeabur 會自動處理

**網域建議**：`jasperlien.com`、`jasperlien.tv`

---

## 之後想改內容

所有文字都在 `index.html` 裡，用任何文字編輯器打開就能改。

幾個常改的地方：

| 想改什麼 | 找什麼關鍵字 |
|---|---|
| 聯絡信箱 / 電話 | `p90huha@gmail.com` |
| 開場那段 | `30 年，13 家電視台` |
| 規格表 | `class="spec"` |
| HERO 下方的人像照 | `id="portrait"` |
| 扶輪社身分（HERO 下方） | `id="rotary"` |
| 節目表（電視台清單） | `const sched=[` |
| Hero 背景滾動的節目名 | `const titles=[` |

換圖：把新圖放進 `images/`，改 `index.html` 裡對應的 `src="images/imgXX.webp"`。

---

## 技術備註

- 單一 HTML，無框架、無 build 流程
- 字體走 Google Fonts CDN
- 已做響應式（桌機 / 平板 / 手機）
- 已標註圖片尺寸，無版面跳動
- 支援 `prefers-reduced-motion`
- 圖片皆為 WebP，並使用 lazy loading
