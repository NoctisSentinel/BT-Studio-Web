# BT Studio 白棠影像造型工作室

白棠影像造型工作室官方網站，位於台中南屯，提供韓式證件照、職業形象照、全家福寫真及妝髮造型服務。

**網站網址：** [bt-studio.nox-ai.net](https://bt-studio.nox-ai.net)

---

## 專案結構

```
├── index.html          # 網頁主體（僅包含結構，不含文字）
├── content.js          # ← 所有網站文字內容都在這裡
├── css/
│   └── style.css       # 樣式設定
├── assets/
│   ├── logo/           # 工作室 Logo
│   ├── hero/           # 首頁背景照片
│   ├── services/       # 服務項目照片
│   ├── portfolio/      # 作品展示照片
│   └── about/          # 關於我們照片
└── source-ori/         # 原始素材備份（不上傳至 Git）
```

---

## 如何修改網站文字

所有網站文字都集中在 **`content.js`** 這個檔案中，修改時**不需要接觸任何 HTML 或 CSS 程式碼**。

### 操作步驟

1. 用任意文字編輯器開啟 `content.js`（記事本、VS Code 等皆可）
2. 找到要修改的區塊（每個區塊都有中文註解說明）
3. 修改引號 `" "` 內的文字
4. 儲存檔案後重新部署即可生效

### 可修改的內容

| 區塊 | 內容說明 |
|---|---|
| `meta` | 頁面標題與搜尋引擎描述（SEO） |
| `nav` | 導覽列連結名稱 |
| `hero` | 首頁標語、按鈕文字 |
| `services` | 各服務項目的標題、說明文字、特色列表 |
| `portfolio` | 作品展示標題、分類篩選按鈕 |
| `pricing` | 方案名稱、價格、項目列表、標籤文字 |
| `booking` | 預約說明、LINE ID 與連結網址、地址、電話、Email |
| `about` | 關於我們的所有段落文字與特色說明 |
| `footer` | 版權聲明文字 |

---

### 範例：修改首頁標語

開啟 `content.js`，找到以下內容：

```js
hero: {
  tagline: "光影之美・永恆瞬間",   // ← 修改這裡
  ...
}
```

將引號內的文字改為想要的內容，儲存即可。

---

### 範例：修改項目列表

```js
s01: {
  features: [
    "專業底妝造型",          // ← 可修改每一行
    "白、淺灰、深灰背景任選",  // ← 可新增或刪除項目
    "多種尺寸輸出",
    "高解析數位檔提供"
  ]
}
```

每個項目各佔一行，可以新增、刪除或調換順序，只需保留每行的 `"引號"` 與結尾的逗號 `,`。

---

### 範例：更新聯絡資訊

```js
booking: {
  line_id:  "LINE ID：@lcx1786x",      // 顯示在網頁上的 LINE ID 文字
  line_url: "https://lin.ee/8l7pXm1",  // LINE 連結網址
  address:  "台中市南屯區惠中路三段33號5樓",
  phone:    "0905-333289",
  email:    "btstudio.tw@gmail.com",
  ...
}
```

> ⚠️ **注意：** 請勿刪除引號 `" "`、冒號 `:`、逗號 `,` 等符號，只修改引號內的文字即可。

---

## 部署方式

網站託管於 **Cloudflare Pages**，執行以下指令即可部署更新：

```bash
npx wrangler pages deploy . --project-name=bt-studio --branch=main --commit-dirty=true
```

若已將 GitHub 儲存庫連接至 Cloudflare Pages，推送至 `main` 分支後將自動觸發重新部署。

---

## 技術架構

- 純 HTML / CSS / JavaScript，無需任何建置流程
- Cloudflare Pages 靜態網站託管
- 自訂網域透過 Cloudflare DNS 設定（`nox-ai.net`）
