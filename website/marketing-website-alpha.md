# 行銷型一頁式網站生成提示詞

## 目的
將內容轉換成由頂尖設計師製作的一個視覺吸引、行銷效果強的一頁式響應式網站，使用提供的色彩配置與設計元素，確保無障礙使用體驗。

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
- Tailwind CSS CDN 整合
- Font Awesome 圖示庫
- 完整響應式設計(RWD)
- Animate.js 動畫效果
- 符合 WCAG 2.1 AA 級無障礙標準

### 3. 排版與字體
- 標題：使用無襯線字體，大小流動漸變
- 正文：優先閱讀性，行距1.5-1.8
- 強調文字：搭配UI/UX-2(活力橙金)色調
- 按鈕文字：清晰可讀，足夠對比度

## 網站區塊結構

### 1. 導航列
- 固定頂部，半透明背景
- 品牌標誌左側，導航選單右側
- 手機版轉為漢堡選單
- 滾動時背景加深效果

### 2. 英雄區塊
- 全屏背景圖或漸層背景
- 大標題+副標題組合
- 明確行動號召按鈕(CTA)
- 圖示化價值展示(3-4個核心賣點)

### 3. 產品/服務特色
- 三欄或四欄卡片式設計
- 每卡片配大型Font Awesome圖示
- 標題、簡短說明與微型CTA
- 卡片懸浮效果

### 4. 顧客見證/案例展示
- 引用式設計，搭配顧客照片/標誌
- 引用符號使用強調色
- 來源資訊與評分清晰標示
- 左右滑動功能(手機版)

### 5. 資料與成就區塊
- 大字體資料展示
- 動畫計數效果
- 簡短說明文字
- 使用圖示強化視覺傳達

### 6. 行動號召區塊
- 對比鮮明背景
- 大型CTA按鈕
- 簡潔有力的標語
- 輕量級表單(若需要)

### 7. 聯絡/頁尾區塊
- 聯絡資訊與社群媒體連結
- 簡短公司介紹
- 版權資訊
- 隱私政策連結

## 動畫效果指南
- 進場動畫：元素從下/側向滑入
- 滾動觸發：資訊卡、資料計數動畫
- 互動效果：按鈕、卡片懸浮狀態變化
- 微動畫：圖示旋轉、跳動或脈動效果
- 頁面轉場：平滑錨點滾動

## 行銷設計要點
- 視覺層次分明，引導視線流向CTA
- 留白策略性使用，避免資訊過載
- 強調解決方案而非產品特性
- 使用社會認同元素(見證、標誌、計數)
- 製造稀缺感或時效感
- 降低風險表述(保證、試用、退款政策)

## 無障礙設計要求
- 色彩對比符合WCAG 2.1 AA標準
- 所有圖像提供alt文字
- 表單元素提供標籤與說明
- 支援鍵盤導航
- ARIA標籤適當使用
- 字體大小可調整
- 動畫可暫停選項

## HTML/CSS框架範例
```html
<!DOCTYPE html>
<html lang="zh-tw">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>產品名稱 - 核心價值主張</title>
  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Font Awesome -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <!-- Animate.css -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css">
  
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            primary: '#1B6C8C',
            secondary: '#BF8136',
            background: '#F2E8E4',
            text: '#260101',
            accent: '#BF5656',
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
  </style>
</head>

<body class="bg-background text-text">
  <!-- 導航列 -->
  <nav class="fixed w-full bg-primary bg-opacity-90 text-white z-50">
    <!-- 導航內容 -->
  </nav>
  
  <!-- 英雄區塊 -->
  <header class="min-h-screen flex items-center">
    <!-- 英雄內容 -->
  </header>
  
  <!-- 產品特色 -->
  <section class="py-20">
    <!-- 特色內容 -->
  </section>
  
  <!-- 其他區塊... -->
  
  <!-- 動畫脚本 -->
  <script>
    // 滾動動畫觸發
    const animateElements = document.querySelectorAll('.animate-on-scroll');
    
    function checkScroll() {
      animateElements.forEach(element => {
        const elementTop = element.getBoundingClientRect().top;
        if (elementTop < window.innerHeight * 0.8) {
          element.classList.add('visible');
        }
      });
    }
    
    window.addEventListener('scroll', checkScroll);
    checkScroll(); // 初始檢查
  </script>
</body>
</html>
