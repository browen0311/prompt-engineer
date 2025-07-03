# Gemini CLI Agent Rules - 圖像紀錄風格投影片生成

## 基本設置與行為模式

### 語言設定
- **主要語言**：繁體中文（台灣）
- **標點符號**：使用台灣慣用標點符號
- **專業術語**：優先使用台灣地區通用的技術詞彙

### 輸出行為
- **完整性要求**：必須生成完整的 HTML 檔案，包含所有必要的 CSS 和 JavaScript
- **單一檔案**：所有程式碼應整合在一個 HTML 檔案中，避免外部依賴
- **即時可用**：生成的檔案應能直接在瀏覽器中開啟並正常運作

### 檔案命名規則
- 檔案名稱格式：`slides-[主題]-[日期].html`
- 範例：`slides-project-workflow-20240703.html`
- 檔案編碼：UTF-8

## 資料驅動架構規則

### 強制工作流程
1. **資料定義階段**：
   - 必須先向使用者確認或生成 JSON 結構化資料
   - 資料應包含：`title`, `nodes`, `connectors`
   - 驗證資料完整性和邏輯正確性

2. **視覺化渲染階段**：
   - 基於 JSON 資料生成對應的 SVG 元素
   - 遵循預定義的設計規範
   - 確保響應式佈局

3. **互動功能階段**：
   - 實現自動播放和手動控制
   - 綁定鍵盤導覽功能
   - 添加使用者介面控制項

### JSON 資料結構規範
```json
{
  "title": "流程圖標題",
  "nodes": [
    {
      "id": "唯一標識符",
      "content": "節點顯示文字",
      "notes": "詳細說明",
      "position": { "x": 100, "y": 50 }
    }
  ],
  "connectors": [
    {
      "id": "連接線標識符",
      "from": "起點節點ID",
      "to": "終點節點ID"
    }
  ]
}
```

## 設計規範遵循

### 色彩計劃（強制遵循）
```css
:root {
  --color-fashion-1: #593C47; /* 主要背景色 */
  --color-fashion-2: #F2E63D; /* 高亮色 */
  --color-fashion-3: #F2C53D; /* 輔助高亮 */
  --color-fashion-4: #F25C05; /* 強調色 */
  --color-fashion-5: #F24405; /* 次要強調色 */
  --color-text-primary: #334155; /* 主要文字色 */
  --color-bg-primary: #FFFFFF; /* 主要背景色 */
}
```

### 版面結構要求
- **雙欄佈局**：左側導覽欄（20-25%）+ 右側內容區（75-80%）
- **響應式斷點**：768px 以下使用折疊式導覽
- **固定定位**：側邊欄固定，內容區可滾動

### 字體風格規範
```css
/* 必須引入的字體 */
@import url('https://fonts.googleapis.com/css2?family=Kaisei+Decol:wght@400;500;700&family=Yomogi&family=Zen+Kurenaido&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@100..900&family=Noto+Serif+TC:wght@200..900&display=swap');

/* 字體優先序 */
body {
  font-family: 'Kaisei Decol', 'Noto Sans TC', sans-serif;
}

h1, h2, h3 {
  font-family: 'Yomogi', 'Zen Kurenaido', 'Noto Serif TC', serif;
}
```

## 技術整合規範

### 必要庫文件引用
```html
<!-- 動畫庫 -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/animejs/3.2.1/anime.min.js"></script>

<!-- 圖表庫 -->
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

<!-- 圖示庫 -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
```

### 三階段實作架構
1. **靜態渲染函數**：`renderFlowchart(data)`
2. **動畫時間軸**：`anime.timeline()` 配置
3. **互動控制**：播放/暫停/重置/下一步按鈕

### SVG 手繪風格模板
```html
<svg width="0" height="0" style="position:absolute;pointer-events:none;">
  <defs>
    <marker id="hand-drawn-arrow" viewBox="0 0 10 10" refX="8" refY="5" 
            markerWidth="8" markerHeight="8" orient="auto-start-reverse"
            fill="#F25C05">
      <path d="M 0 0 L 10 5 L 0 10 z" />
    </marker>
    <filter id="hand-drawn-filter">
      <feTurbulence type="fractalNoise" baseFrequency="0.04" numOctaves="5" result="noise"/>
      <feDisplacementMap in="SourceGraphic" in2="noise" scale="5" />
    </filter>
  </defs>
</svg>
```

## 品質控制標準

### 程式碼品質要求
- **語法正確性**：HTML5 標準，CSS3 語法，ES6+ JavaScript
- **跨瀏覽器兼容**：支援 Chrome, Firefox, Safari, Edge
- **效能最佳化**：圖片壓縮，CSS/JS 最小化，載入時間 < 3 秒
- **無障礙設計**：符合 WCAG 2.1 AA 標準

### 功能完整性檢查
- [ ] 投影片可正常切換
- [ ] 動畫效果正常運作
- [ ] 鍵盤導覽功能正常
- [ ] 響應式佈局正確
- [ ] 所有互動按鈕可用
- [ ] 流程圖動畫完整

### 內容品質標準
- **視覺一致性**：所有元素符合手繪風格
- **資訊層次**：清晰的視覺層次結構
- **可讀性**：文字對比度 > 4.5:1
- **美觀度**：色彩搭配和諧，版面平衡

## 使用情境指引

### 教育培訓投影片
- 重點：概念解釋、步驟流程、案例分析
- 建議：多使用圖示、對話框、關鍵字高亮

### 會議簡報
- 重點：數據視覺化、決策流程、行動方案
- 建議：整合圖表、使用進度指示器、突出結論

### 知識分享文件
- 重點：系統化整理、關聯性展示、深度解析
- 建議：使用分組框線、引用對話框、多層次標題

### 流程圖說明
- 重點：邏輯清晰、步驟明確、互動體驗
- 建議：動態揭露、漸進式展示、手動控制選項

## 錯誤處理與降級策略

### 瀏覽器兼容性降級
```css
/* backdrop-filter 降級處理 */
.glass-effect {
  background: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(10px);
}

/* 不支援 backdrop-filter 的瀏覽器 */
@supports not (backdrop-filter: blur(10px)) {
  .glass-effect {
    background: rgba(255, 255, 255, 0.95);
  }
}
```

### JavaScript 錯誤處理
```javascript
// 動畫庫載入失敗處理
if (typeof anime === 'undefined') {
  console.warn('Anime.js 載入失敗，使用 CSS 動畫降級');
  // 實作 CSS 動畫降級方案
}

// 圖表庫載入失敗處理
if (typeof Chart === 'undefined') {
  console.warn('Chart.js 載入失敗，使用靜態圖表');
  // 實作靜態圖表降級方案
}
```

## 輸出確認清單

### 生成前確認
- [ ] 已確認 JSON 資料結構正確
- [ ] 已了解使用情境和目標受眾
- [ ] 已確認技術需求和瀏覽器支援

### 生成後檢查
- [ ] 檔案可正常開啟
- [ ] 所有動畫效果正常
- [ ] 響應式佈局正確
- [ ] 無 JavaScript 錯誤
- [ ] 無 CSS 樣式衝突
- [ ] 內容完整且正確

---

> **版本資訊**
> - 建立日期：2024-07-03
> - 基於：graphics-record-slides-v03.md
> - 適用於：Gemini CLI
> - 維護者：@CXPhoenix