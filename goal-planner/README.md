# 🎯 目標理財規劃器 Goal Planner

以 PV（現值）、FV（終值）、PMT（定期投入）為核心的目標導向理財工具。
選擇目標（退休、購屋、教育、緊急預備金、旅行、自訂），即時獲得達標診斷、資產成長圖、調整建議與情境比較。

純靜態網站（單一 HTML，無依賴、無建置步驟）。

## 專案結構

```
goal-planner/
├── public/
│   ├── index.html     # 網站本體
│   └── _headers       # Cloudflare 安全標頭
├── wrangler.jsonc     # Cloudflare 設定（Workers 靜態資源）
├── .gitignore
├── LICENSE
└── README.md
```

## 本機預覽

```bash
npx wrangler dev
# 或
cd public && python3 -m http.server 8000
```

## 上傳到 GitHub

```bash
cd goal-planner
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/<你的帳號>/goal-planner.git
git push -u origin main
```

（先在 GitHub 建立一個空的 repository，不要勾選 README / .gitignore。）

## 部署到 Cloudflare

### 方式 A：Cloudflare Pages 連接 GitHub（推薦）
1. Cloudflare 後台 → Workers & Pages → Create → Pages → Connect to Git
2. 選擇 `goal-planner` repository
3. 設定：
   - Framework preset：None
   - Build command：留空
   - Build output directory：`public`
4. Save and Deploy。之後每次 push 到 `main` 都會自動重新部署。

### 方式 B：Workers 靜態資源（使用 wrangler.jsonc）
1. Workers & Pages → Create → Import a repository，選擇此 repo
2. Build command 留空，Deploy command 使用預設 `npx wrangler deploy`
3. 或在本機執行：`npx wrangler deploy`

## 免責聲明
本工具僅供規劃與教育用途，估算結果不代表投資保證，亦非個人化財務建議。

## 授權
MIT License
