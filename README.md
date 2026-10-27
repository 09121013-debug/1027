# 理財目標導航

以理財目標為核心的 PV / FV / PMT 試算網站。純靜態單一頁面，不需建置步驟（No build）。

## 專案結構
```
.
├── index.html     # 整個網站（HTML / CSS / JS 都在這個檔案）
├── _headers       # Cloudflare Pages 安全與快取標頭
├── .gitignore
└── README.md
```

## 一、上傳到 GitHub
1. GitHub → New repository（例如 `goal-planner`）→ Create repository
2. 在新 repo 頁面點 **uploading an existing file**
3. 把本資料夾內的所有檔案（`index.html`、`_headers`、`.gitignore`、`README.md`）直接拖進去
   - 注意：是拖「檔案」，不是拖 zip；`index.html` 必須在 repo 最外層
4. Commit changes

## 二、用 GitHub 連動部署到 Cloudflare Pages（推薦，之後 push 會自動更新）
1. Cloudflare Dashboard → Workers & Pages → Create → Pages → **Connect to Git**
2. 授權並選擇剛建立的 repo → Begin setup
3. 設定：
   - Framework preset：`None`
   - Build command：留空
   - Build output directory：`/`（或留空）
4. Save and Deploy → 取得 `https://<專案名稱>.pages.dev`
5. 可在 Custom domains 綁定自己的網域

## 三、不用 GitHub，直接上傳部署（選用）
- Workers & Pages → Create → Pages → Upload assets → 拖入本資料夾的檔案
- 或用指令：`npx wrangler pages deploy . --project-name goal-planner`

## 備註
- 字型由 Google Fonts 載入。
- 使用者的目標資料只存在各自瀏覽器的 localStorage，不會上傳到伺服器。
