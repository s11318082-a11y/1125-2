# 🎪 午夜謝幕：月蝕馬戲團 (The Midnight Curtain: Eclipse Circus)

一款結合 **Google Gemini AI** 動態敘事、隱藏數值判定、心理恐怖氛圍與塔羅結局圖鑑的網頁互動文字冒險遊戲。

---

## ❓ 為什麼之前上傳 GitHub 後劇情跑不出來？

在原本的 `index.html` 中，API 金鑰欄位是空白的（`const apiKey = "";`，原本依賴預覽環境自動注入金鑰）。當專案部署到 **GitHub Pages** 等靜態網站空間時，瀏覽器無法自動取得金鑰，導致連線至 Google Gemini API 失敗、劇情無法推進。

### ✅ 本專案已完成的修正
1. **內建「🔑 AI 金鑰設定」介面**：玩家進入網頁後，點擊首頁的 **「設定 AI 金鑰」** 或遊戲右上角的 **「🔑 金鑰」**，貼上免費的 Gemini API Key 即可立即遊玩（金鑰僅儲存在玩家自己的瀏覽器 `localStorage` 中，不會外洩）。
2. **支援網址參數快捷分享**：你也可以在分享網址後方加上 `?key=你的API_KEY`（例如 `https://你的帳號.github.io/專案名稱/?key=AIzaSy...`），網頁會自動讀取並存入本機，同時自動隱藏網址列上的金鑰參數。
3. **修復結局彈窗顯示**：補上了結局故事容器 `#ending-story`，確保進入第六幕「謝幕」時能完整閱讀結局全文並收錄進劇情圖鑑。

---

## 🚀 如何上傳並部署到 GitHub Pages

1. **解壓縮本壓縮包**，裡面包含：
   - `index.html`（完整遊戲主程式，含前端介面、音效合成器與 AI 引擎）
   - `README.md`（本說明文件）
2. **上傳至 GitHub Repository**：
   - 登入 GitHub，建立一個新的 Repository（或開啟你原本的專案）。
   - 點擊 **Add file → Upload files**，將 `index.html` 與 `README.md` 直接拖曳上傳並點擊 **Commit changes**。
3. **開啟 GitHub Pages**：
   - 進入該 Repository 的 **Settings（設定）** → 左側選單 **Pages**。
   - 在 **Build and deployment → Branch** 下拉選單選擇 `main`（與 `/ (root)` 資料夾），點擊 **Save**。
   - 等待約 1～2 分鐘，上方即會出現你的遊戲公開網址！
4. **取得免費 Gemini API Key**：
   - 前往 [Google AI Studio](https://aistudio.google.com/apikey) 登入 Google 帳號並建立一組 API Key。
   - 開啟你的 GitHub Pages 遊戲網頁，點擊 **「🔑 AI 金鑰設定」** 貼上金鑰即可開始體驗！
