# 專案備忘錄

## Cloudflare Pages 部署

### 建立專案（僅需執行一次）

```bash
npx wrangler pages project create bt-studio
```

執行後 Cloudflare 會自動分配預設網址：`bt-studio.pages.dev`

---

### 部署／更新網站

```bash
npx wrangler pages deploy . --project-name=bt-studio --branch=main --commit-dirty=true
```

---

### 網站網址

| 類型 | 網址 |
|---|---|
| 自訂網域 | https://bt-studio.nox-ai.net |
| Cloudflare 預設 | https://bt-studio.pages.dev |
| GitHub Pages | https://noctissentinel.github.io/BT-Studio-Web/ |
