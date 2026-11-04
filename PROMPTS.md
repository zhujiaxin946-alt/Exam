# 糖廠樂悠遊｜Vibe Coding 指令說明

本文件記錄製作《糖廠樂悠遊》影展專題網站時，與 AI（Claude Code）協作所使用的 Vibe Coding 指令（Prompt），以及每一步產生的成果。

- 專題名稱：糖廠樂悠遊（離城市很近，離壓力很遠）
- 組別：乙二
- 組員：朱家芯、李美茵、陳鈺誠、張紫珊、吳怡霈、林羽恩、葉沛欣
- 使用工具：Claude Code、Canva、GitHub、Vercel、InfinityFree

---

## 1. 整理內容與素材

### Prompt 1：根據企劃書做簡報
```
請根據這份企劃書（乙2_離城市很近離壓力很遠_期中企劃.pdf）幫我生成一份 Canva 簡報。
風格希望結合綠洲與糖廠，不要太多文字、多一點圖。
```
成果：產生 15 頁 Canva 簡報，色系為米白、焦糖棕、鼠尾草綠，後續網站沿用同一套風格與插圖。

### Prompt 2：修正簡報內容
```
請確實依照企劃書內容與頁面規定修改，並讓最小字體不低於 30，
企劃書第一頁最下方有組員姓名。
```
成果：簡報文字全部對照企劃書，作為網站文案的來源。

---

## 2. 建立網站

### Prompt 3：依作業規定建立網站
```
我現在想做一個網頁並按照作業規定：
1. 題目：大二「您自己的影展專題介紹」
2. 建立一個具有導覽列、側邊欄，並具有分頁的完整網頁
3. 需要具有完整的 SEO 內容、Grid System、RWD 功能（手機可顯示完整資訊）
4. CSS 檔案切割後放在 css 資料夾
5. 圖片放在 images 資料夾
```
成果：
| 檔案 | 說明 |
| --- | --- |
| `index.html` | 首頁（Landing page）：主視覺、專題簡介、亮點、標語 |
| `story.html` | 影片故事：故事大綱、角色、核心訊息、分鏡表 |
| `venue.html` | 拍攝場域：帝國製糖廠歷史、產能數據、為什麼選這裡 |
| `analysis.html` | 企劃分析：消費者痛點、競爭者、SWOT、STP |
| `team.html` | 製作團隊：組員、指導老師、參考資料 |

### Prompt 4：素材放進 images 資料夾
```
把企劃書裡的封面、封底、分鏡表、產能圖，以及 Canva 簡報裡的插圖，
裁切後放進 images 資料夾給網頁使用。
```
成果：`images/` 內 18 張圖片（主視覺、四個場域插圖、5 頁分鏡表等）。

### Prompt 5：CSS 切割
```
CSS 請分成多個檔案放在 css 資料夾：基本樣式、版面、元件、RWD 各一個。
```
成果：
- `css/base.css`：全頁文字、標題、段落、連結
- `css/layout.css`：頁首、導覽列、Grid 版面（主內容 3fr＋側邊欄 1fr）、頁尾
- `css/components.css`：區塊盒子、卡片（兩欄／三欄 Grid）、表格、圖片、地圖、分頁按鈕
- `css/rwd.css`：860px（平板）與 600px（手機）兩個 @media 斷點

### Prompt 6：導覽列、側邊欄、分頁
```
每一頁都要有：上方導覽列、右側側邊欄（本頁目錄、作品資訊、標語），
頁面底部要有 1～5 的分頁按鈕和上一頁／下一頁。
```
成果：導覽列用 `nav ul li` 排成一列按鈕，目前頁面加 `class="active"`；側邊欄用 `aside`，手機版會移到內容下方。

### Prompt 7：SEO
```
請加上 SEO：每頁不同的 title、description、keywords、author、robots、Open Graph，
語意化 HTML 標籤、圖片 alt 文字、robots.txt 和 sitemap.xml。
```
成果：五頁皆有獨立 meta；使用 header、nav、main、article、section、aside、footer；所有圖片都有中文 alt。

### Prompt 8：照課堂教過的寫法修改
```
https://github.com/zhujiaxin946-alt/HW07_D1420558
這個 GitHub 是我上課學到的內容，請照著老師有教過的東西修，而且不要讓我的程度躍進太大。
```
成果：參考 HW07 的寫法重寫：
- HTML 結構與 HW07 相同（header＋nav、main＞article＞section、aside、footer、回到頁首）
- 使用課堂學過的標籤：`mark`、`time`、`small`、`table`＋`caption`＋`th scope`、`figure`＋`figcaption`、Google 地圖 `iframe`
- CSS 用元素選擇器與 class，不用變數或進階語法；RWD 用 `@media`
- 移除漢堡選單、結構化資料等課堂沒教過的寫法

---

## 3. 部署

### Prompt 9：部署步驟
```
告訴我怎麼把網站放到 GitHub、用 Vercel 部署，以及上傳到 InfinityFree 取代首頁。
```
成果：見 `README.md` 的部署步驟。

---

## 繳交連結

1. Prompt 說明（本檔案）：https://github.com/zhujiaxin946-alt/Exam/blob/main/PROMPTS.md
2. InfinityFree 網址：https://xin.great-site.net/
3. Vercel 網址：https://exam-d1420558.vercel.app/
