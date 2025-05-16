# 行銷型一頁式網站生成提示詞 (進階版)

## 目的
將內容轉換成由頂尖設計師製作的一個視覺吸引、行銷效果強的一頁式響應式網站，使用提供的色彩配置與設計元素，確保無障礙使用體驗，並融入現代 UI/UX 設計趨勢，提升使用者互動與轉換率。

## 設計規格

### 1. 色彩配置
```
<palette>
<color name='UI/UX-1 (主色調 - 專業藍)' rgb='1B6C8C' r='26' g='108' b='140' />
<color name='UI/UX-2 (輔助/強調色 - 活力橙金)' rgb='BF8136' r='191' g='129' b='53' />
<color name='UI/UX-3 (背景色 - 舒適米白)' rgb='F2E8E4' r='242' g='231' b='227' />
<color name='UI/UX-4 (文字色 - 深褐黑)' rgb='260101' r='38' g='0' b='0' />
<color name='UI/UX-5 (次要強調色 - 沉穩紅)' rgb='BF5656' r='191' g='86' b='86' />
</palette>
```

### 2. 必要技術元素
- Tailwind CSS CDN 整合，支援暗黑模式切換
- Font Awesome 圖示庫與 Material Icons
- 完整響應式設計 (RWD)，適配所有裝置
- Animate.js 動畫效果與 Intersection Observer API 觸發動畫
- 符合 WCAG 2.1 AA 級無障礙標準
- 支援圖表展示 (Chart.js 整合)
- Preline UI 組件庫，提升互動體驗

### 3. 排版與字體
- 標題：使用無襯線字體 (Noto Sans TC)，大小流動漸變，支援暗黑模式對比
- 正文：優先閱讀性，行距 1.6-1.8，段落間距適當
- 強調文字：搭配 UI/UX-2 (活力橙金) 色調或 UI/UX-5 (沉穩紅)
- 按鈕文字：清晰可讀，足夠對比度，支援懸浮與點擊效果
- 支援多語言字體，確保繁體中文顯示優化

## 網站區塊結構

### 1. 導航列
- 固定頂部，半透明背景，支援暗黑模式切換按鈕
- 品牌標誌左側，導航選單右側，包含行動號召按鈕 (CTA)
- 手機版轉為漢堡選單，展開時平滑動畫效果
- 滾動時背景加深效果，增加陰影，提升層次感

### 2. 英雄區塊
- 全屏背景圖或漸層背景 (支援暗黑模式調整)
- 大標題 + 副標題組合，文字動畫進場效果
- 明確行動號召按鈕 (CTA)，支援多按鈕選項
- 圖示化價值展示 (3-4 個核心賣點)，卡片式設計，支援懸浮效果
- 向下滾動提示箭頭或動畫

### 3. 產品/服務特色
- 三欄或四欄卡片式設計，支援響應式調整為單欄
- 每卡片配大型 Font Awesome 或 Material Icons 圖示
- 標題、簡短說明與微型 CTA，支援動畫進場效果
- 卡片懸浮效果，暗黑模式下調整陰影與邊框對比

### 4. 顧客見證/案例展示
- 引用式設計，搭配顧客照片/標誌，支援輪播效果
- 引用符號使用強調色，背景微妙漸層效果
- 來源資訊與評分清晰標示，五星評分圖示化
- 左右滑動功能 (手機版)，支援觸控操作

### 5. 資料與成就區塊
- 大字體資料展示，動畫計數效果 (滾動觸發)
- 簡短說明文字，支援多語言顯示
- 使用圖示或 Chart.js 圖表強化視覺傳達
- 支援多資料點展示，響應式調整佈局

### 6. 行動號召區塊
- 對比鮮明背景，支援暗黑模式調整
- 大型 CTA 按鈕，支援多按鈕並排或堆疊
- 簡潔有力的標語，文字動畫效果
- 輕量級表單 (若需要)，支援表單驗證與無障礙標籤

### 7. 聯絡/頁尾區塊
- 聯絡資訊與社群媒體連結，圖示化顯示
- 簡短公司介紹，支援多語言切換
- 版權資訊與隱私政策連結，文字對比清晰
- 返回頂部按鈕，滾動一定距離後顯示，平滑滾動效果

## 動畫效果指南
- 進場動畫：元素從下/側向滑入，支援延遲效果
- 滾動觸發：資訊卡、資料計數動畫，基於 Intersection Observer API
- 互動效果：按鈕、卡片懸浮狀態變化，平滑過渡
- 微動畫：圖示旋轉、跳動或脈動效果，吸引注意力
- 頁面轉場：平滑錨點滾動，支援導航列連結跳轉

## 行銷設計要點
- 視覺層次分明，引導視線流向 CTA，支援視覺引導線索
- 留白策略性使用，避免資訊過載，提升閱讀舒適度
- 強調解決方案而非產品特性，聚焦使用者痛點
- 使用社會認同元素 (見證、標誌、計數)，增加信任感
- 製造稀缺感或時效感，促進立即行動
- 降低風險表述 (保證、試用、退款政策)，消除購買疑慮

## 無障礙設計要求
- 色彩對比符合 WCAG 2.1 AA 標準，暗黑模式下亦符合
- 所有圖像提供 alt 文字，支援螢幕閱讀器
- 表單元素提供標籤與說明，支援鍵盤導航
- ARIA 標籤適當使用，提升語義化結構
- 字體大小可調整，支援瀏覽器縮放
- 動畫可暫停選項，避免干擾使用者
- 支援高對比模式，確保資訊可讀性

## HTML/CSS 框架範例
```html
<!DOCTYPE html>
<html lang="zh-TW" class="light scroll-smooth dark">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="產品名稱 - 核心價值主張">
  <title>產品名稱 - 核心價值主張</title>
  
  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  
  <!-- Preline UI -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/preline/1.9.0/preline.min.js"></script>
  
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
            primary: {
              DEFAULT: '#1B6C8C',
              dark: '#134160'
            },
            secondary: {
              DEFAULT: '#BF8136',
              dark: '#8C5A26'
            },
            background: {
              DEFAULT: '#F2E8E4',
              dark: '#2A2A2A'
            },
            text: {
              DEFAULT: '#260101',
              dark: '#F0F0F0'
            },
            accent: {
              DEFAULT: '#BF5656',
              dark: '#8C3A3A'
            }
          },
          fontFamily: {
            sans: ['Noto Sans TC', 'sans-serif'],
          },
          animation: {
            'fade-in': 'fadeIn 1s ease-in-out',
          },
          keyframes: {
            fadeIn: {
              '0%': { opacity: '0' },
              '100%': { opacity: '1' },
            }
          }
        }
      }
    }
  </script>
  
  <style>
    /* 自定義樣式補充 */
    html {
      scroll-behavior: smooth;
    }
    
    .animate-on-scroll {
      opacity: 0;
      transform: translateY(20px);
      transition: all 0.5s;
    }
    
    .animate-on-scroll.visible {
      opacity: 1;
      transform: translateY(0);
    }
    
    @keyframes slideInFromBottom {
      0% {
        transform: translateY(20px);
        opacity: 0;
      }
      100% {
        transform: translateY(0);
        opacity: 1;
      }
    }
    
    .animate-slide-in {
      animation: slideInFromBottom 0.5s ease-out forwards;
      opacity: 0;
    }
    
    .delay-100 { animation-delay: 0.1s; }
    .delay-200 { animation-delay: 0.2s; }
    .delay-300 { animation-delay: 0.3s; }
    .delay-400 { animation-delay: 0.4s; }
    .delay-500 { animation-delay: 0.5s; }
    
    [data-section] {
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 0.6s ease-out, transform 0.6s ease-out;
    }
    
    [data-section].visible {
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
      .animate-slide-in {
        animation: none;
        opacity: 1;
      }
      
      [data-section] {
        opacity: 1;
        transform: none;
        transition: none;
      }
      
      .card-hover:hover, .btn-hover:hover {
        transform: none;
      }
    }
  </style>
</head>

<body class="font-sans bg-background text-text dark:bg-gray-900 dark:text-gray-100">
  <!-- 頂部導航欄 -->
  <header class="sticky top-0 z-50 bg-primary bg-opacity-90 dark:bg-gray-900 border-b border-gray-200 dark:border-gray-700 shadow-sm">
    <div class="container mx-auto px-4 py-3 flex justify-between items-center">
      <div class="flex items-center space-x-2">
        <i class="material-icons text-secondary dark:text-secondary-dark">school</i>
        <h1 class="text-xl font-bold">品牌名稱</h1>
      </div>
      <div class="flex items-center space-x-4">
        <button id="theme-toggle" class="p-2 rounded-full hover:bg-gray-100 dark:hover:bg-gray-800 transition-colors">
          <i class="fa-solid fa-sun text-yellow-500 dark:hidden"></i>
          <i class="fa-solid fa-moon text-blue-300 hidden dark:block"></i>
        </button>
        <a href="#contact" class="hidden sm:inline-block px-4 py-2 bg-secondary hover:bg-secondary-dark text-white rounded-md transition-colors btn-hover">聯絡我們</a>
      </div>
    </div>
  </header>

  <!-- 英雄區塊 -->
  <section class="py-12 md:py-20 bg-gradient-to-br from-primary to-accent dark:from-gray-900 dark:to-gray-800">
    <div class="container mx-auto px-4">
      <div class="max-w-4xl mx-auto text-center">
        <h1 class="text-3xl md:text-5xl font-bold mb-6 text-white animate-slide-in">
          產品名稱 - <span class="text-secondary dark:text-secondary-dark">核心價值主張</span>
        </h1>
        <p class="text-xl md:text-2xl text-gray-100 mb-8 animate-slide-in delay-100">
          簡短有力的副標題，說明產品或服務如何解決客戶痛點
        </p>
        <div class="flex flex-wrap justify-center gap-4 mb-8 animate-slide-in delay-200">
          <a href="#features" class="px-6 py-3 bg-secondary hover:bg-secondary-dark text-white rounded-md transition-colors btn-hover">
            了解更多
          </a>
          <a href="#contact" class="px-6 py-3 border border-white dark:border-gray-400 text-white hover:bg-gray-100 dark:hover:bg-gray-800 rounded-md transition-colors btn-hover">
            立即聯絡
          </a>
        </div>
      </div>
    </div>
  </section>

  <!-- 產品特色 -->
  <section id="features" class="py-16 visible" data-section="">
    <div class="container mx-auto px-4">
      <div class="max-w-4xl mx-auto">
        <h2 class="text-2xl md:text-3xl font-bold mb-8 text-gray-900 dark:text-white text-center">
          <i class="fas fa-star text-secondary mr-2"></i>產品特色
        </h2>
        <div class="grid md:grid-cols-3 gap-6 mb-12">
          <div class="bg-white dark:bg-gray-800 p-6 rounded-xl shadow-lg border border-gray-100 dark:border-gray-700 card-hover">
            <div class="w-16 h-16 mx-auto flex items-center justify-center rounded-full bg-primary-100 dark:bg-primary-800 mb-4">
              <i class="fas fa-rocket text-primary dark:text-primary-dark text-2xl"></i>
            </div>
            <h3 class="text-xl font-semibold mb-2 text-gray-900 dark:text-white text-center">特色一</h3>
            <p class="text-gray-700 dark:text-gray-300 text-center">
              簡短說明如何幫助客戶解決問題或提升價值。
            </p>
          </div>
          <!-- 更多特色卡片... -->
        </div>
      </div>
    </div>
  </section>

  <!-- 其他區塊... -->

  <!-- 腳本 -->
  <script>
    // 暗黑模式切換
    document.addEventListener('DOMContentLoaded', function() {
      const themeToggle = document.getElementById('theme-toggle');
      const html = document.documentElement;
      
      // 檢查系統主題
      if (window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches) {
        html.classList.add('dark');
      }
      
      // 切換主題
      themeToggle.addEventListener('click', function() {
        html.classList.toggle('dark');
      });
      
      // 監聽系統主題變化
      window.matchMedia('(prefers-color-scheme: dark)').addEventListener('change', e => {
        if (e.matches) {
          html.classList.add('dark');
        } else {
          html.classList.remove('dark');
        }
      });
      
      // 區塊動畫
      const sections = document.querySelectorAll('[data-section]');
      
      const observerOptions = {
        root: null,
        rootMargin: '0px',
        threshold: 0.1
      };
      
      const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            entry.target.classList.add('visible');
          }
        });
      }, observerOptions);
      
      sections.forEach(section => {
        observer.observe(section);
      });
      
      // 平滑滾動
      document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function (e) {
          e.preventDefault();
          const targetId = this.getAttribute('href');
          const targetElement = document.querySelector(targetId);
          
          if (targetElement) {
            window.scrollTo({
              top: targetElement.offsetTop,
              behavior: 'smooth'
            });
          }
        });
      });
    });
  </script>
</body>
</html>
