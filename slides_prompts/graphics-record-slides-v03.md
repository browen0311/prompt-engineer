# **圖像紀錄風格投影片提示詞 v3**

## **目的**
本文件旨在引導大型語言模型（LLM）將一份**結構化的數據**，轉換成一份具有親和力、易於理解的**圖像紀錄風格單頁應用程式（SPA）投影片**。

此 Prompt 的核心理念是**「資料與呈現分離」**。首先，我們會定義一個清晰的 JSON 結構來描述資訊流程（例如思維鏈 CoT）；接著，LLM 的任務是根據本文件詳述的設計規格，將這份資料渲染成包含動態效果的視覺化網頁。

此方法適用於教育培訓、會議簡報、知識分享等情境，旨在透過頂尖的資訊視覺化技術，結合手繪風格的溫暖質感與專業的內容架構，讓觀眾能夠快速理解、深度記憶並有效應用所傳達的知識。所有書寫內容皆符合臺灣慣用繁體中文用語及標點符號。

### 動態流程圖生成
* **工作流程**：本 Prompt 的執行分為兩個階段：
  1. **定義資料**：首先，由使用者提供，或由 LLM 根據需求生成一份描述思維鏈、邏輯流程或決策樹的 **JSON 結構化資料**。
  2. **視覺化渲染**：LLM 根據此 JSON 資料，並遵循後述的設計規格，生成包含 HTML, CSS, 和 JavaScript 的完整網頁，特別是使用 `anime.js` 實現動態流程圖。
* **漸進式揭露**：最終生成的流程圖應支援自動播放模式和手動逐步說明模式，讓使用者可以按照自己的節奏理解內容。

## **設計規格**
### **1. 色彩計劃**
```xml
<palette>  
<color name='時尚1' rgb='593C47' r='89' g='59' b='70' />  
<color name='時尚2' rgb='F2E63D' r='242' g='230' b='60' />  
<color name='時尚3' rgb='F2C53D' r='242' g='196' b='60' />  
<color name='時尚4' rgb='F25C05' r='242' g='91' b='4' />  
<color name='時尚5' rgb='F24405' r='242' g='68' b='4' />
</palette>
```
* **主要背景色**：建議使用接近白色的淺色調（例如 #FFFFFF 或 #F8F9FA），以突顯手繪元素和內容。  
* **時尚1 (#593C47)**：主要用於側邊欄背景、部分標題文字、圖示或重點區塊的邊框。  
* **時尚2 (#F2E63D)**：高亮色，可用於關鍵字背景、圖示點綴、小型裝飾圖形。  
* **時尚3 (#F2C53D)**：輔助高亮，可與時尚2搭配使用，或用於圖表、進度條等元素的色彩區分。  
* **時尚4 (#F25C05)**：強調色，適用於行動呼籲按鈕、重要提示的圖示或文字、流程圖中的箭頭。  
* **時尚5 (#F24405)**：次要強調色，可與時尚4搭配，或作為概念標題文字顏色。  
* **文字顏色**：主要內容文字使用深灰色（例如 #334155），確保可讀性。

### **2. 版面結構**
* **整體佈局**：採用雙欄佈局。  
  * **左側**：固定寬度的側邊欄（約佔整體寬度的 20% - 25%），用於目錄和導覽。  
  * **右側**：主要內容區域（約佔整體寬度的 75% - 80%），以投影片形式展示資訊。  
* **響應式設計**：  
  * 在較小螢幕（如平板、手機）上，側邊欄可設計為預設隱藏，透過漢堡選單按鈕觸發展開/收合。  
  * 主要內容區域應能流暢適應不同螢幕寬度。  
* **固定與滾動**：  
  * 側邊欄應固定位置，不隨頁面滾動。  
  * 主要內容區域若單張投影片內容過長，允許垂直滾動；但優先考慮將內容拆分為多張投影片。

### **3. 側邊欄設計**
* **背景**：使用 時尚1 (#593C47) 作為背景色。  
* **標題**：  
  * 網站標題或Logo置於側邊欄頂部中央。  
  * 標題文字顏色可使用 時尚2 (#F2E63D) 或白色，以確保對比度。  
* **導覽選單**：  
  * 列表形式，連結至主要內容的各個部分/投影片。  
  * 每個選單項目前方放置「📌」圖示（可使用 FontAwesome 或 SVG 圖示）。  
  * **當前活動部分**：應有視覺化突顯，例如不同的背景色（可使用 時尚4 (#F25C05) 的較淺版本或增加左邊框）、文字加粗或不同顏色的圖示。  
  * 選單文字顏色建議使用淺色系（如白色或 時尚3 (#F2C53D) 的淺色版），滑鼠懸停 (hover) 時可改變文字或背景顏色以提供反饋。  
* **底部**：可放置版權資訊或相關連結，字體應較小。

### **4. 投影片設計元素**
* **字體風格**：  
  * **中文手寫風格字體**：優先使用 `@import url('https://fonts.googleapis.com/css2?family=Kaisei+Decol:wght@400;500;700&family=Yomogi&family=Zen+Kurenaido&display=swap');`; 中定義的字體。  
    * Yomogi 或 Zen Kurenaido 可用於標題和重點文字，營造手寫感。  
    * Kaisei Decol 可用於內文，兼顧手寫風格與可讀性。  
  * 若上述字體效果不佳或字元不全，可考慮使用「思源黑體 (Noto Sans TC)」、「思源宋體 (Noto Serif TC)」作為備選，並透過 CSS 調整字重和樣式以貼近手寫感。  
    * Noto Sans TC 的 url 為 `https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@100..900&display=swap`
    * Noto Serif TC 的 url 為 `https://fonts.googleapis.com/css2?family=Noto+Serif+TC:wght@200..900&display=swap`
    * 若有需要兩者皆引用，可以使用的 url 為 `https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@100..900&family=Noto+Serif+TC:wght@200..900&display=swap`
* **手繪風格圖形**：  
  * **邊框**：內容區塊、圖片、引用文等可使用手繪風格邊框（例如：不完全平直的線條、雙線、虛線、略帶陰影的邊框）。  
  * **箭頭**：用於指示流程、關聯性，應為手繪樣式（例如：箭頭兩側寬度不均、線條略帶彎曲）。  
  * **橫幅/緞帶**：用於小標題或強調短語，設計成手繪橫幅樣式。  
  * **對話框**：用於引用、註解或人物發言，應為手繪氣泡或對話框樣式。  
  * **分隔線**：使用手繪風格的波浪線、點線或不規則短線。  
* **圖示整合**：  
  * 廣泛使用 FontAwesome 圖示 (確保 v5 或 v6 版本以獲取最新圖示)。  
  * 圖示風格應與手繪感協調，可考慮對圖示應用輕微旋轉、大小不一或手繪邊框效果。  
* **關鍵字強調**：  
  * **彩色底線**：使用 時尚2 (#F2E63D) 或 時尚3 (#F2C53D) 給關鍵字添加波浪形或粗獷的底線。  
  * **標記效果**：模擬螢光筆效果，使用半透明的 時尚2 或 時尚3 作為關鍵字背景。  
* **玻璃擬態效果 (Glassmorphism)**：  
  * 應用於特定內容區塊的背景（例如：次要資訊卡片、圖表背景）。  
  * 效果包含：半透明背景、模糊效果 (backdrop-filter: blur(10px);)、以及細緻的邊框。  
  * 確保在不支援 backdrop-filter 的瀏覽器上有合適的降級處理（例如：純色半透明背景）。

### **5. 組件構成**
* **內容框 (Content Box)**：  
  * **背景**：主要為白色 (#FFFFFF) 或非常淺的米色，以提供最佳閱讀對比。  
  * **圓角**：略微不規則的圓角，或標準圓角 (e.g., border-radius: 8px;) 搭配手繪邊框。  
  * **陰影**：微妙的、略帶擴散的陰影 (box-shadow)，模擬手繪感，避免使用銳利、標準的陰影。可嘗試使用多層陰影或不規則陰影。  
  * **漸層效果**：可選用非常淡的線性漸層作為背景，例如從白色到極淺的 時尚1 衍生色。  
* **手繪風格框 (Hand-drawn Frame)**：  
  * **邊框樣式**：使用雙實線、一實一虛線、或波浪線邊框。顏色可選用深灰色或 時尚1。  
  * **傾斜設計**：可對整個框體或僅邊框應用輕微的 transform: rotate(-1deg); 或 transform: rotate(1deg);，增加手作感。  
* **帶圖示的標題 (Iconic Title)**：  
  * **結構**：FontAwesome 圖示 + 標題文字。  
  * **圖示**：顏色可使用 時尚4 (#F25C05) 或 時尚5 (#F24405)。大小略大於標題文字。  
  * **對齊**：圖示與文字垂直居中對齊。  
* **對話框 (Speech Bubble/Callout)**：  
  * **背景**：白色。  
  * **邊框**：手繪風格，黑色或深灰色。  
  * **箭頭/指示器**：指向相關內容或發言者，同樣為手繪風格。  
  * **用途**：顯示引用、註解、提示或虛擬人物的發言。  
* **圖示容器 (Icon Cluster)**：  
  * **佈局**：將多個相關圖示（2-5個）不規則地組合在一起，形成一個視覺群組，代表一個核心概念。  
  * **背景**：可為每個圖示添加一個手繪圓形或不規則形狀的背景板，顏色可從調色盤中選取。  
  * **排列**：避免死板對齊，可有輕微重疊和角度差異。  
* **備註/提示框 (Note/Tip Box)**：  
  * **左側邊框**：使用 時尚3 (#F2C53D) 或 時尚4 (#F25C05) 的粗邊框 (e.g., border-left: 5px solid;)。  
  * **圖釘圖示**：在左上角或右上角放置「📌」圖示，可稍微傾斜。  
  * **背景**：比主內容框略深的背景色（例如淺灰色或調色盤中顏色的極淡版）。  
* **流程/步驟 (Process/Steps)**：  
  * **排列**：通常為橫向排列，若步驟過多或螢幕空間有限，可改為垂直排列。  
  * **連接線**：使用手繪風格的虛線或帶有箭頭的實線連接各個步驟。線條可略帶彎曲。  
  * **編號/圖示**：每個步驟可使用手繪風格的數字圈或相關圖示標識。

### **6. 文字排版**
* **字體引入**：  
```html
<style>  
  @import url('https://fonts.googleapis.com/css2?family=Kaisei+Decol:wght@400;500;700&family=Yomogi&family=Zen+Kurenaido&display=swap'); 
  body {  
      font-family: 'Kaisei Decol', 'Yomogi', 'Zen Kurenaido', serif; /* 優先使用手寫體 */  
  }  
  /* 可針對不同元素指定不同手寫體 */  
  h1, h2, h3 {  
      font-family: 'Yomogi', 'Zen Kurenaido', sans-serif; /* 標題用較有特色的手寫體 */  
  }  
</style>
```

* **部分標題 (Section Title)**：  
  * **字體大小**：1.5rem 到 2rem。  
  * **顏色**：#1e40af (藍色系，若與整體風格衝突，可改用 時尚1 (#593C47) 或 時尚5 (#F24405))。  
  * **樣式**：可搭配「帶圖示的標題」組件。  
* **概念標題 (Concept Title)**：  
  * **字體**：使用 Yomogi 或 Zen Kurenaido。  
  * **樣式**：粗體 (font-weight: bold;)。  
  * **顏色**：時尚5 (#F24405) 或 時尚4 (#F25C05)。  
  * **大小**：1.2rem 到 1.5rem。  
* **正文 (Body Text)**：  
  * **字體**：使用 Kaisei Decol 或備選的思源宋體/黑體。  
  * **顏色**：#334155 (深灰色)。  
  * **行距 (line-height)**：1.6 到 1.8，確保易讀性。  
  * **大小**：1rem 或 16px 為基準。  
* **引用文字 (Blockquote)**：  
  * **樣式**：斜體 (font-style: italic;)。  
  * **左側邊框**：使用 時尚3 (#F2C53D)，寬度 3px 到 5px。  
  * **內縮**：適當的左側內縮 (padding-left)。  
  * 可搭配「對話框」組件呈現。

### **7. 分頁功能**
* **導覽按鈕**：  
  * 固定在主要內容區域的右下角。  
  * 按鈕文字：「上一頁」、「下一頁」。  
  * **樣式**：按鈕應符合整體手繪風格，例如手繪邊框、使用調色盤中的顏色。  
  * **圖示**：可搭配左右箭頭圖示 (FontAwesome)。  
* **狀態管理**：  
  * **第一頁**：禁用「上一頁」按鈕（例如：降低透明度、改變顏色、移除點擊事件）。  
  * **最後一頁**：禁用「下一頁」按鈕。  
* **鍵盤導覽**：支援使用鍵盤的左右方向鍵 (ArrowLeft, ArrowRight) 切換投影片。

### **8. 動畫與圖表技術整合**

#### **8.1 動畫效果 (Animation Effects)**
* **函式庫引入**:  
  ```html
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"/>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/animejs/3.2.1/anime.min.js"></script>
  ```
* **投影片切換動畫**:  
  * 主要內容區域的投影片切換時，應使用 Animate.css 提供的淡入淡出效果。  
  * **進入動畫**: 新投影片使用 `animate_animated animate_fadeInRight` (從右側淡入) 或 `animate_fadeIn`。  
  * **離開動畫**: 舊投影片使用 `animate_animated animate_fadeOutLeft` (向左側淡出) 或 `animate_fadeOut`。  
  * 動畫速度可設定為 `animate_fast` 或 `animate_faster`。  
* **互動回饋動畫**:  
  * 按鈕、導覽連結等互動元素在滑鼠懸停 (hover) 或點擊 (click) 時，可加入輕微的 Animate.css 動畫，如 `animate_pulse` 或 `animate_headShake` (用於提示)。  
* **動畫原則**: 動畫應增強使用者體驗，不應過度使用或影響內容閱讀。保持動畫的簡潔和目的性。

#### **8.2 圖表呈現 (Chart Presentation)**
* **函式庫引入**:  
```html
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
```
* **使用時機**: 當內容中包含數據比較、趨勢、比例等資訊時，應使用 Chart.js 生成圖表。  
* **圖表類型**: 根據數據特性選擇合適的圖表類型，如長條圖 (bar), 折線圖 (line), 圓餅圖 (pie), 環圈圖 (doughnut), 雷達圖 (radar)。  
* **圖表設計與風格化**:  
  * **容器**: 圖表應在 `<canvas id="myChart"></canvas>` 元素中渲染。  
  * **顏色**:  
    * 圖表的數據系列顏色應從「色彩計劃」中選取，例如 時尚2 到 時尚5 及其衍生色。  
    * 背景色、格線、文字顏色應與整體設計協調，避免與手繪風格衝突。  
  * **字體**: 圖表的標題、圖例 (legend)、工具提示 (tooltip)、座標軸標籤應使用「文字排版」中指定的字體風格，並確保為繁體中文。  
  * **工具提示**: 應清晰顯示數據點的詳細資訊，背景和文字顏色需易於閱讀。  
  * **響應式**: 圖表必須是響應式的 (`responsive: true`, `maintainAspectRatio: false`)，以適應不同螢幕尺寸。  

#### 8.3 資料驅動的動態流程圖 (Data-Driven Dynamic Flowchart)

##### **8.3.1 核心概念：資料與呈現分離**
為確保流程圖生成的穩定性與可維護性，我們採用「資料驅動」的設計模式。LLM 的任務不是憑空創造並編寫動畫，而是將一個預先定義好的、結構化的 **JSON 資料**，轉換為一個動態的視覺化呈現。

##### **8.3.2 資料結構 (Data Structure)**
所有流程圖都必須基於以下 JSON 結構進行渲染。LLM 應先向使用者請求或自行生成此結構，再進行後續的視覺化工作。

*   **`title`**: (可選) 流程圖的標題，將顯示在流程圖的上方。
*   **`nodes`**: 一個陣列，包含所有流程中的步驟節點。
    *   `id`: 節點的唯一標識符。
    *   `content`: 節點中顯示的主要文字。
    *   `notes`: 對此步驟的詳細補充說明，可在互動時顯示。
    *   `position`: 節點在畫布上的 `x` 和 `y` 座標。
*   **`connectors`**: 一個陣列，定義節點之間的連接線。
    *   `id`: 連接線的唯一標識符。
    *   `from`: 連接線的**起點**，對應 `nodes` 中的一個 `id`。
    *   `to`: 連接線的**終點**，對應 `nodes` 中的一個 `id`。

**範例 `flowchartData.json`**:
```json
{
  "title": "專案執行流程",
  "nodes": [
    { "id": "step1", "content": "定義問題", "notes": "釐清核心挑戰與目標。", "position": { "x": 100, "y": 50 } },
    { "id": "step2", "content": "收集資料", "notes": "從多個來源搜集相關資訊。", "position": { "x": 300, "y": 200 } },
    { "id": "step3", "content": "分析與假設", "notes": "基於資料提出可能的解決方案。", "position": { "x": 100, "y": 350 } }
  ],
  "connectors": [
    { "id": "conn1-2", "from": "step1", "to": "step2" },
    { "id": "conn2-3", "from": "step2", "to": "step3" }
  ]
}
```

##### **8.3.3 視覺風格：使用 SVG 模板 (Visual Style: Using SVG Templates)**
為了確保「手繪風格」的一致性與高品質，我們不依賴 CSS 的隨機模擬。應在 HTML 中預先定義好 SVG 模板，並透過 CSS 或 JavaScript 進行調用。

**範例 SVG `defs`**:
```html
<!-- 預先定義好的 SVG 資產，應置於 <body> 開頭 -->
<svg width="0" height="0" style="position:absolute;pointer-events:none;">
  <defs>
    <!-- 手繪風格的箭頭標記 -->
    <marker id="hand-drawn-arrow" viewBox="0 0 10 10" refX="8" refY="5" 
            markerWidth="8" markerHeight="8" orient="auto-start-reverse"
            fill="#F25C05">
      <path d="M 0 0 L 10 5 L 0 10 z" />
    </marker>
    <!-- 手繪風格的節點背景 (可透過 CSS 的 filter: url(#hand-drawn-filter) 使用) -->
    <filter id="hand-drawn-filter">
        <feTurbulence type="fractalNoise" baseFrequency="0.04" numOctaves="5" result="noise"/>
        <feDisplacementMap in="SourceGraphic" in2="noise" scale="5" />
    </filter>
  </defs>
</svg>
```
*   **節點 (Node)**: 應為 SVG `<g>` 元素，包含一個 `<rect>` 或 `<circle>` 和一個 `<text>`。節點的邊框可應用 `filter: url(#hand-drawn-filter);` 來產生不規則抖動效果。
*   **連接線 (Connector)**: 應為 SVG `<path>` 元素，並在 `marker-end` 屬性中設置 `url(#hand-drawn-arrow)` 來應用手繪箭頭。

##### **8.3.4 實現三階段 (Three-Stage Implementation)**
LLM 應遵循以下三個階段來生成流程圖，確保程式碼的結構清晰、易於除錯。

1.  **階段一：靜態渲染 (Static Rendering)**
    *   **任務**：編寫一個函式 `renderFlowchart(data)`。
    *   **輸入**：`flowchartData` JSON 物件。
    *   **輸出**：在指定的 SVG 容器中，根據 `data.nodes` 和 `data.connectors` 生成對應的 SVG 元素 (`<g>`, `<path>` 等)。**如果 `data.title` 存在，應在 SVG 容器上方生成一個 `<h2>` 或 `<h3>` 標題。**
    *   **初始狀態**：所有生成的元素初始 `opacity` 應為 0，為後續動畫做準備。

2.  **階段二：動畫實現 (Animation)**
    *   **任務**：使用 `anime.js` 創建一個動畫時間軸 `timeline`。
    *   **邏輯**：
        *   使用 `anime.timeline()` 創建一個實例，並設置 `autoplay: false`。
        *   遍歷 `flowchartData.nodes`，為每個節點的 SVG 元素添加一個進場動畫 (例如：`opacity: [0, 1]`, `scale: [0.5, 1]`) 到時間軸中。
        *   遍歷 `flowchartData.connectors`，為每個連接線的 SVG `<path>` 元素添加一個「路徑繪製」動畫 (`strokeDashoffset`) 到時間軸中。

3.  **階段三：互動綁定 (Interaction Binding)**
    *   **任務**：創建 HTML 互動按鈕 (e.g., `<button id="playBtn">播放</button>`)。
    *   **邏輯**：
        *   為「播放/暫停」按鈕添加點擊事件監聽器，調用 `timeline.play()` 和 `timeline.pause()`。
        *   為「重置」按鈕添加監聽器，調用 `timeline.restart()` 和 `timeline.pause()`。
        *   (可選) 為「下一步」按鈕添加監聽器，調用 `timeline.seek(timeline.currentTime + 1000)` (假設每個步驟動畫時長為 1 秒) 來手動控制進程。

## **內容表達重點**
* **知識視覺化**: 將複雜的專業知識、數據、流程，透過簡潔明瞭的圖形和圖示轉化為易於理解的視覺資訊。  
* **圖文並茂**: 每個核心概念或數據點都應搭配相關的圖示、插畫或圖表。  
* **手繪親切感**: 整體風格運用手繪元素（邊框、箭頭、字體、圖示處理）營造親和力、降低資訊的嚴肅感。  
* **關聯性表達**: 使用手繪箭頭、連接線、分組框線等方式，清晰表達不同資訊區塊之間的邏輯關係與層次。  
* **案例與引用**: 具體例子、引用名言等，使用對話框、特殊樣式的內容框進行歸納和突出。  
* **關鍵字突顯**: 透過顏色、底線、標記效果等方式，使核心關鍵字易於被使用者捕捉和記憶。  
* **框架化概念**: 重要的概念、模型或結論，使用手繪風格的框架（如內容框、手繪風格框）進行框選強調。  
* **數據簡潔化**: 若不使用圖表，數據資料也應以簡潔、易讀的方式呈現（例如：大數字突出、單位清晰、搭配小圖示）。  
* **故事性與流程感**: 盡可能將資訊組織成具有引導性的閱讀流程，讓使用者能一步步跟隨內容進展。

---

> Reference
>
> Powered by Claude 4-sonnet
>
> Edited by @CXPhoenix
>
> Upgraded to v3 by Gemini AI Assistant based on conversation with @CXPhoenix.
> 
> Idea from [Pikalai](https://hackmd.io/@pikalai/rymtrelTJe)
