# 提示詞工程 (Prompt Engineer) 專案

> [!NOTE]
> **作者**：CXPhoenix
>
> **靈感與參考來源**：
> *   [Pikalai](https://hackmd.io/@pikalai/rymtrelTJe)
> *   [Sunwood-ai-labs](https://github.com/Sunwood-ai-labs/MysticLibrary)
> *   [LangGPT](https://github.com/langgptai/awesome-deep-research-prompts)

## 專案簡介

本專案是一個精心打造的「提示詞 (Prompt) 資源庫」，旨在提供一系列高品質、結構化且符合台灣慣用繁體中文語境的提示詞模板。無論您是內容創作者、設計師、開發者，還是研究人員，都能在此找到適用於各種 AI 生成任務的強力工具，涵蓋領域包括：

*   **視覺化內容生成**：資訊圖表、專業投影片、書籍內頁設計。
*   **內容創作**：撰寫風格自然、宛如真人般的文章。
*   **專案與研究輔助**：高效規劃專案、建構深度研究框架。
*   **網站開發**：快速生成行銷或教育類型網站的完整前端程式碼。
*   **開發者工具**：提供程式碼開發、身分驗證整合的結構化指南。

本專案的目標是成為一個實用且易於擴充的知識庫，讓使用者能輕鬆地客製化與應用提示詞，從而顯著提升工作效率與產出品質。

## 主要特色

*   **多元化應用場景**：涵蓋從視覺設計到軟體開發的廣泛需求。
*   **台灣繁體中文優化**：所有提示詞與說明文件均使用台灣使用者習慣的語彙和表達方式，確保溝通無礙。
*   **結構化與模組化**：提示詞設計清晰，易於理解、修改與擴充。
*   **整合最佳實踐**：融合業界頂尖的設計原則與開發實務，例如響應式網頁設計 (RWD)、無障礙網頁標準 (WCAG) 等。
*   **持續更新**：專案將不斷納入新的提示詞與應用範例。

## 如何使用

1.  **瀏覽目錄**：透過下方的「可用提示詞總覽」尋找您需要的提示詞類型。
2.  **點擊查閱**：點擊連結，查看該提示詞的詳細規格、設計原則與使用範例。
3.  **複製與客製化**：將提示詞模板複製到您的 AI 生成平台（如 Google Gemini, ChatGPT, Claude 等）。
4.  **填入您的內容**：根據提示詞的指引，填入您自己的主題、資料或具體需求。
5.  **生成與迭代**：執行生成，並根據產出結果微調您的輸入內容或提示詞參數，以達到最佳效果。

## 可用提示詞總覽

本資源庫已整理多種提示詞類型，詳細列表如下：

### ✒️ 文章與寫作

*   [**類人風格文章寫作 (v1)**](article/article-like-human-v1.md)
    *   *用途*：生成一篇風格自然流暢、如同真人對話般的長篇敘事文章。

### 📚 書籍排版

*   [**A4 書籍內頁生成 (Alpha)**](book/a4-book-generate-alpha.md)
    *   *用途*：將原始內容轉換為視覺化、適合印刷的 A4 書籍內頁，並整合 `pdfMake.js`、`Chart.js` 等技術。

### 🔬 深度研究

*   [**深度研究提示詞生成器 (v2, 繁體中文)**](deep_research/deep_research_prompt_generator_zhTW-v02.md)
    *   *用途*：引導使用者透過結構化的「協作學習單」模式，建構出一個用於進行深度主題研究的完整提示詞。
*   [**深度研究提示詞生成器 (v1, 英文)**](deep_research/deep_research_prompt_generator_en-v01.md)
    *   *用途*：英文版的深度研究提示詞建構指南。

### 📊 資訊圖表

*   [**圖像紀錄風格資訊圖表 (動畫版, v1)**](infomation_graphics/graphic-recording-style-infograph-anim-v01.md)
    *   *用途*：將內容轉換為帶有動畫效果、手繪風格的 HTML 資訊圖表。
*   [**圖像紀錄風格資訊圖表 (v1)**](infomation_graphics/graphics-recording-style-infograph-v01.md)
    *   *用途*：生成靜態、手繪風格的 HTML 資訊圖表。
*   [**資訊圖表縮圖 (v1)**](infomation_graphics/information-graphics-thumbnil-v01.md)
    *   *用途*：為部落格文章或影片生成 16:9 比例的高品質資訊圖表風格縮圖。

### 📝 專案管理

*   [**專案規劃助理 (v1, 繁體中文)**](project/project_plan_assistant_zhTW-v01.md)
    *   *用途*：透過系統性的引導，協助使用者建構一份清晰的專案概念書或摘要。

### 🖥️ 投影片生成

*   [**圖像紀錄風格投影片 (v2, 互動版)**](slides_prompts/graphics-record-slides-v02.md)
    *   *用途*：生成具有互動功能、手繪風格的單頁應用程式 (SPA) HTML 投影片，整合 `anime.js` 與 `Chart.js`。
*   [**圖像紀錄風格投影片 (v1)**](slides_prompts/graphics-record-slides-v01.md)
    *   *用途*：生成靜態、手繪風格的 HTML 投影片。
*   [**ISIP 主題風格投影片 (v1)**](slides_prompts/isip-theme-slides-v1.md)
    *   *用途*：根據特定品牌（ISIP.HS）的視覺規格，生成高度客製化的 HTML 簡報應用程式。

### 💬 字幕提取

*   [**SRT 字幕提取 (for Google AI Studio, v1)**](subtitle-extract/subtitle-extract-for-google-ai-studio-v1.md)
    *   *用途*：將語音內容轉換為符合業界標準的 SRT 格式字幕檔案。

### 💻 程式碼與開發

*   [**Claude 程式碼指令 (v1)**](vibe_coding/cluade_code_instruction-v01.md)
    *   *用途*：指導 Claude AI 如何利用 Gemini CLI 的大內容視窗來分析大型程式碼庫。
*   [**Reflex 應用程式開發規範 (v1)**](vibe_coding/reflex_app_and_beanie_and_google_oauth_structure_rules-v01.md)
    *   *用途*：提供一個完整的開發規範，用於建構整合 Reflex 框架、Beanie (MongoDB ODM) 及 Google OAuth 的 Python 網頁應用程式。

### 🌐 網站生成

*   **行銷類型網站**
    *   [**Alpha 版**](website/marketing-website-alpha.md)：專注於基本行銷需求的響應式一頁式網站。
    *   [**Beta 版**](website/marketing-website-beta.md)：強化互動元素與轉換設計的進階版本。
*   **教育招生網站**
    *   [**v1**](website/educational-student-recruit-website-v1.md)：整合 Tailwind CSS 與暗黑模式的基礎版本。
    *   [**v2**](website/educational-student-recruit-website-v2.md)：增強互動性與動畫效果。
    *   [**v3a (清新活力方案)**](website/educational-student-recruit-website-v3a.md)：採用清新活潑的色彩配置與現代 UI/UX 設計。
    *   [**v3b (專業精緻方案)**](website/educational-student-recruit-website-v3b.md)：採用專業穩重的色彩配置，聚焦精緻互動體驗。
*   **知識展示網站**
    *   [**v1**](website/educational-website-for-knowledges-display-v01.md)：專為知識分享與學習資源呈現而設計的視覺化網站。

## 如何貢獻

我們非常歡迎社群的貢獻！如果您有新的提示詞想法，或想改進現有的內容，請遵循以下步驟：

1.  **Fork** 本專案。
2.  建立一個新的分支 (`git checkout -b feature/your-new-prompt`)。
3.  進行您的修改與新增。
4.  提交您的變更 (`git commit -m 'Add some feature'`)。
5.  將分支推送到您的 Fork (`git push origin feature/your-new-prompt`)。
6.  建立一個新的 **Pull Request**，並在描述中詳細說明您的變更。

我們將會審核並合併您的貢獻。

## 授權條款

本專案採用 [MIT 授權](LICENSE)。歡迎自由使用與分享。
