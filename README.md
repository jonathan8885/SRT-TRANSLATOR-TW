# 字幕翻譯室 · SRT EN → 台灣繁體中文

一個單一 HTML 檔的小工具：把英文 `.srt` 字幕翻成**台灣慣用語**的繁體中文，翻完可以在表格裡逐句修改，再下載成新的 `.srt`。

A single-file, in-browser tool that translates English `.srt` subtitles into Traditional Chinese (Taiwan usage). Two engines: a free on-device one (Chrome's built-in Translator API) and an optional higher-quality one (bring your own Anthropic API key). No server, no build step.

> 這是個人作品，不是 Anthropic 或 Google 的官方產品。

## 兩種翻譯引擎

| | 免費・Chrome 內建翻譯 | 進階・Claude |
|---|---|---|
| 需要什麼 | 桌面版 Chrome（或支援的 Edge） | 自己的 Anthropic API key |
| 費用 | 免費 | 依 API 用量，算在你自己的帳戶 |
| 字幕會不會上傳 | 不會，在你的電腦上翻譯 | 會，直接送到 Anthropic 的 API |
| 風格選項 | 不支援 | 自然口語／正式書面／戲劇化 |
| 品質 | 草稿級，語氣偏書面，偶爾誤譯 | 較口語，提示詞針對台灣用語調整 |

免費模式第一次使用要下載語言包（約一分鐘，視網路而定），之後不用再下載。

## 使用方式

1. 開啟網頁：`https://jonathan8885.github.io/SRT-TRANSLATOR-TW/`（或下載 `index.html` 直接用瀏覽器打開）
2. 在「翻譯引擎與連線設定」選擇引擎；選進階引擎的話，到 [Anthropic Console](https://console.anthropic.com/) 建立 API key 並貼上
3. 拖入 `.srt` 檔案，選擇輸出格式，按「開始翻譯」
4. 檢查翻譯：中文欄可以直接點擊修改；同一個錯誤出現很多次的話，用表格上方的「批次修正」一次全部換掉
5. 下載翻譯好的字幕

免費模式會自動把常見的大陸用語換成台灣用語（例如互聯網→網路、視頻→影片），並清掉多餘的空格和句尾句號。這份替換表很保守，只放把握度高的詞，翻完請仍然逐句檢查。

## 隱私與費用

- 免費模式：翻譯完全在你的瀏覽器內進行，字幕不會離開你的電腦。
- 進階模式：你的 API key 和字幕文字會**從你的瀏覽器直接送到 Anthropic 的 API**，這個工具沒有任何自己的伺服器。勾選「記住在這個瀏覽器」才會把金鑰存在本機 localStorage，公用電腦請不要勾選。
- 進階模式的 API 費用算在你自己的帳戶，建議先在 Console 設定用量上限，並用一小段字幕測試。
- 網頁會載入 Google Fonts；如果介意，可以把字型連結移除，不影響功能。

## 使用範圍

請只處理你有權使用或翻譯的字幕（例如自己的作品、已取得授權的內容、公有領域或明確允許翻譯的素材）。這個專案不提供也不收錄任何影視作品的字幕檔。

## 限制

- AI 翻譯可能出現誤譯、語氣不一致或漏句，正式使用前請人工校對，尤其是免費模式。
- 免費模式只支援桌面版 Chrome 等支援 Translator API 的瀏覽器；Firefox、Safari 和手機瀏覽器請使用進階模式。
- 免費模式是專門的翻譯模型，一句一句翻、沒有上下文，也可能把粗話翻得比原文溫和。
- 目前只支援標準 SubRip（`.srt`），編碼需為 UTF-8。
- 重新翻譯全部會覆蓋你的人工修改，按下按鈕後需要再按一次確認。

## 回饋

歡迎在 Issues 回報問題或建議。回報時請不要貼上受版權保護的完整字幕內容。

## 授權

MIT License，見 [LICENSE](LICENSE)。
