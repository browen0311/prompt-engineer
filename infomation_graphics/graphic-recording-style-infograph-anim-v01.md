# 圖像紀錄風格資訊圖表轉換提示詞 V5

## 目的
請將以下內容轉換成運用**大型Font Awesome圖示**和**手繪風格對話框**的繁體中文(依臺灣慣用繁體中文用語及標點符號)圖像紀錄風格HTML資訊圖表。在每張卡片中放置一個大型圖示，並積極使用小型內嵌圖示，使資訊以視覺方式更容易理解。

## 設計規格
### 1. 色彩配置
```
<palette>
<color name='UI/UX-1' rgb='1B6C8C' r='26' g='108' b='140' />
<color name='UI/UX-2' rgb='BF8136' r='191' g='129' b='53' />
<color name='UI/UX-3' rgb='F2E8E4' r='242' g='231' b='227' />
<color name='UI/UX-4' rgb='260101' r='38' g='0' b='0' />
<color name='UI/UX-5' rgb='BF5656' r='191' g='86' b='86' />
</palette>
```

### 2. 圖像紀錄元素（改良版）
- 整體放置在白色背景（#FFF8F5）的畫布上
- **每張卡片配置一個超大尺寸的主題圖示**（fa-5x左右）
- **卡片內容以小型圖示清單格式**結構化
- 使用**手繪風格對話框**添加重點或補充資訊
- 將內容分成多個區塊，以卡片形式整理
- 以標籤形式視覺化強調關鍵字
- 以預覽形式顯示程式碼範例
- 連接相關概念的視覺元素（箭頭或線條）
- 使用動畫效果強調各卡片（可應用於任意部分）
- 增加卡片內部資訊量，並用小型圖示視覺化整理

### 3. 排版
  - 標題：36px、#333333（文字顏色）、粗體、超大相關圖示（fa-6x以上）
  - 卡片標題：24px、#555555、較大圖示（fa-5x）
  - 清單標題：18px、#333333
  - 清單項目：16px、#333333、附小型圖示
  - 標籤：16px、#333333、帶背景色
  - 內文：16px、#333333、行距1.5
  - 程式碼預覽：14px、等寬字體、帶背景色
  - 對話框內文字：手寫風格字體、15px、#333333
  - 日期和補充說明：14px、#777777
  - 字體指定：
    ```html
    <style>
    @import url('https://fonts.googleapis.com/css2?family=Kaisei+Decol&family=Yomogi&family=Zen+Kurenaido&display=swap');
    @import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css');
    </style>
    ```

### 4. 版面配置（改良版）
  - 整體：**4欄式結構**（支援響應式設計）
  - 頁首：超大型圖示標題（fa-7x）＋日期
  - 各卡片：一個大型圖示＋清單形式內容＋對話框
  - 卡片內部：以結構化清單形式整理資訊
  - 程式碼預覽：等寬字體、帶背景色的預覽形式
  - 留白：確保足夠留白提高可讀性
  - 寬度：100%（最大約2000px並置中）

### 5. 對話框與標籤表現
- **手繪風格對話框**：3種變化（標準、變化1、變化2）
- **位置變化**：從上部/左右/下部延伸的對話框使版面多樣化
- **標籤表現**：以標籤風格設計強調關鍵字或程式碼範例
- **手寫字體**：使用「Yomogi」等中文手寫風格字體
- **圖示裝飾**：在對話框內也放置小型圖示

### 6. 動畫效果
- **各卡片大型圖示加入動畫**（fa-beat-fade、fa-bounce、fa-flip等）
- 卡片出現時的淡入縮放動畫
- 重要關鍵字出現時的強調效果
- 背景色變化動畫（滑鼠懸停時）
- 捲動相關的卡片出現效果

## 圖示運用指南（改良版）
- 每張卡片的大型圖示（僅限一個）：
  - 主要概念：**fa-5x～fa-7x**（置於卡片中心）
  
- 清單項目的小型圖示：
  - 內嵌圖示：**fa-lg**（配合文字大小）
  - 概念分類建議圖示：
    - 戀愛・愛情：fa-heart、fa-heart-crack、fa-kiss、fa-hand-holding-heart
    - 人際關係：fa-people-arrows、fa-handshake、fa-users、fa-user-group
    - 情緒：fa-face-smile、fa-face-sad-tear、fa-face-angry、fa-face-surprise
    - 問題：fa-circle-question、fa-question、fa-magnifying-glass
    - 時間・流程：fa-clock、fa-hourglass、fa-calendar、fa-timeline
    - 溝通：fa-comments、fa-message、fa-comment-dots
    - 思考・想法：fa-brain、fa-lightbulb、fa-thought-bubble
    - 正面元素：fa-thumbs-up、fa-check、fa-circle-check
    - 負面元素：fa-thumbs-down、fa-ban、fa-triangle-exclamation
    - 方向性：fa-arrow-right、fa-arrow-left、fa-arrow-up、fa-arrow-down
    - 關聯性：fa-link、fa-handshake、fa-code-branch、fa-network-wired
    - 程式設計：fa-code、fa-terminal、fa-file-code、fa-laptop-code
    - 設定：fa-gear、fa-sliders、fa-screwdriver-wrench、fa-tools
    - 資訊：fa-info-circle、fa-circle-info、fa-book、fa-clipboard
    - 使用範例：fa-code、fa-terminal、fa-laptop、fa-mobile

## HTML/CSS實作重點（改良版）
```css
/* 卡片樣式 */
.section-card {
  flex: 1;
  min-width: 220px;
  max-width: 450px;
  background-color: white;
  border-radius: 20px;
  padding: 15px;
  box-shadow: 5px 5px 15px rgba(0,0,0,0.1);
  position: relative;
  overflow: hidden;
}

/* 卡片內圖示容器 */
.mega-icon-container {
  text-align: center;
  margin: 15px 0;
}

/* 卡片內容 */
.card-content {
  padding: 0 10px 15px;
}

/* 關鍵字清單 */
.keyword-list {
  margin: 15px 0;
  padding: 0;
  list-style-type: none;
}

.keyword-list li {
  margin-bottom: 8px;
  display: flex;
  align-items: flex-start;
}

.keyword-list li i {
  margin-right: 8px;
  color: var(--ui-color-2);
  min-width: 16px;
}

/* 關鍵字標籤 */
.keyword-tag {
  background-color: var(--ui-color-3);
  color: var(--ui-color-4);
  padding: 3px 8px;
  border-radius: 5px;
  margin-right: 5px;
  display: inline-block;
  font-weight: bold;
}

/* 手繪風格對話框 */
.speech-bubble {
  position: relative;
  background: #fff;
  border: 3px solid var(--ui-color-1);
  border-radius: 20px;
  padding: 10px 15px;
  margin: 15px 5px;
  font-family: 'Yomogi', cursive;
  box-shadow: 3px 3px 10px rgba(0,0,0,0.1);
  transform: rotate(-1deg);
}

.speech-bubble::after {
  content: '';
  position: absolute;
  bottom: -13px;
  left: 20px;
  border-width: 12px 8px 0;
  border-style: solid;
  border-color: var(--ui-color-1) transparent;
  display: block;
  width: 0;
}

/* 對話框變化 */
.speech-bubble.right::after {
  left: auto;
  right: 20px;
  transform: rotate(15deg);
}

.speech-bubble.top::after {
  bottom: auto;
  top: -13px;
  border-width: 0 8px 12px;
  transform: rotate(-5deg);
}

.speech-bubble.variant-1 {
  background: #FFF9E3;
  border-color: var(--ui-color-2);
  transform: rotate(1deg);
}

.speech-bubble.variant-1::after {
  border-color: var(--ui-color-2) transparent;
}

.speech-bubble.variant-2 {
  background: #FFE9E9;
  border-color: var(--ui-color-5);
  transform: rotate(-2deg);
}

.speech-bubble.variant-2::after {
  border-color: var(--ui-color-5) transparent;
}

/* 手寫文字 */
.handwritten {
  font-family: 'Yomogi', cursive;
  font-size: 15px;
  line-height: 1.5;
  color: #333;
}

/* 程式碼預覽 */
pre {
  background: #f5f5f5;
  padding: 8px;
  border-radius: 5px;
  font-size: 12px;
  margin-top: 10px;
  overflow-x: auto;
}

/* 響應式設計 */
@media (max-width: 1600px) {
  .section-card {
    min-width: 280px;
  }
}

@media (max-width: 1200px) {
  .section-card {
    min-width: 320px;
  }
}

@media (max-width: 900px) {
  .section-card {
    min-width: 380px;
  }
}

@media (max-width: 768px) {
  .section-layout {
    flex-direction: column;
  }
  
  .section-card {
    width: 100%;
    min-width: auto;
  }
}
```

## 整體指導方針（改良版）
- **每張卡片放置一個大型圖示**，積極使用小型內嵌圖示
- **以清單形式結構化資訊**，提高可讀性和理解度
- 使用**手繪風格對話框**添加重點或補充資訊
- **以標籤形式強調關鍵字**，視覺化突顯
- **以預覽形式顯示程式碼範例**，提高實用性
- 用視覺元素（箭頭或線條）表達資訊關聯性
- 使用動畫強調重要元素
- 保持整體一致性，同時避免單調感
- 以繁體中文為基礎，必要時也使用英文關鍵字

## 範例HTML程式碼（改良版）
```html
<!-- 卡片範例 -->
<div class="section-card fade-in-scale">
  <div class="mega-icon-container">
    <i class="fa-solid fa-code fa-5x" style="color: var(--ui-color-1); animation: fa-bounce 2s;" aria-hidden="true"></i>
    <h2>區段標題</h2>
  </div>
  
  <div class="card-content">
    <ul class="keyword-list">
      <li>
        <i class="fa-solid fa-circle-info" aria-hidden="true"></i>
        <span>清單項目1: <span class="keyword-tag">關鍵字</span></span>
      </li>
      <li>
        <i class="fa-solid fa-lightbulb" aria-hidden="true"></i>
        <span>清單項目2</span>
      </li>
      <li>
        <i class="fa-solid fa-code" aria-hidden="true"></i>
        <span>程式碼範例:</span>
      </li>
    </ul>
    
    <pre>
const sample = {
  title: '範例程式碼',
  description: '以預覽形式顯示'
};</pre>
  </div>
  
  <div class="speech-bubble">
    <span class="handwritten">
      <i class="fa-solid fa-lightbulb fa-lg" style="color: var(--ui-color-2);"></i>
      補充資訊或解釋以
      <br>
      手寫風格對話框表現！
      <br>
      <span class="keyword-tag">重要重點</span>
    </span>
  </div>
</div>
```

---

> Reference
>
> [@Sunwood-ai-labs](https://github.com/Sunwood-ai-labs/MysticLibrary)