# 糖廠樂悠遊｜乙二影展專題網站

以臺中帝國製糖廠為場景的影展專題介紹網站。Vibe Coding 指令見 [PROMPTS.md](PROMPTS.md)。

## 檔案結構
```
index.html      首頁（landing page）
story.html      影片故事
venue.html      拍攝場域
analysis.html   企劃分析
team.html       製作團隊
css/            base / layout / components / rwd 四個 CSS
images/         所有圖片
robots.txt、sitemap.xml   SEO
```

## 部署步驟

### 1. GitHub
1. 到 GitHub 建立一個新的 public repository（例如 `sugar-factory-film`）。
2. 在這個資料夾執行：
   ```bash
   git init
   git add .
   git commit -m "糖廠樂悠遊影展專題網站"
   git branch -M main
   git remote add origin https://github.com/<帳號>/sugar-factory-film.git
   git push -u origin main
   ```
3. Prompt 說明連結：`https://github.com/<帳號>/sugar-factory-film/blob/main/PROMPTS.md`

### 2. Vercel
1. 用 GitHub 帳號登入 https://vercel.com 。
2. Add New → Project → 選剛剛的 repository → Import。
3. Framework Preset 選 **Other**，其他不用改，按 Deploy。
4. 取得網址 `https://<專案名稱>.vercel.app/`，並把 `robots.txt`、`sitemap.xml` 裡的 `YOUR-SITE.vercel.app` 換成這個網址再 push 一次。

### 3. InfinityFree
1. 登入 InfinityFree → 帳號 → Control Panel → **Online File Manager**。
2. 進入 `htdocs` 資料夾，刪除或改名原本的 `index2.html`／預設首頁。
3. 把整個網站（所有 html、`css/`、`images/`、robots.txt、sitemap.xml）上傳到 `htdocs`。
4. 打開 `https://<自己的網址>.infinityfreeapp.com/` 確認看到首頁。
