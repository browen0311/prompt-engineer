# 教育招生網站生成提示詞 (第三版B - 專業精緻方案)

## AI 任務與角色
你將扮演一位頂尖的網頁設計師與前端開發者，根據以下規格與內容，生成一個完整、可直接部署的單頁響應式教育招生網站 HTML 檔案。請確保代碼簡潔、高效，並充分體現設計美感與使用者體驗。在遵循核心要求的同時，歡迎在細節佈局與視覺呈現上發揮創意。

## 目的
將內容轉換成由頂尖設計師製作的一個視覺吸引、招生效果強的一頁式響應式教育網站，使用提供的色彩配置與設計元素，確保無障礙使用體驗，並融入現代 UI/UX 設計趨勢，提升學生與家長的互動與報名轉換率。

## 設計規格

### 1. 色彩配置
```
<palette name='專業精緻方案'>
  <color name='Edu-1 (主色調 - 現代活力藍 - 日間模式)' rgb='007AFF' r='0' g='122' b='255' />
  <color name='Edu-2 (輔助/強調色 - 亮眼橙色 - 日間模式)' rgb='FF9500' r='255' g='149' b='0' />
  <color name='Edu-3 (背景色 - 淺灰白 - 日間模式)' rgb='F7F9FB' r='247' g='249' b='251' />
  <color name='Edu-4 (文字色 - 深灰黑 - 日間模式)' rgb='222222' r='34' g='34' b='34' />
  <color name='Edu-5 (次要強調色 - 原有亮綠 - 日間模式)' rgb='00C2A0' r='0' g='194' b='160' />
  <color name='Edu-1-Dark (主色調 - 亮眼橙色 - 暗黑模式)' rgb='FF9500' r='255' g='149' b='0' />
  <color name='Edu-2-Dark (輔助/強調色 - 現代活力藍 - 暗黑模式)' rgb='007AFF' r='0' g='122' b='255' />
  <color name='Edu-3-Dark (背景色 - 深灰藍 - 暗黑模式)' rgb='212C42' r='33' g='44' b='66' />
  <color name='Edu-4-Dark (文字色 - 淺灰白 - 暗黑模式)' rgb='F7F9FB' r='247' g='249' b='251' />
  <color name='Edu-5-Dark (次要強調色 - 原有亮綠 - 暗黑模式)' rgb='00C2A0' r='0' g='194' b='160' />
</palette>
```

### 2. 必要技術元素
- Tailwind CSS CDN 整合，支援暗黑模式切換。
- Font Awesome 圖示庫與 Material Icons。
- 完整響應式設計 (RWD)，適配所有裝置。
- 使用 Animate.css 動畫效果 (或使用 Tailwind CSS 內建動畫/自定義動畫) 並結合 Intersection Observer API 觸發動畫。
- 符合 WCAG 2.1 AA 級無障礙標準。
- 支援圖表展示 (Chart.js 整合)。
- 可選用 Preline UI 組件庫中的元素來增強互動性 (例如下拉選單、模態框等)，但主要佈局應自行實現。

### 3. 排版與字體
- 標題：使用無襯線字體 (Noto Sans TC)，大小流動漸變，支援暗黑模式對比。
- 正文：優先閱讀性，行距 1.6-1.8，段落間距適當。
- 強調文字：使用 `Edu-2` (亮眼橙色) 或 `Edu-5` (原有亮綠) 作為強調色，確保對比度。
- 按鈕文字：清晰可讀，足夠對比度，支援懸浮與點擊效果。
- 支援多語言字體，確保繁體中文 (使用 Noto Sans TC) 顯示最佳化。

## 網站區塊結構
*請為各區塊的標題、描述文字、學生姓名等使用具體的、符合情境的佔位符文本（例如，「探索我們的[學程名稱]特色」，「[學生姓名] - [年級/畢業年份]」），以便使用者後續替換。*

### 1. 導航列
- 固定頂部，半透明背景，支援暗黑模式切換按鈕。
- 學校或學程標誌左側，導航選單右側，包含行動號召按鈕 (CTA)。
- 手機版轉為漢堡選單，展開時平滑動畫效果。
- 滾動時背景加深效果，增加陰影，提升層次感。

### 2. 英雄區塊
- 全屏背景圖 (校園或學習場景的抽象視覺或漸層，避免使用真實人物肖像以尊重隱私) 或漸層背景 (支援暗黑模式調整)。
- 大標題 + 副標題組合，文字動畫進場效果，強調學程特色或價值。
- 明確行動號召按鈕 (CTA)，如「立即報名」或「了解更多」。
- 圖示化價值展示 (3-4 個核心優勢)，如師資、課程、設施，支援懸浮效果。
- 向下滾動提示箭頭或動畫。

### 3. 學程特色
- 三欄或四欄卡片式設計，支援響應式調整為單欄。
- 每卡片配大型 Font Awesome 或 Material Icons 圖示，代表不同特色。
- 標題、簡短說明與微型 CTA，支援動畫進場效果。
- 卡片懸浮效果，暗黑模式下調整陰影與邊框對比。

### 4. 學生見證/校友分享
- 引用式設計，搭配抽象圖示或學生/校友照片佔位符，支援輪播效果。
- 引用符號使用強調色，背景微妙漸層效果。
- 來源資訊 (如年級或畢業年份) 與評價清晰標示。
- 左右滑動功能 (手機版)，支援觸控操作。

### 5. 資料與成就區塊
- 大字體資料展示，如錄取率、獎項數、畢業生就業率，動畫計數效果 (滾動觸發)。
- 簡短說明文字，支援多語言顯示。
- 使用圖示或 Chart.js 圖表強化視覺傳達，如學生成就統計。
- 支援多資料點展示，響應式調整佈局。

### 6. 招生資訊與行動號召區塊
- 對比鮮明背景，支援暗黑模式調整。
- 大型 CTA 按鈕，如「線上報名」或「下載簡章」，支援多按鈕並排或堆疊。
- 簡潔有力的招生口號，文字動畫效果。
- 輕量級表單 (若需要)，如諮詢表單，支援表單驗證與無障礙標籤。

### 7. 聯絡/頁尾區塊
- 聯絡資訊 (地址、電話、電子郵件) 與社群媒體連結，圖示化顯示。
- 簡短學校或學程介紹，支援多語言切換。
- 版權資訊與隱私政策連結，文字對比清晰。
- 返回頂部按鈕，滾動一定距離後顯示，平滑滾動效果。

## 動畫效果指南
- 進場動畫：元素從下/側向滑入，支援延遲效果。
- 滾動觸發：資訊卡、資料計數動畫，基於 Intersection Observer API。
- 互動效果：按鈕、卡片懸浮狀態變化，平滑過渡。
- 微動畫：圖示旋轉、跳動或脈動效果，吸引注意力。
- 頁面轉場：平滑錨點滾動，支援導航列連結跳轉。

## 招生設計要點
- 視覺層次分明，引導視線流向 CTA，支援視覺引導線索。
- 留白策略性使用，避免資訊過載，提升閱讀舒適度。
- 強調教育價值與成果，聚焦學生與家長關心的問題，如未來發展與學習環境。
- 使用社會認同元素 (見證、成就、合作單位)，增加信任感。
- 製造時效感，如報名截止日期，促進立即行動。
- 降低疑慮表述 (如獎學金、免費體驗課程、校園導覽)，消除報名障礙。

## 無障礙設計要求
- 色彩對比符合 WCAG 2.1 AA 標準，暗黑模式下亦符合。
- 所有圖像提供有意義的 alt 文字 (或對於純裝飾性圖片使用 `alt=""`)，支援螢幕閱讀器。
- 表單元素提供標籤與說明，支援鍵盤導航。
- ARIA 標籤適當使用，提升語義化結構。
- 字體大小可調整，支援瀏覽器縮放。
- 確保動畫效果尊重使用者的 `prefers-reduced-motion` 系統設定。如果偵測到用戶偏好減少動態效果，則應禁用或減弱非必要的動畫。
- 支援高對比模式，確保資訊可讀性。

## 輸出風格與基礎結構參考
*以下提供一個 HTML 檔案的基礎結構、必要的 CDN 引入、以及 Tailwind CSS 的配置範例，作為你生成網站時的風格與技術實現參考。你應基於此範例的技術選型進行擴展，並生成完整的網站內容與佈局。*
```html
<!DOCTYPE html>
<html lang="zh-TW" class="light scroll-smooth dark">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="[學校名稱] - [學程特色與招生資訊]">
  <title>[學校名稱] - [學程招生]</title>
  
  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  
  <!-- Preline UI (Optional, if used) -->
  <!-- <script src="https://cdnjs.cloudflare.com/ajax/libs/preline/1.9.0/preline.min.js"></script> -->
  
  <!-- Font Awesome Icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  
  <!-- Material Icons -->
  <link rel="stylesheet" href="https://fonts.googleapis.com/icon?family=Material+Icons">
  
  <!-- Animate.css -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css">
  
  <!-- Chart.js -->
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  
  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@400;500;700&display=swap" rel="stylesheet">
  
  <script>
    tailwind.config = {
      darkMode: 'class',
      theme: {
        extend: {
          colors: {
            primary: { // Edu-1
              DEFAULT: '#007AFF', 
              dark: '#FF9500' // Edu-1-Dark
            },
            secondary: { // Edu-2
              DEFAULT: '#FF9500',
              dark: '#007AFF' // Edu-2-Dark
            },
            background: { // Edu-3
              DEFAULT: '#F7F9FB',
              dark: '#212C42' // Edu-3-Dark
            },
            text: { // Edu-4
              DEFAULT: '#222222',
              dark: '#F7F9FB' // Edu-4-Dark
            },
            accent: { // Edu-5
              DEFAULT: '#00C2A0',
              dark: '#00C2A0' // Edu-5-Dark
            }
          },
          fontFamily: {
            sans: ['Noto Sans TC', 'sans-serif'],
          }
          // You can add custom animations/keyframes here if not using Animate.css extensively
        }
      }
    }
  </script>
  
  <style>
    /* 自定義樣式補充 - 保持簡潔，優先使用 Tailwind utility classes */
    html {
      scroll-behavior: smooth;
    }
    
    /* Example for Intersection Observer based animations */
    .animate-on-scroll {
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 0.6s ease-out, transform 0.6s ease-out;
    }
    
    .animate-on-scroll.visible {
      opacity: 1;
      transform: translateY(0);
    }
    
    .card-hover {
      transition: all 0.3s ease;
    }
    
    .card-hover:hover {
      transform: translateY(-5px);
      box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.1), 0 8px 10px -6px rgba(0, 0, 0, 0.1);
    }
    
    .btn-hover {
      transition: all 0.2s ease;
    }
    
    .btn-hover:hover {
      transform: scale(1.05);
    }
    
    @media (prefers-reduced-motion: reduce) {
      .animate-on-scroll, 
      .animate-slide-in { /* Assuming .animate-slide-in is a class you might use */
        animation: none !important;
        transition: none !important;
        opacity: 1 !important;
        transform: none !important;
      }
      
      .card-hover:hover, .btn-hover:hover {
        transform: none;
      }
    }
  </style>
</head>

<body class="font-sans bg-background text-text">
  <!-- 網站內容將由 AI 生成 -->
  <!-- 範例 Header (僅供結構參考，AI 應生成完整導航列) -->
  <header class="sticky top-0 z-50 bg-primary/90 dark:bg-primary-dark/90 backdrop-blur-sm border-b border-gray-200 dark:border-gray-700 shadow-sm">
    <div class="container mx-auto px-4 py-3 flex justify-between items-center">
      <div class="flex items-center space-x-2">
        <i class="material-icons text-secondary dark:text-secondary-dark">school</i> <!-- 範例圖示 -->
        <h1 class="text-xl font-bold text-white dark:text-text-dark">[學校Logo/名稱]</h1>
      </div>
      <nav class="hidden md:flex items-center space-x-4">
        <a href="#features" class="text-white dark:text-text-dark hover:text-secondary dark:hover:text-secondary-dark">學程特色</a>
        <a href="#testimonials" class="text-white dark:text-text-dark hover:text-secondary dark:hover:text-secondary-dark">學生見證</a>
        <a href="#contact" class="px-4 py-2 bg-secondary hover:bg-opacity-80 text-white rounded-md transition-colors btn-hover">立即報名</a>
      </nav>
      <div class="flex items-center space-x-2">
        <button id="theme-toggle" aria-label="Toggle dark mode" class="p-2 rounded-full hover:bg-white/20 dark:hover:bg-black/20 transition-colors">
          <i class="fa-solid fa-sun text-accent dark:hidden"></i>
          <i class="fa-solid fa-moon text-accent hidden dark:block"></i>
        </button>
        <button class="md:hidden p-2" aria-label="Open menu"> <!-- Mobile menu button -->
            <i class="fa-solid fa-bars text-white dark:text-text-dark"></i>
        </button>
      </div>
    </div>
  </header>

  <!-- 之後的區塊 (英雄區塊, 學程特色等) 將由 AI 根據上方定義的「網站區塊結構」生成 -->
  <!-- AI 應確保所有區塊都包含在內，並使用適當的 Tailwind CSS class 進行樣式設計 -->

  <!-- 腳本 (僅供結構參考，AI 應生成完整 JS 邏輯) -->
  <script>
    document.addEventListener('DOMContentLoaded', function() {
      // 暗黑模式切換邏輯
      const themeToggle = document.getElementById('theme-toggle');
      const htmlEl = document.documentElement;

      // Load saved theme from localStorage or default to system preference
      const savedTheme = localStorage.getItem('theme');
      if (savedTheme === 'dark' || (!savedTheme && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
        htmlEl.classList.add('dark');
      } else {
        htmlEl.classList.remove('dark');
      }

      themeToggle.addEventListener('click', function() {
        htmlEl.classList.toggle('dark');
        localStorage.setItem('theme', htmlEl.classList.contains('dark') ? 'dark' : 'light');
      });

      // Intersection Observer for scroll animations
      const animatedElements = document.querySelectorAll('.animate-on-scroll');
      const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            entry.target.classList.add('visible');
            // Optional: unobserve after animation
            // observer.unobserve(entry.target); 
          }
        });
      }, { threshold: 0.1 }); // Adjust threshold as needed

      animatedElements.forEach(el => observer.observe(el));

      // Smooth scroll for anchor links
      document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function (e) {
          e.preventDefault();
          const targetId = this.getAttribute('href');
          const targetElement = document.querySelector(targetId);
          if (targetElement) {
            targetElement.scrollIntoView({ behavior: 'smooth' });
          }
        });
      });

      // Mobile menu toggle (basic example)
      // AI should implement a more robust version if a汉堡菜单is complex
      const mobileMenuButton = document.querySelector('button[aria-label="Open menu"]'); // Or a more specific selector
      const nav = document.querySelector('header nav'); // Assuming this is the nav to toggle
      if(mobileMenuButton && nav) {
        mobileMenuButton.addEventListener('click', () => {
            nav.classList.toggle('hidden'); // This is a very basic toggle, AI might need a more sophisticated approach
        });
      }

    });
  </script>
</body>
</html>
```

## 輸出要求
- 請生成單一完整的 HTML 檔案，包含所有必要的 CSS (主要通過 Tailwind CSS class 實現，輔以少量內聯 `<style>` 中的自定義樣式) 和 JavaScript (內聯 `<script>`)。
- 確保 HTML 結構語義化且良好註釋 (例如，標註各主要區塊的開始與結束)。
- 所有外部資源 (CDN) 應正確引入且使用 HTTPS。
- 網站應在主流瀏覽器 (Chrome, Firefox, Safari, Edge) 的最新版本上表現一致。
