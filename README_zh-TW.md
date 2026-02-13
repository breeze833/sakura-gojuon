# Sakura Gojuon (日文 50 音學習)

[開始學習 (Live Demo)](https://breeze833.github.io/sakura-gojuon/) | [English](README.md)

這是一個專為繁體中文使用者（台灣）設計的日文平假名與片假名學習資源。使用 `reveal.js` 製作，提供互動式的 50 音學習投影片。

## 功能特色

### 🌸 視覺與美學
- **櫻花浮水印**: 所有投影片背景皆有淡淡的櫻花花瓣圖案。
- **日式轉場效果**: 採用「拉門 (Sliding Door)」轉場效果，並在切換投影片時觸發「櫻吹雪 (Sakura Blizzard)」動畫。
- **清晰設計**: 使用 `Noto Serif JP` 顯示日文，`Noto Sans TC` 顯示繁體中文，確保高對比度與易讀性。

### 🧭 導覽功能
- **全域導覽列**: 畫面底部固定顯示導覽列，可快速跳轉至：
  - 首頁
  - 大綱
  - 五十音圖
  - 平假名
  - 片假名
  - 測驗
- **優化控制項**: Reveal.js 的控制項位置已調整，避免與導覽列重疊。

### 📚 學習模組
- **五十音圖**: 完整且緊湊的表格，包含平假名、片假名與羅馬拼音。
- **筆順動畫**:
  - 使用 `dmak.js` 與 KanjiVG 資料。
  - 在詳細教學頁面中，可觀看筆順書寫動畫。
- **語音/發音**:
  - 使用 Web Speech API (`window.speechSynthesis`)。
  - 點擊任何假名或單字即可聆聽發音。
  - 系統會優先選擇 "Google Japanese" 或原生 `ja-JP` 語音，並調整語速與音調以利學習。

## 技術細節
- **框架**: [reveal.js](https://revealjs.com/)
- **筆順**: [dmak.js](https://github.com/mbilbille/dmak) + [KanjiVG](https://kanjivg.tagaini.net/)
- **字型**: Google Fonts
- **部署**: 純靜態 HTML (可部署於 GitHub Pages)

## 安裝與執行
1. Clone 此專案。
2. **執行本地端 Web Server** (由於 CORS 限制，必須透過 Web Server 開啟)：
   ```bash
   # 使用 Python 3
   python3 -m http.server 8000
   ```
3. 在瀏覽器中打開 `http://localhost:8000/src/`。

   > **注意**: 您無法直接用瀏覽器開啟 `src/index.html` 檔案，因為程式需要讀取外部 Markdown 檔案 (`slides.md`)，這會被瀏覽器的 CORS 安全策略擋下 (file:// 協定不支援)。

## 專案背景
本專案的發展歷程與技術嘗試記錄於 [專案發展歷程](doc/DEVELOPMENT_HISTORY.md)。

## 授權
MIT
