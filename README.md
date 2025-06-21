# 提示詞工程 (Prompt Engineer) 專案

> [!NOTE]  
> **作者**：CXPhoenix
> 
> **參考資料**：
> - Pikalai (https://hackmd.io/@pikalai/rymtrelTJe) [![PikaLai Hackmd](https://img.shields.io/badge/hackmd-Pika_Lai_Hackmd-8A2BE2?logo=Markdown&label=hackmd)](https://hackmd.io/@pikalai/HkvaVkWp1g)
> - Sunwood-ai-labs (https://github.com/Sunwood-ai-labs/MysticLibrary) [![Sunwook-ai-labs Index Page](https://img.shields.io/badge/github-Sunwood--ai--labs-blue?style=plastic&logo=github&logoColor=white&labelColor=black)](https://github.com/Sunwood-ai-labs)

## 簡介
本專案是一個全面的提示詞 (Prompt) 資源庫，專為使用者提供高品質的提示詞模板，用於生成視覺化內容、文章、投影片、資訊圖表及其他專業設計需求。透過本資源庫，您可以輕鬆存取並自訂提示詞，加速創作流程，提升產出品質。所有內容皆以台灣慣用繁體中文用語撰寫，確保語言自然流暢，並符合本地文化與專業標準。

本專案旨在成為開發者、設計師和內容創作者的實用工具，持續更新以涵蓋更多應用場景。如果您是新手，我們的提示詞設計注重易用性；如果您是專業人士，我們提供進階的自訂選項。 ![尚在開發中](https://img.shields.io/badge/%E8%87%AA%E5%AE%9A%E7%BE%A9%E5%85%A7%E5%AE%B9%E9%96%8B%E7%99%BC%E4%B8%AD-(%E4%BD%86%E4%B8%8D%E7%9F%A5%E9%81%93%E4%BB%80%E9%BA%BC%E6%99%82%E5%80%99%E6%9C%83%E5%AE%8C%E6%88%90)-gray?style=flat&labelColor=red)

## 主要特點
- **多樣化提示詞類型**：涵蓋投影片、資訊圖表、書籍生成、專案管理、深度研究及網站設計等多個領域。
- **繁體中文優化**：所有提示詞均使用台灣慣用語彙和表達方式，讓使用者無須額外翻譯即可應用。
- **易於擴充**：資源庫結構化設計，便於貢獻者新增或修改提示詞。
- **專業視覺效果**：提示詞整合了視覺設計原則，如手繪風格、動畫元素和高解析度圖表，協助產生吸引人的輸出。

## 如何使用
1. **瀏覽提示詞**：查看以下目錄中的檔案，選擇適合的提示詞模板。
2. **自訂提示詞**：複製模板並根據需求調整參數，例如變更風格、尺寸或內容細節。
3. **整合工具**：將提示詞應用於 AI 生成平台（如 ChatGPT 或 Midjourney），快速產生內容。
4. **測試與迭代**：生成後，檢查輸出是否符合預期，並根據需要微調提示詞。

例如，若您要生成一張資訊圖表，請參考 `infomation_graphics/graphics-recording-style-infograph-v01.md`，並將其整合到您的生成流程中。

## 目前可用提示詞
本資源庫已整理多種提示詞類型，詳細列表如下。您可以點擊連結查看完整規格：

### 投影片
- [圖像紀錄風格投影片 v01](slides_prompts/graphics-record-slides-v01.md)：轉換內容為手繪風格 HTML 投影片，適合專業簡報。
- [圖像紀錄風格投影片 v02](slides_prompts/graphics-record-slides-v02.md)：更新版本，新增互動元素。
- [ISIP 主題投影片 v1](slides_prompts/isip-theme-slides-v1.md)：以 ISIP 主題設計的投影片，適合特定品牌或活動使用。

### 資訊圖表
- [資訊圖表縮圖 v01](infomation_graphics/information-graphics-thumbnil-v01.md)：生成 16:9 比例的高品質縮圖。
- [圖像紀錄風格資訊圖表 v01](infomation_graphics/graphics-recording-style-infograph-v01.md)：視覺化複雜資訊。
- [圖像紀錄風格資訊圖表動畫 v01](infomation_graphics/graphic-recording-style-infograph-anim-v01.md)：加入動畫效果的版本。

### 文章
- [類似人類撰寫的文章 v01](article/article-like-human-v1.md)：生成自然流暢的文章內容。

### 書籍
- [A4 書籍生成提示詞 - Alpha 版](book/a4-book-generate-alpha.md)：用於教育或專業出版物（測試中）。

### 專案管理
- [專案規劃助理提示詞 v01](project/project_plan_assistant_zhTW-v01.md)：協助產生專案規劃文件。

### 深度研究
- [深度研究提示詞生成器 v01 (繁體中文)](deep_research/deep_research_prompt_generator_zhTW-v01.md)。
- [深度研究提示詞生成器 v02 (繁體中文)](deep_research/deep_research_prompt_generator_zhTW-v02.md)。
- [深度研究提示詞生成器 v01 (英文)](deep_research/deep_research_prompt_generator_en-v01.md)。

### 字幕提取
- [字幕提取 for Google AI Studio v01](subtitle-extract/subtitle-extract-for-google-ai-studio-v1.md)：用於從影片或音頻中提取字幕。

### 程式碼開發
- [Reflex 應用程式結構規則 v01](vibe_coding/reflex_app_and_beanie_and_google_oauth_structure_rules-v01.md)：包含 Beanie 資料庫和 Google OAuth 整合。

### 網站
- **行銷網站**：
  - [Alpha 版本](website/marketing-website-alpha.md)：視覺吸引的一頁式響應式網站，使用專業藍和活力橙金色彩配置，提供無障礙設計 (WCAG 2.1 AA)，強調行銷效果與互動體驗，包括英雄區塊、產品特色展示和行動號召按鈕。
  - [Beta 版本](website/marketing-website-beta.md)：視覺吸引的一頁式響應式網站，強化互動元素，提供無障礙設計 (WCAG 2.1 AA)，聚焦於行銷轉換率，包括動畫效果和顧客見證區塊。
- **教育招生網站**：
  - [版本 1](website/educational-student-recruit-website-v1.md)：基本版本，整合 Tailwind CSS 和暗黑模式，提供無障礙設計 (WCAG 2.1 AA)，強調招生效果。
  - [版本 2](website/educational-student-recruit-website-v2.md)：增強互動性，包含動畫效果和更豐富的互動元素。
  - [版本 3a](website/educational-student-recruit-website-v3a.md)：採用清新活力方案色彩，強調現代 UI/UX 設計。
  - [版本 3b](website/educational-student-recruit-website-v3b.md)：使用專業精緻方案色彩，聚焦教育價值和精緻互動體驗。
- **教育知識展示網站**：
  - [版本 1](website/educational-website-for-knowledges-display-v01.md)：視覺吸引的教育知識展示網站，支援響應式設計和無障礙標準 (WCAG 2.1 AA)，聚焦於知識分享與學習資源呈現。

## 安裝與設定
本專案無需特殊安裝。您可以直接克隆儲存庫並瀏覽檔案：
```
git clone https://github.com/cxphoenix/prompt-engineer.git
cd prompt-engineer
```
如果您要測試提示詞，請確保有 AI 生成工具（如 OpenAI API）設定好。

## 貢獻指南
我們歡迎社區貢獻！若您想新增提示詞或改進現有內容，請遵循以下步驟：
1. Fork 本儲存庫。
2. 建立新分支並進行修改。
3. 提交 Pull Request，並在描述中說明變更細節。
4. 我們將審核並合併您的貢獻。

## 未來規劃
- 擴充更多提示詞類型，例如影片生成和互動式應用。
- 加入使用者回饋機制，讓社區能參與優化。
- 開發自動化工具，簡化提示詞應用流程。

## 授權
本專案採用 MIT 授權。詳細資訊請參閱 LICENSE 檔案（若適用）。

感謝您使用本資源庫！如果有任何問題，請在 Issues 頁面提出。
