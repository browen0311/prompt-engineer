### **研習簡報內容規劃：大語言模型簡報術**
**副標題：** 專為中小學教師設計的 AI 增能實作坊

---

### **第一部分：觀念建立 - 為什麼這對我們重要？ (約 15 分鐘)**

這部分旨在快速建立共識，用最淺顯的方式讓老師們理解核心概念，並感受到 LLM 的價值。

#### **【投影片 1: 封面頁 & 研習破冰】**
*   **標題：** 大語言模型簡報術
*   **副標題：** 格式化產生 HTML 簡報與部屬
*   **引導語：** 「老師們好，備課時間永遠不夠用嗎？今天，我們來學習一項能為您釋放時間、激發創意的新魔法！」
*   **今日目標：**
    1.  認識 LLM 這位教學神隊友。
    2.  **【實作】** 學會從零到一，用 AI 製作一份互動網頁簡報。
    3.  **【帶走】** 掌握一套可重複使用的 Prompt 與自動化部署流程。

#### **【投影片 2: 什麼是大型語言模型 (LLM)？】**
*   **核心概念：** 把 LLM 比喻成「一個讀過全世界圖書館、超會模仿與歸納的語言大師」。
*   **主要內文：**
    *   **定義：** 一種深度學習模型，在海量資料中學習，具備理解、摘要、翻譯及生成內容的能力。
    *   **核心能力：** 不僅懂人類語言，還懂程式碼，這就是我們今天魔法的基礎！
*   **圖像：** 使用您學習單中規劃的「大腦匯入文字、圖片、程式碼」的意象。

#### **【投影片 3: LLM 為何能成為教學神隊友？】**
*   **核心比喻：** 「AI 是您的智慧副駕，幫您處理繁瑣事務，讓身為駕駛的您，專注在教學路線的規劃與跟學生的互動上。」
*   **主要內文（四點核心優勢）：**
    *   **提升備課效率：** 快速生成大綱、講義、題目。
    *   **激發教學創意：** 提供多元視角與活動建議。
    *   **實現個人化學習：** 客製化不同程度的學習材料。
    *   **教材多元化生成：** 從文字到簡報、圖像，豐富教學媒材。
*   **圖像：** 使用您學習單中規劃的「時鐘、燈泡、人群、文件」四個圖示。

---

### **第二部分：實戰演練 - 五步驟打造您的 AI 簡報 (約 60 分鐘)**

這是研習的核心，我們將以一個清晰的「五步驟流程」帶領老師們從頭到尾完成一次簡報製作。

#### **【投影片 4: 我們的創作流程概覽】**
*   **核心概念：** 展示一個清晰的五步驟路線圖，讓老師對接下來的實作環節有全盤的了解。
*   **內容：** 使用動態流程圖 (Flowchart) 呈現：
    1.  **內容規劃** (用 AI 搜集靈感)
    2.  **格式整理** (用 Markdown 餵養 AI)
    3.  **指令詠唱** (撰寫專屬 Prompt)
    4.  **AI 生成** (在 Google AI Studio 施展魔法)
    5.  **網路部署** (一鍵發佈您的作品)

#### **【投影片 5: 步驟一：善用 AI 規劃內容】**
*   **任務：** 「在動手做之前，先讓 AI 幫我們找靈感、擬大綱。」
*   **工具介紹：**
    *   **Felo.ai:** 適合將影音內容快速整理成逐字稿與摘要。
        *   (展示 Felo.ai 的 Logo 圖片: `https://static.felo.ai/felo-search/20250110-101851.webp`)
    *   **Perplexity.ai:** 適合進行資料搜尋與主題探究，並附上資料來源，可信度較高。
        *   (展示 Perplexity.ai 的 Logo 圖片: `https://d1.awsstatic.com/perplexity-logo.fb0a5659778ed3654ffa5604c8feaa92b2d04c20.jpg`)
*   **行動呼籲：** 「請老師們任選一個工具，針對您下學期想教的某個單元，生成一份初步的教學大綱。」

#### **【投影片 6: 步驟二：將內容整理成 Markdown】**
*   **任務：** 「為什麼要用 Markdown？因為它就像是 AI 能最快理解並消化吸收的『標準便當盒』。」
*   **主要內文：**
    *   **結構化：** Markdown 的標題、清單格式，能讓 AI 精準識別內容層次。
    *   **易讀性：** 對人類和機器都清晰易懂。
    *   **提供範本：** 我們已經設計好一份「投影片內容規劃學習單」，請老師們複製並將剛剛的大綱填入。
        *   **範本連結：** `https://drive.google.com/uc?export=download&id=1ybBo0yhJasfq2-__UTybkXtLrik9LuCj`

#### **【投影片 7: 步驟三：撰寫強大的投影片製作 Prompt】**
*   **任務：** 「現在，我們要學習如何下達清晰的『咒語』(Prompt)，讓 AI 精準地為我們工作。」
*   **核心原則 (簡化版 PREP)：**
    *   **角色 (Persona):** 「你是一位...」
    *   **任務 (Request):** 「請幫我製作...」
    *   **規則 (Polish/Rules):** 「必須遵守...格式」、「語氣要...」
    *   **內容 (Examples/Content):** 「資料如下...」 (也就是我們剛剛填好的 Markdown 學習單)
*   **提供範本：** 展示本次研習的核心 Prompt 結構。
    *   **範本連結：** [圖像紀錄風格投影片提示詞 v3](https://github.com/CXPhoenix/prompt-engineer/blob/main/slides_prompts/graphics-record-slides-v03.md)
    *   **提示框：** 「這個 Prompt 已經幫大家把複雜的 HTML/CSS/JS 規則都寫好了，您只需要專注於填寫教學內容！」

#### **【投影片 8: 步驟四：在 Google AI Studio 中生成簡報】**
*   **任務：** 「見證奇蹟的時刻！我們將在 Google AI Studio 這個魔法實驗室中，生成我們的簡報。」
*   **為什麼用 Google AI Studio？**
    *   **優點：** 免費、能使用最新的 Gemini 模型、可調整參數多、適合實驗。
    *   **缺點：** 介面相對單純、需要一些學習。
*   **操作指引 (搭配螢幕操作)：**
    1.  **System Prompt：** 將 v3 提示詞的**「規則部分」**貼入左側的「系統指令」區。這是告訴 AI 它必須遵守的鐵律。
    2.  **User Prompt：** 將 v3 提示詞的**「角色、任務」**以及**「您填寫好的 Markdown 學習單」**，**一次性地**貼入主對話框。
    3.  點擊「執行」，耐心等待 AI 生成完整的 HTML 程式碼。

#### **【投影片 9: 步驟五：一鍵部署！將簡報發佈到網路】**
*   **任務：** 「最後一步，讓您的心血結晶變成一個任何人都能瀏覽的網頁。」
*   **核心工具：** Google 試算表 + Google Apps Script
*   **操作流程 (一步步帶領)：**
    1.  **複製部署範本：** 點擊此連結複製一份專用試算表：
        *   `https://docs.google.com/spreadsheets/d/1zW6C_WYfJIkSgxilGZlZ9xXc1K22i0ldY4qprDWKRwU/copy`
    2.  **貼上程式碼：** 將 Google AI Studio 生成的整段 HTML 程式碼，貼到試算表的指定儲存格 (A2)。
    3.  **進入 App Script：** 點擊「擴充功能」>「Apps Script」。
    4.  **填寫參數：** 在 `Code.gs` 檔案中，將 `SPREADSHEET_ID` 和 `SHEET_NAME` 填入您的試算表資訊。
    5.  **部署與授權：** 點擊「部署」>「新增部署」，並完成授權。
    6.  **大功告成：** 複製產生的 Web App 網址，您的互動簡報已正式上線！

---

### **第三部分：核心心法與未來展望 (約 15 分鐘)**

在實作的興奮後，進行收斂與提醒，確保老師們能正確、長久地應用這項技術。

#### **【投影片 10: 常見挑戰與應對心態】**
*   **常見痛點：**
    *   **模型幻覺：** AI 會一本正經地胡說八道。
    *   **內容偏見：** AI 的回答可能帶有刻板印象。
    *   **知識延遲：** AI 不知道昨天剛發生的事。
*   **教師的應對策略（心態建立）：**
    *   **人類專家置於迴圈中：** 您是最終的把關者，專業判斷無可取代。
    *   **交叉驗證與事實查核：** 對關鍵知識點，務必多方查證。
    *   **AI 是副駕，不是代駕：** 善用它來輔助，而非完全依賴。

#### **【投影片 11: 總結 & Q&A】**
*   **核心價值重申：**
    > 「學習使用 LLM 的目標，從來都不是取代教師，而是將我們從重複性的工作中釋放，讓我們能更專注於**課程設計、師生互動與啟發思考**這些教育的核心價值上。」
*   **實用資源：**
    *   **本次研習 GitHub Repo (所有範本與資源都在此):**
        *   [github.com/CXPhoenix/prompt-engineer](https://github.com/CXPhoenix/prompt-engineer)
    *   **實作平台：**
        *   [Google AI Studio](https://aistudio.google.com/)
*   **開放 Q&A**

---

> [!NOTE]
> 以下為 [Felo.ai](https://felo.ai) 產生的結果。

## 總覽

本研習報告旨在闡述如何運用大型語言模型（LLM）徹底改變教學簡報的製作與呈現方式，特別是針對中小學教師的需求，提供一套從觀念建立到實戰部署的完整解決方案。核心方法是利用 Google AI Studio 的 Gemini 模型，根據結構化的 Markdown 內容，自動生成包含 HTML、CSS 與 JavaScript 的互動式網頁簡報。隨後，透過 Google Apps Script 將此網頁部署為一個可公開存取的網路應用程式，實現零成本、高效率的教材發布流程。

此流程不僅能將教師從繁瑣的簡報排版工作中解放出來，更能激發教學創意，產出形式更多元的數位教材 [[30](https://zhuanlan.zhihu.com/p/688613861)][[46](https://juejin.cn/post/7310412144394584073)]。透過將 AI 定位為「智慧副駕」，教師得以更專注於課程設計、師生互動與啟發思考等教育核心價值 [[50](http://www.jyb.cn/rmtzgjyb/202502/t20250215_2111304035.html)][[70](https://www.ebiotrade.com/newsf/2025-2/20250227073541934.htm)]。本報告將詳細拆解此流程的五大步驟，並提供應對 AI 內在挑戰（如模型幻覺）的實務心法，確保教師能自信且有效地將此創新技術融入日常備課工作中。

## 詳細報告

### **第一部分：建立教學新典範：大型語言模型 (LLM) 的核心價值**

在導入實作技術前，首要任務是建立共識，理解大型語言模型（LLM）為何能成為教育現場的強大盟友。

**大型語言模型 (LLM) 概念解析**

大型語言模型是一種基於深度學習的人工智慧模型，透過在海量的文本與程式碼資料上進行訓練，從而具備理解、歸納、翻譯乃至生成全新內容的卓越能力 [[27](https://aws.amazon.com/tw/what-is/large-language-model/)] [[31](https://www.redhat.com/zh/topics/ai/what-are-large-language-models)] [[39](https://zh.wikipedia.org/zh-hant/%E5%A4%A7%E5%9E%8B%E8%AF%AD%E8%A8%80%E6%A8%A1%E5%9E%8B)]。可將其比喻為一位「讀過全世界圖書館、超會模仿與歸納的語言大師」，它不僅能理解人類的自然語言，更能理解程式語言，這正是實現自動化簡報生成的技術基石 [[66](https://aws.amazon.com/tw/what-is/large-language-model/)][[68](https://www.cloudflare.com/zh-tw/learning/ai/what-is-large-language-model/)]。

目前主流的 LLM（如 Google 的 Gemini 系列）是建立在稱為「Transformer」的神經網路架構之上，使其能夠高效處理複雜的語言模式與上下文關係 [[67](https://www.redhat.com/zh/topics/ai/what-are-large-language-models)][[68](https://www.cloudflare.com/zh-tw/learning/ai/what-is-large-language-model/)]。這使得 LLM 不僅是內容的產生器，更是能理解任務、遵循規則的智慧體。

![以引擎、汽車、工作坊比喻 Gemini、Gemini App 和 Google AI Studio 三者關係[121]](https://zaiwork.com/wp-content/uploads/2025/01/Gemini-01.webp)

**LLM 於教育領域的應用優勢**

將 LLM 視為教師的「智慧副駕」，其價值在於輔助而非取代。它能有效處理重複性與事務性的工作，讓教師能將寶貴的時間與精力投入到更具創造性與互動性的教學環節 [[50](http://www.jyb.cn/rmtzgjyb/202502/t20250215_2111304035.html)][[70](https://www.ebiotrade.com/newsf/2025-2/20250227073541934.htm)]。其核心優勢可歸納為以下四點：

*   **提升備課效率：** LLM 能根據簡單的提示，在短時間內生成教學大綱、課程講義、隨堂測驗題目及活動設計，大幅縮短備課所需時間 [[30](https://zhuanlan.zhihu.com/p/688613861)][[46](https://juejin.cn/post/7310412144394584073)][[69](https://publish.illinois.edu/teaching-learninghub-byjen/benefits-of-llms-in-education/)]。
*   **激發教學創意：** 針對單一主題，LLM 能提供多元的切入視角、創新的教學活動建議，或生成不同風格的教學案例，協助教師突破傳統思維框架 [[45](https://www.microsoft.com/en-us/microsoft-cloud/blog/2024/10/09/5-key-features-and-benefits-of-large-language-models/)][[69](https://publish.illinois.edu/teaching-learninghub-byjen/benefits-of-llms-in-education/)]。
*   **實現個人化學習：** 教師可利用 LLM 快速客製化不同難度、不同深度的學習材料，以適應班級內學生的個別差異，提供更具針對性的學習支持 [[33](https://www.maxiomtech.com/large-language-models-in-education/)][[57](https://springsapps.com/knowledge/how-llm-can-transform-education)][[70](https://www.ebiotrade.com/newsf/2025-2/20250227073541934.htm)]。
*   **教材多元化生成：** LLM 的能力不僅限於文字，更能生成圖像、程式碼，甚至如本研習核心所示，直接產出完整的網頁簡報，豐富教學媒材的呈現形式 [[66](https://aws.amazon.com/tw/what-is/large-language-model/)][[120](https://www.threads.com/@deepsrt.cc/post/DJkuA_KKqsb/%EF%B8%8F-%E4%BD%BF%E7%94%A8gemini-25-pro%E7%94%9F%E6%88%90%E9%AB%98%E9%9A%8E%E7%B6%B2%E9%A0%81%E7%9A%84%E4%B8%89%E6%AD%A5%E9%A9%9F%E9%80%8F%E9%81%8Egoogle-ai-studio%E5%85%88%E8%AE%93%E6%A8%A1%E5%9E%8B%E8%87%AA%E5%8B%95%E8%92%90%E9%9B%86%E7%9B%AE%E6%A8%99%E5%85%AC%E5%8F%B8%E5%A6%82%E9%98%BF%E9%87%8C%E5%B7%B4%E5%B7%B4%E7%9A%84%E8%B2%A1%E5%A0%B1%E8%B3%87%E6%96%99%E6%8E%A5%E8%91%97%E9%80%B2%E8%A1%8C%E5%B0%88%E6%A5%AD%E7%9A%84%E6%95%B8%E6%93%9A%E5%88%86%E6%9E%90%E6%9C%80%E5%BE%8C)]。

### **第二部分：AI 簡報生成實戰：五步驟自動化流程**

本段落為研習的核心實作環節，透過一個清晰的五步驟流程，引導教師從零開始，完成一份AI生成的互動式網頁簡報。

**創作流程概覽**

整個自動化流程涵蓋了從內容發想到最終發布的完整循環，具體步驟如下：
1.  **內容規劃：** 運用 AI 工具搜集靈感與初步資料。
2.  **格式整理：** 將內容整理成 AI 易於理解的 Markdown 格式。
3.  **指令詠唱：** 撰寫結構化、高效率的 Prompt。
4.  **AI 生成：** 於 Google AI Studio 執行 Prompt，生成 HTML 程式碼。
5.  **網路部署：** 透過 Google Apps Script 將 HTML 發布為網頁應用程式。

![Google Apps Script 的程式碼打包（二）包成 HTML 網頁與或 API（2021 鐵人賽 D29）插图[147]](https://coachchiao.com/wp-content/uploads/2025/05/Ik5OVHb.avif)

**步驟一：運用 AI 輔助內容規劃**

在正式製作簡報前，可先利用專業的 AI 工具進行高效的資料搜集與靈感探勘。
*   **Felo.ai:** 此工具適合快速將 YouTube 影片或音訊檔案轉換為逐字稿與內容摘要，便於從影音教材中萃取重點。
*   **Perplexity.ai:** 此工具專長於進行主題式的資料搜尋與探究，其特色是會附上資料來源連結，有助於後續的事實查核，可信度相對較高。

![Felo.ai Logo](https://static.felo.ai/felo-search/20250110-101851.webp)
![Perplexity.ai Logo](https://d1.awsstatic.com/perplexity-logo.fb0a5659778ed3654ffa5604c8feaa92b2d04c20.jpg)

**步驟二：以 Markdown 進行內容結構化**

Markdown 語法是串連人類思維與 AI 理解的關鍵橋樑。其優勢在於它提供了一種對人類和機器都清晰易讀的結構化方式 [[120](https://www.threads.com/@deepsrt.cc/post/DJkuA_KKqsb/%EF%B8%8F-%E4%BD%BF%E7%94%A8gemini-25-pro%E7%94%9F%E6%88%90%E9%AB%98%E9%9A%8E%E7%B6%B2%E9%A0%81%E7%9A%84%E4%B8%89%E6%AD%A5%E9%A9%9F%E9%80%8F%E9%81%8Egoogle-ai-studio%E5%85%88%E8%AE%93%E6%A8%A1%E5%9E%8B%E8%87%AA%E5%8B%95%E8%92%90%E9%9B%86%E7%9B%AE%E6%A8%99%E5%85%AC%E5%8F%B8%E5%A6%82%E9%98%BF%E9%87%8C%E5%B7%B4%E5%B7%B4%E7%9A%84%E8%B2%A1%E5%A0%B1%E8%B3%87%E6%96%99%E6%8E%A5%E8%91%97%E9%80%B2%E8%A1%8C%E5%B0%88%E6%A5%AD%E7%9A%84%E6%95%B8%E6%93%9A%E5%88%86%E6%9E%90%E6%9C%80%E5%BE%8C)]。透過標題（`#`）、清單（`-` 或 `*`）等簡單符號，可以明確定義內容的層級與關係，讓 LLM 在後續生成 HTML 時，能精準地將對應內容放置到正確的投影片標題、內文或項目符號中。這就像是提供給 AI 一個標準化的「便當盒」，讓它能最快速度地消化吸收內容。

**步驟三：建構高效的投影片製作 Prompt**

Prompt（提示詞）是與 LLM 溝通的「咒語」。一個結構清晰的 Prompt 能引導 AI 產出更精準、更符合預期的結果。本次研習採用的核心 Prompt 結構，簡化了 PREP 原則：
*   **角色 (Persona):** 明確賦予 AI 一個專家身分，例如：「你是一位擅長視覺化設計與前端開發的專家」。
*   **任務 (Request):** 清晰下達需要完成的具體工作，例如：「請根據我提供的 Markdown 內容，為我製作一份圖像紀錄風格的單頁式 HTML 互動簡報」。
*   **規則 (Polish/Rules):** 制定嚴格的輸出規範，這部分是技術核心。例如，要求 AI 必須使用特定的 CSS 框架、JavaScript 函式庫，並將所有程式碼（HTML, CSS, JS）都封裝在單一的 `.html` 檔案中。
*   **內容 (Examples/Content):** 提供前一步驟整理好的 Markdown 學習單作為資料來源。

此方法將複雜的前端程式碼規則預先寫入 Prompt 範本，讓教師僅需專注於教學內容的填寫。

**步驟四：於 Google AI Studio 生成簡報程式碼**

Google AI Studio 是一個基於網頁的開發者工具，提供了一個理想的「魔法實驗室」來執行 Prompt 並生成簡報 [[75](https://cloud.google.com/ai/gemini?hl=zh-TW)][[122](https://ai.google.dev/gemini-api/docs/ai-studio-quickstart?hl=zh-tw)]。
*   **主要優勢：** 免費使用、可直接存取最新的 Gemini 模型、提供豐富的參數（如 Temperature）供使用者微調、適合進行快速原型設計與實驗 [[83](https://www.facebook.com/wang.joan.92/posts/%E9%A6%96%E5%85%88google-ai-studio%E6%98%AF%E5%85%8D%E8%B2%BB%E7%9A%84%E4%B8%8D%E7%94%A8%E9%8C%A2%E7%9A%84%E5%8F%AF%E4%BB%A5%E8%96%85%E7%9A%84%E5%86%8D%E4%BE%86-google-ai-studio%E7%9C%9F%E7%9A%84%E5%8F%AF%E4%BB%A5%E7%8E%A9%E7%9A%84%E7%8E%A9%E6%84%8F%E8%B6%85%E5%A4%9A%E7%9A%84%E6%89%80%E4%BB%A5%E6%88%91%E4%B8%8D%E6%9C%83%E8%AC%9Bprompt%E6%80%8E%E9%BA%BC%E4%B8%8B%E6%AF%94%E8%BC%83%E6%9C%89%E7%89%B9%E8%89%B2/25061413426791995/)][[121](https://zaiwork.com/google-ai-studio/)]。
*   **操作流程：**
    1.  **登入與介面：** 使用 Google 帳號即可登入 [[121](https://zaiwork.com/google-ai-studio/)]。介面主要分為系統指令區、主對話框與執行設定區。
    2.  **貼上 Prompt：** 將 Prompt 範本中的「規則部分」貼入左側的「System Instructions」（系統指令）區域。此舉是設定 AI 不可違背的底層規則。
    3.  **提供內容：** 將 Prompt 的「角色、任務」部分，連同已填寫好的「Markdown 內容」，一次性地貼入中央的主對話框。
    4.  **執行與生成：** 點擊「執行」按鈕，AI 將開始處理指令，並在數秒至數分鐘內生成一段完整的 HTML 程式碼。

![Google AI Studio 界面概覽[121]](https://zaiwork.com/wp-content/uploads/2025/01/Google-AI-Studio-2.webp)

**步驟五：透過 Google Apps Script 一鍵部署**

取得 HTML 程式碼後，最後一步是將其發布為一個公開的網頁。Google Apps Script (GAS) 提供了完美的解決方案，它是一種基於雲端的 JavaScript 平台，能與 Google Workspace 應用（如試算表）深度整合，並可將專案部署為網頁應用程式 [[3](https://www.pintech.com.tw/tw/article/575/wow-google-apps-script-tutorial-must-know-amazing-features)][[10](https://realnewbie.com/coding/google-apps-script-doget-function/)][[14](https://gingerdesign.com.tw/google-apps-script-tutorial/)]。
*   **核心原理：** GAS 透過一個名為 `doGet(e)` 的特殊函式來處理來自網路的 GET 請求 [[140](https://realnewbie.com/coding/google-apps-script-doget-function/)][[148](https://realnewbie.com/coding/google-apps-script-doget-function/)]。當使用者訪問部署後的網址時，此函式會被觸發，並回傳一個 `HtmlOutput` 物件，也就是我們的網頁內容 [[2](https://developers.google.com/apps-script/guides/html?hl=zh-tw)][[146](https://developers.google.com/apps-script/guides/html?hl=zh-tw)]。
*   **操作流程：**
    1.  **建立容器：** 複製一份預先設定好的 Google 試算表範本。
    2.  **貼上內容：** 將從 Google AI Studio 生成的完整 HTML 程式碼，貼入試算表的指定儲存格（例如 A2）。
    3.  **開啟腳本編輯器：** 在試算表中，點擊「擴充功能」>「Apps Script」進入編輯環境。
    4.  **設定腳本：** 範本中的 `Code.gs` 檔案已包含讀取儲存格內容並將其作為 HTML 回傳的程式碼。使用者僅需確認試算表 ID 與工作表名稱等參數正確無誤。
    5.  **部署為網頁應用程式：** 點擊編輯器右上角的「部署」>「新增部署」。在設定中，將「誰有存取權」設定為「任何人」，然後點擊部署 [[1](https://coachchiao.com/google-apps-script-build-html-api/)][[129](https://coachchiao.com/google-apps-script-build-html-api/)][[147](https://coachchiao.com/google-apps-script-build-html-api/)]。
    6.  **取得網址：** 完成授權後，系統會產生一個以 `.../exec` 結尾的網址。此網址即為您正式上線的互動簡報。

![在 GAS 中部署網頁應用程式[147]](https://coachchiao.com/wp-content/uploads/2025/05/Ys623oQ.gif)

### **第三部分：核心心法與永續應用**

成功完成技術實作後，建立正確的應用心態與認知其限制，是確保技術能發揮長期效益的關鍵。

**應對 AI 的內建挑戰**

儘管 LLM 功能強大，但其技術本身存在固有挑戰，使用者必須保持警覺 [[68](https://www.cloudflare.com/zh-tw/learning/ai/what-is-large-language-model/)][[70](https://www.ebiotrade.com/newsf/2025-2/20250227073541934.htm)]。
*   **模型幻覺 (Hallucination):** AI 有時會「一本正經地胡說八道」，即在缺乏足夠資訊時，編造看似合理但完全錯誤的內容 [[68](https://www.cloudflare.com/zh-tw/learning/ai/what-is-large-language-model/)]。
*   **內容偏見 (Bias):** 由於訓練資料源於真實世界，AI 的回答可能複製或放大既有的社會偏見與刻板印象 [[70](https://www.ebiotrade.com/newsf/2025-2/20250227073541934.htm)]。
*   **知識延遲 (Knowledge Cutoff):** 大多數 LLM 的知識有其截止日期，無法獲取最新的即時資訊。

**教師的應對策略**

面對上述挑戰，教師應採取以下心態與策略：
*   **人類專家置於迴圈中 (Human-in-the-Loop):** 教師的專業判斷與學科知識是最終的把關者。AI 生成的任何內容，尤其是知識性內容，都必須經過教師的審核與確認。
*   **交叉驗證與事實查核：** 對於 AI 提供的關鍵數據、歷史事件或科學定義，務必透過可靠的第二、第三方來源進行查證。
*   **AI 是副駕，不是代駕：** 善用 AI 處理 80% 的重複性工作，但最終的方向盤必須掌握在自己手中。將 AI 視為提升效率的輔助工具，而非完全依賴的知識權威。

**總結與未來展望**

學習並掌握運用 LLM 生成簡報的技術，其最終目標並非取代教師，而是將教師從耗時的重複性工作中釋放出來 [[54](https://linguaresources.com/%E7%A0%94%E7%A9%B6%E5%8A%A8%E6%80%81-nature%EF%BC%9A%E5%A4%A7%E8%AF%AD%E8%A8%80%E6%A8%A1%E5%9E%8B%E6%AD%A3%E5%9C%A8%E9%87%8D%E5%A1%91%E6%95%99%E8%82%B2%EF%BC%8C%E5%8F%98%E9%9D%A9%E6%97%B6%E5%88%BB/)][[58](http://gccce2024.swu.edu.cn/info/1189/1169.htm)]。當備課的效率大幅提升後，教師將有更多的時間與心力，投入到**課程的深度設計、與學生的情感連結、以及啟發學生的批判性思考**等無法被 AI 取代的教育核心環節上。這項技術賦予了教師一把鑰匙，開啟了通往更高效、更具創意、更個人化教學的未來大門。



1. [Google Apps Script 的程式碼打包（二）包成HTML 網頁與或 ...](https://coachchiao.com/google-apps-script-build-html-api/)
2. [HTML 服務：建立及提供HTML | Apps Script](https://developers.google.com/apps-script/guides/html?hl=zh-tw)
3. [哇!Google Apps Script教學,你不可不知的神奇功能! - 品科技](https://www.pintech.com.tw/tw/article/575/wow-google-apps-script-tutorial-must-know-amazing-features)
4. [HTML 服务：最佳实践| Apps Script - Google for Developers](https://developers.google.com/apps-script/guides/html/best-practices?hl=zh-cn)
5. [HTML サービス: HTML の作成と提供 | Apps Script](https://developers.google.com/apps-script/guides/html?hl=ja)
6. [Apps Script - 擴充Google 簡報檔案](https://developers.google.com/apps-script/guides/slides?hl=zh-tw)
7. [「Google Apps Script」：自動執行](https://workspace.google.com/intl/zh-HK/products/apps-script/)
8. [實作Google 試算表表單串接API (Google Apps Script) - HackMD](https://hackmd.io/@naralala/Vyoj0mf4g)
9. [How to Host a Web Page on Google Apps Script](https://hooshmand.net/host-a-web-page-google-apps-script/)
10. [從零開始：Google Apps Script 中的doGet 函數入門指南](https://realnewbie.com/coding/google-apps-script-doget-function/)
11. [你必須知道的Apps Script技巧,讓你輕鬆開發應用程式 - 品科技](https://www.pintech.com.tw/tw/article/565/apps-script-tips-easy-application-development)
12. [clasp - Apps Script CLI | Google Codelabs](https://codelabs.developers.google.com/codelabs/clasp?hl=zh-tw)
13. [3 時間で学ぶ Google Apps Script 入門 ～スプレッドシートと ...](https://www.seplus.jp/dokushuzemi/blog/2022/03/learn_gas4non_developers.html)
14. [Google Apps Script 是什麼？操作教學 - 野薑設計](https://gingerdesign.com.tw/google-apps-script-tutorial/)
15. [[Day 30] GAS 最終回- 總回顧、限制、資源，下一步該怎麼走](https://ithelp.ithome.com.tw/articles/10365901)
16. [Google Workspace 開發人員支援](https://support.google.com/a/answer/6103110?hl=zh-Hant)
17. [【完全解説】GASでWebアプリを作る方法(簡単なWebページ)](https://gungii.com/gas05-info/?srsltid=AfmBOoqxaJCm8qWeCO4xWQe1OdR6dKWtfqaJYt0M40CtFAkUXBcJZl7q)
18. [Gg / 如何讓Google Apps Script部署的程式接收url參數並呈現 ...](https://tricohobby.net/trico/2693/)
19. [Extending Google Slides | Apps Script - Google for Developers](https://developers.google.com/apps-script/guides/slides)
20. [用Google Apps Script 做的網頁應用程式 - Reddit](https://www.reddit.com/r/GoogleAppsScript/comments/1gl430n/web_app_using_google_apps_script/?tl=zh-hant)
21. [Google Apps ScriptのWebアプリケーションにCSSでスタイル ...](https://tonari-it.com/gas-html-css/)
22. [Google Apps Script 到底是什麼– 實作LINE Bot 打造專屬翻譯機](https://www.wingwill.com.tw/zh-tw/%E9%83%A8%E8%90%BD%E6%A0%BC/google-apps-script-line-bot/)
23. [Google Apps Script で Web アプリを作る](https://www2.kobe-u.ac.jp/~tnishida/programming/GAS-02.html)
24. [透過Google Apps Script製作查詢頁面 - 莊生趣味](https://tricohobby.net/trico/4074/)
25. [Refresh the deployed HTML web page using Google Apps ...](https://stackoverflow.com/questions/50422375/refresh-the-deployed-html-web-page-using-google-apps-script)
26. [Google Apps Script Web App 發布後網址的問題 - 雄::gsyan](https://gsyan888.blogspot.com/2023/12/gas-web-app-url-issue.html)
27. [什麼是LLM？– 大型語言模型說明 - AWS](https://aws.amazon.com/tw/what-is/large-language-model/)
28. [Introduction to Large Language Models | Machine Learning](https://developers.google.com/machine-learning/resources/intro-llms)
29. [Benefits of LLMs in Education - Publish](https://publish.illinois.edu/teaching-learninghub-byjen/benefits-of-llms-in-education/)
30. [大语言模型在教育中的应用:是兴奋剂还是助推器?](https://zhuanlan.zhihu.com/p/688613861)
31. [一文看懂大语言模型是什么？ - Red Hat](https://www.redhat.com/zh/topics/ai/what-are-large-language-models)
32. [What is LLM? - Large Language Models Explained - AWS](https://aws.amazon.com/what-is/large-language-model/)
33. [Large Language Models in Education: Empower Success](https://www.maxiomtech.com/large-language-models-in-education/)
34. [探究人工智能在教育领域的应用——以大语言模型为例原创](https://blog.csdn.net/2401_83740084/article/details/144706535)
35. [LLM 是什麼？LLM 快速入門：大型語言模型的定義與應用指南](https://solwen.ai/posts/what-is-large-language-model)
36. [What are Large Language Models? | A Comprehensive LLMs ...](https://www.elastic.co/what-is/large-language-models)
37. [The Impact of LLM on Education: Simplifying AI for Better ...](https://integranxt.com/blog/the-impact-of-large-language-models-on-education-simplifying-ai-for-better-learning/)
38. [大语言模型在教育领域的机遇与挑战：探索智能教育新路径](https://www.ebiotrade.com/newsf/2025-2/20250227073541934.htm)
39. [大型語言模型- 維基百科，自由的百科全書](https://zh.wikipedia.org/zh-hant/%E5%A4%A7%E5%9E%8B%E8%AF%AD%E8%A8%80%E6%A8%A1%E5%9E%8B)
40. [What is an LLM (large language model)? - Cloudflare](https://www.cloudflare.com/learning/ai/what-is-large-language-model/)
41. [ChatGPT for good? On opportunities and challenges of large ...](https://www.sciencedirect.com/science/article/abs/pii/S1041608023000195)
42. [大型语言模型（LLM）在教育领域的应用及影响 - 飞书文档](https://docs.feishu.cn/v/wiki/CscGwisJfi84vck251pcmR01nqc/a4)
43. [什么是大模型？一文读懂大模型的基本概念 - 知乎专栏](https://zhuanlan.zhihu.com/p/675906726)
44. [A Very Gentle Introduction to Large Language Models without ...](https://mark-riedl.medium.com/a-very-gentle-introduction-to-large-language-models-without-the-hype-5f67941fa59e)
45. [5 key features and benefits of large language models - Microsoft](https://www.microsoft.com/en-us/microsoft-cloud/blog/2024/10/09/5-key-features-and-benefits-of-large-language-models/)
46. [大语言模型在教育行业的应用与未来趋势 - 稀土掘金](https://juejin.cn/post/7310412144394584073)
47. [超白話- 什麼是大語言模型LLM - 方格子](https://vocus.cc/article/6707e5f0fd897800014fbe74)
48. [What Are Large Language Models (LLMs)? - IBM](https://www.ibm.com/think/topics/large-language-models)
49. [Large Language Models in Education: Vision and Opportunities](https://arxiv.org/pdf/2311.13160)
50. [智能体打开教育拥抱大模型的入口](http://www.jyb.cn/rmtzgjyb/202502/t20250215_2111304035.html)
51. [什麼是大型語言模型(LLM)？ - Cloudflare](https://www.cloudflare.com/zh-tw/learning/ai/what-is-large-language-model/)
52. [Large language model - Wikipedia](https://en.wikipedia.org/wiki/Large_language_model)
53. [Large Language Models in E-learning: Advantages and ... - HAL](https://hal.science/hal-04223277v1/document)
54. [Nature：大语言模型正在重塑教育，变革时刻已经到来](https://linguaresources.com/%E7%A0%94%E7%A9%B6%E5%8A%A8%E6%80%81-nature%EF%BC%9A%E5%A4%A7%E8%AF%AD%E8%A8%80%E6%A8%A1%E5%9E%8B%E6%AD%A3%E5%9C%A8%E9%87%8D%E5%A1%91%E6%95%99%E8%82%B2%EF%BC%8C%E5%8F%98%E9%9D%A9%E6%97%B6%E5%88%BB/)
55. [一文了解大模型应用基本概念 - 稀土掘金](https://juejin.cn/post/7506051295952502796)
56. [10 Large Language Model Key Concepts Explained](https://www.kdnuggets.com/10-large-language-model-key-concepts-explained)
57. [How LLM Can Transform Education - Springs](https://springsapps.com/knowledge/how-llm-can-transform-education)
58. [教育大語言模型工作坊 - 第二十八届全球华人计算机教育应用大会](http://gccce2024.swu.edu.cn/info/1189/1169.htm)
59. [大模型基本概念介绍- Naylor - 博客园](https://www.cnblogs.com/Naylor/p/18959690)
60. [Large language models: The basics and their applications](https://www.moveworks.com/us/en/resources/blog/large-language-models-strengths-and-weaknesses)
61. [The Future of Education with Large Language Models (LLMs)](https://medium.com/@sharifghafforov00/the-future-of-education-with-large-language-models-llms-personalized-learning-and-beyond-596d60fa6951)
62. [应用大语言模型快速有效分析教育访谈文本](https://www.ictdedu.cn/sknews/jyxxhs/neirong/n20240122_83261.shtml)
63. [Large Language Model (LLM)大語言模型簡單介紹 - Medium](https://medium.com/@babyodawithlightsaber/llm-%E5%A4%A7%E8%AA%9E%E8%A8%80%E6%A8%A1%E5%9E%8B%E6%A6%82%E8%A6%81-7b77add39372)
64. [What is a Large Language Model (LLM) - GeeksforGeeks](https://www.geeksforgeeks.org/artificial-intelligence/large-language-model-llm/)
65. [AI+Education: How Large Language Models Could Speed ...](https://hai.stanford.edu/news/aieducation-how-large-language-models-could-speed-promising-new-classroom-curricula)
66. [什麼是 LLM？– 大型語言模型說明 – AWS](https://aws.amazon.com/tw/what-is/large-language-model/)
67. [一文看懂大语言模型是什么？](https://www.redhat.com/zh/topics/ai/what-are-large-language-models)
68. [大型語言模型 | 訓練 LLM | Cloudflare](https://www.cloudflare.com/zh-tw/learning/ai/what-is-large-language-model/)
69. [Benefits of LLMs in Education – Jen's Teaching and Learning Hub](https://publish.illinois.edu/teaching-learninghub-byjen/benefits-of-llms-in-education/)
70. [大语言模型在教育领域的机遇与挑战：探索智能教育新路径 - 生物通](https://www.ebiotrade.com/newsf/2025-2/20250227073541934.htm)
71. [️ 使用Gemini 2.5 Pro生成高階網頁的三步驟 - Threads](https://www.threads.com/@deepsrt.cc/post/DJkuA_KKqsb/%EF%B8%8F-%E4%BD%BF%E7%94%A8gemini-25-pro%E7%94%9F%E6%88%90%E9%AB%98%E9%9A%8E%E7%B6%B2%E9%A0%81%E7%9A%84%E4%B8%89%E6%AD%A5%E9%A9%9F%E9%80%8F%E9%81%8Egoogle-ai-studio%E5%85%88%E8%AE%93%E6%A8%A1%E5%9E%8B%E8%87%AA%E5%8B%95%E8%92%90%E9%9B%86%E7%9B%AE%E6%A8%99%E5%85%AC%E5%8F%B8%E5%A6%82%E9%98%BF%E9%87%8C%E5%B7%B4%E5%B7%B4%E7%9A%84%E8%B2%A1%E5%A0%B1%E8%B3%87%E6%96%99%E6%8E%A5%E8%91%97%E9%80%B2%E8%A1%8C%E5%B0%88%E6%A5%AD%E7%9A%84%E6%95%B8%E6%93%9A%E5%88%86%E6%9E%90%E6%9C%80%E5%BE%8C)
72. [Google AI Studioを無料で使い倒す！画像生成・動画分析 ...](https://ai-bo.jp/google-ai-studio/)
73. [Google AI Studio 是什麼? 界面功能教學](https://zaiwork.com/google-ai-studio/)
74. [使用AI 赋能的提示撰写工具| Generative AI on Vertex AI - Google Cloud](https://cloud.google.com/vertex-ai/generative-ai/docs/learn/prompts/ai-powered-prompt-writing?hl=zh-cn)
75. [Google AI Studio、Vertex AI 和Gemini 的比較](https://cloud.google.com/ai/gemini?hl=zh-TW)
76. [Gemini・ImageFX・AI Studioの使い方と活用法【2025年最新】](https://freedoor.co.jp/blog/google-free-generative-ai/)
77. [Google AI Studio のクイックスタート - Gemini API](https://ai.google.dev/gemini-api/docs/ai-studio-quickstart?hl=ja)
78. [用AI打造自己的Blog用HTML程式碼生成器！——不再被編輯器折磨 ...](https://m.facebook.com/groups/1011192722620224/posts/%E7%94%A8ai%E6%89%93%E9%80%A0%E8%87%AA%E5%B7%B1%E7%9A%84-blog%E7%94%A8html%E7%A8%8B%E5%BC%8F%E7%A2%BC%E7%94%9F%E6%88%90%E5%99%A8%E4%B8%8D%E5%86%8D%E8%A2%AB%E7%B7%A8%E8%BC%AF%E5%99%A8%E6%8A%98%E7%A3%A8%E7%82%BA%E4%BB%80%E9%BA%BC%E6%88%91%E9%9C%80%E8%A6%81%E9%80%99%E5%80%8B%E5%B7%A5%E5%85%B7%E7%82%BA%E4%BA%86%E8%AE%93-blogger-%E7%94%A8%E6%88%B6%E6%9B%B4%E8%BC%95%E9%AC%86%E5%9C%B0%E5%89%B5%E4%BD%9C%E6%96%87%E7%AB%A0%E6%88%91%E6%B1%BA%E5%AE%9A%E5%8B%95%E7%94%A8-ai-%E7%9A%84%E5%8A%9B%E9%87%8F%E4%BE%86%E6%89%93%E9%80%A0%E9%80%99/1809261179480037/)
79. [Google AI Studio API密钥：创建、定价和限制](https://zh-cn.extendoffice.com/documents/outlook/7482-how-to-create-google-ai-studio-api-key.html)
80. [Will - 我今年在DevFest Taipei 2023 演講分享【使用Google AI Studio ...](https://www.facebook.com/photo.php?fbid=758618166292275&id=100064322940906&set=a.348225173998245)
81. [Google AI Studio入門：Geminiを使いこなすための基本操作](https://note.com/jerry_ai00/n/n4208fa4b7313)
82. [AI筆記工具-NotebookLM應用簡介 - 計中首頁](https://www.cc.ntu.edu.tw/chinese/epaper/home/News_Content_n_103855_s_250833.html)
83. [完整封裝成你也能實操的工具箱。 課程焦點① 圖像影片產出技巧學會 ...](https://www.facebook.com/wang.joan.92/posts/%E9%A6%96%E5%85%88google-ai-studio%E6%98%AF%E5%85%8D%E8%B2%BB%E7%9A%84%E4%B8%8D%E7%94%A8%E9%8C%A2%E7%9A%84%E5%8F%AF%E4%BB%A5%E8%96%85%E7%9A%84%E5%86%8D%E4%BE%86-google-ai-studio%E7%9C%9F%E7%9A%84%E5%8F%AF%E4%BB%A5%E7%8E%A9%E7%9A%84%E7%8E%A9%E6%84%8F%E8%B6%85%E5%A4%9A%E7%9A%84%E6%89%80%E4%BB%A5%E6%88%91%E4%B8%8D%E6%9C%83%E8%AC%9Bprompt%E6%80%8E%E9%BA%BC%E4%B8%8B%E6%AF%94%E8%BC%83%E6%9C%89%E7%89%B9%E8%89%B2/25061413426791995/)
84. [Google 的AI平台: Google AI Studio - 方格子](https://vocus.cc/article/686495fbfd89780001679734)
85. [Gemini 2.5 Pro使用详解：免费AI Studio保姆级指南，玩转谷歌AI模型](https://www.aihu168.com/archives/2312.html)
86. [【完全ガイド】Google AI Studioとは？使い方や活用方法を ...](https://www.ai-dounyu.com/articles/google-ai-studio)
87. [Google AI Studio 快速上手指南，以實際範例了解如何開始使用 ...](https://ikala.cloud/blog/ai-learing/google-ai-studio-quickstart)
88. [AI筆記工具-NotebookLM應用簡介](https://www.cc.ntu.edu.tw/chinese/epaper/home/20250320_007206.html)
89. [掌握AI簡報工具：提升商務與學術簡報制作的效率](https://www.seoseo.com.tw/article_detail_923.html)
90. [Untitled](https://developers.google.com/womentechmakers/newsletter/202406?hl=zh-cn)
91. [Google AI Studioの使い方を初心者向けに完全解説](https://subscbox.com/gaisdotsukaikatasetsu/)
92. [【保存版】 結局、どの生成AIをどうやって使えばいいのか - note](https://note.com/pogohopper8/n/n5de13b08a5ac)
93. [【超強功能大揭秘！Google AI Studio 】免費生成(融合)圖片、影片](https://vocus.cc/article/682754aafd8978000198d6d6)
94. [Google AI Studio 快速入門導覽課程 - Gemini API](https://ai.google.dev/gemini-api/docs/ai-studio-quickstart?hl=zh-tw)
95. [Google AI Studio Video Gen 快速上手指南(AI生成影片) - 方格子](https://vocus.cc/article/6805b6b1fd89780001c9e4b9)
96. [【Google AI Studio Build × Vibe Coding】使い方をサクッと ...](https://note.com/yakiimo_blog/n/nf5700543afa8)
97. [7.Google AI Studioの基本と使い方 - Zenn](https://zenn.dev/huyu2239/books/4379212c91d382/viewer/66e4a1)
98. [學校補助計畫寫不出來？ #Google AI Studio 一鍵搞定！ ** 各位老師好](https://www.facebook.com/FunFun.AI.Teacher/posts/%E5%AD%B8%E6%A0%A1%E8%A3%9C%E5%8A%A9%E8%A8%88%E7%95%AB%E5%AF%AB%E4%B8%8D%E5%87%BA%E4%BE%86google-ai-studio-%E4%B8%80%E9%8D%B5%E6%90%9E%E5%AE%9A-%E5%90%84%E4%BD%8D%E8%80%81%E5%B8%AB%E5%A5%BD%E6%88%91%E6%98%AF%E6%96%B9%E6%96%B9%E8%80%81%E5%B8%AB%E8%BA%AB%E7%82%BA%E4%B8%80%E5%90%8D%E8%A1%8C%E6%94%BF%E8%80%81%E5%B8%AB%E6%AF%8F%E6%AC%A1%E7%94%B3%E8%AB%8B%E8%A3%9C%E5%8A%A9%E8%A8%88%E7%95%AB%E9%83%BD%E9%A0%AD%E7%97%9B%E4%B8%8D%E5%B7%B2%E6%A0%BC%E5%BC%8F%E8%B6%85%E5%A4%9A%E5%85%A7%E5%AE%B9%E8%B6%85%E9%95%B7%E9%82%84%E8%A6%81%E5%88%86%E6%9E%90%E7%8F%BE%E6%B3%81%E8%A6%8F%E5%8A%83/625549237020493/)
99. [使用您的数据建立依据 | Generative AI on Vertex AI | Google Cloud](https://cloud.google.com/vertex-ai/generative-ai/docs/grounding/grounding-with-your-data?hl=zh-cn)
100. [AI工具集官网| 1000+ AI工具集合，国内外AI工具集导航大全](https://ai-bot.cn/)
101. [Google AI Studioで動画生成を行う方法！料金や注意点も解説](https://shift-ai.co.jp/blog/28760/)
102. [Canva：任何人都能輕鬆上手的Visual Suite](https://www.canva.com/zh_tw/)
103. [AI 生成PPT 簡報只須彈指間！9個字換10頁幻燈片 - 遠距生活](https://wfhlifelab.com/ai-powered-ppt-tools01/)
104. [让工作效率原地起飞！ (Gemini 2.5 Pro + NotebookLM 实战攻略)](https://zhuanlan.zhihu.com/p/1895607359310632898)
105. [【超強功能大揭秘！Google AI Studio 】免費生成(融合)圖片、影片](https://wfhlifelab.com/google-ai-studio/)
106. [Google AI Studioの完全ガイド：初心者から上級者まで ...](https://triggermind.com/ai-development-platform/google-ai-studio-guide/)
107. [Generative AI beginner's guide | Generative AI on Vertex AI | Google ...](https://cloud.google.com/vertex-ai/generative-ai/docs/learn/overview)
108. [Claude.ai](https://claude.ai/)
109. [表單](https://help.asana.com/s/article/forms?language=zh_TW)
110. [如何用Gemini2.5 Pro一键生成高逼格网页和PPT | Google AI Studio ...](https://www.bilibili.com/video/BV1tjTAz9EZb/)
111. [生成式AI 微調與呼叫(Google AI Studio) - HackMD](https://hackmd.io/@PU-X-Discord/%E5%B0%88%E6%A1%88%E5%AF%A6%E4%BD%9C/%2FG-dJzU7eTNO4uvJ5S4plpA)
112. [告別手動更新投影片的惡夢：我如何用AI 高效翻新舊簡報 - CQI 365](https://cqi365.net/2025/04/ai-workflow-presentation-slide-update-gemini/)
113. [Google NotebookLM 免費中文AI 筆記實例教學，老師、學生、創作者 ...](https://www.playpcesor.com/2024/06/google-notebooklm-ai.html)
114. [Wang - 首先，Google AI Studio是免費的，不用錢的，可以薅的！再 ...](https://m.facebook.com/wang.joan.92/photos/%E9%A6%96%E5%85%88google-ai-studio%E6%98%AF%E5%85%8D%E8%B2%BB%E7%9A%84%E4%B8%8D%E7%94%A8%E9%8C%A2%E7%9A%84%E5%8F%AF%E4%BB%A5%E8%96%85%E7%9A%84%E5%86%8D%E4%BE%86-google-ai-studio%E7%9C%9F%E7%9A%84%E5%8F%AF%E4%BB%A5%E7%8E%A9%E7%9A%84%E7%8E%A9%E6%84%8F%E8%B6%85%E5%A4%9A%E7%9A%84%E6%89%80%E4%BB%A5%E6%88%91%E4%B8%8D%E6%9C%83%E8%AC%9Bprompt%E6%80%8E%E9%BA%BC%E4%B8%8B%E6%AF%94%E8%BC%83%E6%9C%89%E7%89%B9%E8%89%B2/25059800173619987/)
115. [透過Gemini 原生音訊，自動生成Podcast 對話(使用Google AI Studio)](https://blog.jiatool.com/posts/gemini_podcast_speech/)
116. [資訊教學資源](https://sh85216s.github.io/Ai-Lan-web/%E8%B3%87%E8%A8%8A%E6%95%99%E5%AD%B8%E8%B3%87%E6%BA%90/index.html)
117. [用Google AI Studio 生成中文版Podcast｜AI 創作新時代來了！](https://cwcchannel.com/2025/05/23/%E7%94%A8-google-ai-studio-%E7%94%9F%E6%88%90%E4%B8%AD%E6%96%87%E7%89%88-podcast%EF%BD%9Cai-%E5%89%B5%E4%BD%9C%E6%96%B0%E6%99%82%E4%BB%A3%E4%BE%86%E4%BA%86%EF%BC%81/)
118. [Google Gemini 免費AI 修圖實測！一句話改圖、換背景、創作連環照片](https://www.playpcesor.com/2025/03/google-gemini-ai.html)
119. [Flourish Studio](https://flourish.studio/)
120. [➡️ 使用Gemini 2.5 Pro生成高階網頁的三步驟

透過Google AI Studio，先讓模型自動蒐集目標公司（如阿里巴巴）的財報資料，接著進行專業的數據分析，最後根據提示詞生成具備動態效果的HTML網頁，並可自訂「便當風格」的視覺設計，使網頁呈現高質感模塊化排版。

➡️ 便當風格設計提升視覺質感

採用類似蘋果網站的「便當風格」（即模塊化豆腐塊排版），搭配簡潔字體與視覺層次，能讓網頁與PPT顯得更專業高級，此風格可靈活套用於財報、課程分享或個人網站等主題。

➡️ 網頁轉PPT的工具與操作流程

利用HTM2Design或CodeDesign插件，將本地HTML網頁轉為PPT格式，再透過Figma微調設計後導出PowerPoint文件，大幅簡化手動製作PPT的流程，保留網頁動態內容並支持進一步編輯。

https://www.youtube.com/watch?v=YEWHNBGIk-I](https://www.threads.com/@deepsrt.cc/post/DJkuA_KKqsb/%EF%B8%8F-%E4%BD%BF%E7%94%A8gemini-25-pro%E7%94%9F%E6%88%90%E9%AB%98%E9%9A%8E%E7%B6%B2%E9%A0%81%E7%9A%84%E4%B8%89%E6%AD%A5%E9%A9%9F%E9%80%8F%E9%81%8Egoogle-ai-studio%E5%85%88%E8%AE%93%E6%A8%A1%E5%9E%8B%E8%87%AA%E5%8B%95%E8%92%90%E9%9B%86%E7%9B%AE%E6%A8%99%E5%85%AC%E5%8F%B8%E5%A6%82%E9%98%BF%E9%87%8C%E5%B7%B4%E5%B7%B4%E7%9A%84%E8%B2%A1%E5%A0%B1%E8%B3%87%E6%96%99%E6%8E%A5%E8%91%97%E9%80%B2%E8%A1%8C%E5%B0%88%E6%A5%AD%E7%9A%84%E6%95%B8%E6%93%9A%E5%88%86%E6%9E%90%E6%9C%80%E5%BE%8C)
121. [Google AI Studio 是什麼? 界面功能教學 - 搞AI的工作室](https://zaiwork.com/google-ai-studio/)
122. [Google AI Studio 快速入門導覽課程  |  Gemini API  |  Google AI for Developers](https://ai.google.dev/gemini-api/docs/ai-studio-quickstart?hl=zh-tw)
123. [Crawl failed](https://www.facebook.com/groups/1011192722620224/posts/%E7%94%A8ai%E6%89%93%E9%80%A0%E8%87%AA%E5%B7%B1%E7%9A%84-blog%E7%94%A8html%E7%A8%8B%E5%BC%8F%E7%A2%BC%E7%94%9F%E6%88%90%E5%99%A8%E4%B8%8D%E5%86%8D%E8%A2%AB%E7%B7%A8%E8%BC%AF%E5%99%A8%E6%8A%98%E7%A3%A8%E7%82%BA%E4%BB%80%E9%BA%BC%E6%88%91%E9%9C%80%E8%A6%81%E9%80%99%E5%80%8B%E5%B7%A5%E5%85%B7%E7%82%BA%E4%BA%86%E8%AE%93-blogger-%E7%94%A8%E6%88%B6%E6%9B%B4%E8%BC%95%E9%AC%86%E5%9C%B0%E5%89%B5%E4%BD%9C%E6%96%87%E7%AB%A0%E6%88%91%E6%B1%BA%E5%AE%9A%E5%8B%95%E7%94%A8-ai-%E7%9A%84%E5%8A%9B%E9%87%8F%E4%BE%86%E6%89%93%E9%80%A0%E9%80%99/)
124. [HTML 服務：建立及提供HTML | Apps Script](https://developers.google.com/apps-script/guides/html?hl=zh-tw)
125. [Apps Script - 擴充Google 簡報檔案](https://developers.google.com/apps-script/guides/slides?hl=zh-tw)
126. [哇!Google Apps Script教學,你不可不知的神奇功能! - 品科技](https://www.pintech.com.tw/tw/article/575/wow-google-apps-script-tutorial-must-know-amazing-features)
127. [實作Google 試算表表單串接API (Google Apps Script) - HackMD](https://hackmd.io/@naralala/Vyoj0mf4g)
128. [How do I include scripts in my Google Apps ... - Stack Overflow](https://stackoverflow.com/questions/48843609/how-do-i-include-scripts-in-my-google-apps-script-google-sheets-html)
129. [Google Apps Script 的程式碼打包（二）包成HTML 網頁與或 ...](https://coachchiao.com/google-apps-script-build-html-api/)
130. [Google Apps Script 是什麼？操作教學 - 野薑設計](https://gingerdesign.com.tw/google-apps-script-tutorial/)
131. [「Google Apps Script」：自動執行](https://workspace.google.com/intl/zh-HK/products/apps-script/)
132. [clasp - Apps Script CLI | Google Codelabs](https://codelabs.developers.google.com/codelabs/clasp?hl=zh-tw)
133. [Google 雲端硬碟：線上分享檔案](https://workspace.google.com/intl/zh-TW/products/drive/)
134. [HTML 服务：最佳实践| Apps Script - Google for Developers](https://developers.google.com/apps-script/guides/html/best-practices?hl=zh-cn)
135. [Google Apps Script 到底是什麼– 實作LINE Bot 打造專屬翻譯機](https://www.wingwill.com.tw/zh-tw/%E9%83%A8%E8%90%BD%E6%A0%BC/google-apps-script-line-bot/)
136. [你必須知道的Apps Script技巧,讓你輕鬆開發應用程式 - 品科技](https://www.pintech.com.tw/tw/article/565/apps-script-tips-easy-application-development)
137. [Google Workspace 開發人員支援](https://support.google.com/a/answer/6103110?hl=zh-Hant)
138. [Apps Script 開發的小幫手. 把你的專案跟Google 服務串接起來 ...](https://medium.com/@Hsu.Yang-Min/apps-script-%E9%96%8B%E7%99%BC%E7%9A%84%E5%B0%8F%E5%B9%AB%E6%89%8B-cd1f15eb722b)
139. [透過Google Apps Script製作查詢頁面 - 莊生趣味](https://tricohobby.net/trico/4074/)
140. [從零開始：Google Apps Script 中的doGet 函數入門指南](https://realnewbie.com/coding/google-apps-script-doget-function/)
141. [Gg / 如何讓Google Apps Script部署的程式接收url參數並呈現 ...](https://tricohobby.net/trico/2693/)
142. [怎麼把Apps Script 部署成Web App？ - Reddit](https://www.reddit.com/r/GoogleAppsScript/comments/q5s95o/how_to_deploy_apps_script_as_web_app/?tl=zh-hant)
143. [Google Apps Script Web App 發布後網址的問題 - 雄::gsyan](https://gsyan888.blogspot.com/2023/12/gas-web-app-url-issue.html)
144. [用Google Apps Script 做的網頁應用程式 - Reddit](https://www.reddit.com/r/GoogleAppsScript/comments/1gl430n/web_app_using_google_apps_script/?tl=zh-hant)
145. [從試算表到網頁：用Google Apps Script 呈現動態數據表格](https://realnewbie.com/coding/google-apps-script-dynamic-table/)
146. [HTML 服務：建立及提供 HTML  |  Apps Script  |  Google for Developers](https://developers.google.com/apps-script/guides/html?hl=zh-tw)
147. [Google Apps Script 的程式碼打包（二）包成 HTML 網頁與或 API（2021 鐵人賽 D29） - Coach 喬的量化求職攻略｜用數據領航您的海外職涯](https://coachchiao.com/google-apps-script-build-html-api/)
148. [從零開始：Google Apps Script 中的 doGet 函數入門指南](https://realnewbie.com/coding/google-apps-script-doget-function/)
149. [哇!Google Apps Script教學,你不可不知的神奇功能!](https://www.pintech.com.tw/tw/article/575/wow-google-apps-script-tutorial-must-know-amazing-features)

