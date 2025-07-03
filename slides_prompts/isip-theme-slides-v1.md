# **ISIP.HS Theme 投影片提示詞 V1**

## **核心任務與開發原則**
你是一位頂尖的資深前端架構師。你的核心任務是**打造一個可複用、高精準度的單一檔案簡報生成引擎**。

這個引擎由三大部分組成：**1. 一套固定的核心設計規範 (CSS)，2. 一個動態的應用程式引擎 (JS)，3. 一個可彈性擴充的內容資料結構 (Data)**。

在開發過程中，請務必遵守以下**三大開發原則**：
1.  **視覺精準還原 (Pixel-Perfect Replication)**：你必須 100% 精準地重現設計規範中的所有視覺細節，包含色彩、排版、座標與圖片資源。這份簡報的視覺風格已經定案，**請勿做任何額外的創意發揮或樣式修改**。
2.  **由資料驅動畫面生成 (Data-Driven Rendering)**：簡報的 HTML 結構**並非寫死的**。應用程式引擎必須讀取「內容資料結構」中的資料，並動態生成對應的投影片。這確保了此引擎未來可以輕鬆擴充或更換內容。
3.  **專業級的使用者體驗 (Professional-Grade UX)**：你必須實作所有規格中定義的專業級互動功能，特別是為不同投影片量身打造的**客製化動畫腳本**。

---

## **第一部分：核心設計規範 (CSS)**
這是簡報的視覺基礎。請在 `<style>` 標籤內**完整、逐字地**實現以下所有 CSS 規則。

```css
/* --- 品牌化調色盤與通用排版 --- */
:root {
  --theme-primary-color: #3b82f6;
  --font-family-default: "Noto Sans TC", "Microsoft JhengHei", sans-serif;
  --text-color-main: #333;
  --text-color-highlight: #d12;
}
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@400;700;900&display=swap');

body {
  font-family: var(--font-family-default); background-color: #333; color: var(--text-color-main);
  margin: 0; display: flex; justify-content: center; align-items: center; min-height: 100vh; overflow: hidden;
}
#presentation-app { width: 90%; max-width: 1100px; aspect-ratio: 16 / 9; position: relative; }

/* 投影片通用框架 */
.slide-frame {
  width: 100%; height: 100%; border: 1px solid #ccc; overflow: hidden; position: absolute;
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
  background-image: url("https://lh3.googleusercontent.com/d/1vARUFgKvceysL-7aX3o58O3pDqAXzDZF=s1920");
  background-repeat: no-repeat; background-size: cover; background-position: center;
  opacity: 0; visibility: hidden; transition: opacity 0.5s ease-in-out; z-index: 1;
}
.slide-frame.active { opacity: 1; visibility: visible; z-index: 2; }
.slide-content { width: 100%; height: 100%; position: relative; color: var(--text-color-main); }
.text-highlight { color: var(--text-color-highlight); font-weight: bold; }

/* 精確排版規則 */
h1,h2,h3,p { margin: 0; }
h1 { font-size: 3.5rem; line-height: 1.2; font-weight: 900; }
h2 { font-size: 2.2rem; line-height: 1.3; font-weight: 700; }
h3 { font-size: 1.8rem; line-height: 1.4; font-weight: 700; }
p { font-size: 1.6rem; line-height: 1.6; }
ul { list-style-position: outside; font-size: 1.6rem; padding-left: 2.5rem; }
ul ul { font-size: 1.5rem; padding-left: 1.5rem; }
ul ul ul { font-size: 1.4rem; padding-left: 1.5rem; }
ul > li::marker { content: "❖ "; font-size: 1.6rem; }
ul ul > li::marker { content: "➢ "; font-size: 1.5rem; }
ul ul ul > li::marker { content: "◼︎ "; font-size: 1.4rem; }

/* 精確座標式佈局系統 */
.layout-default .title, .layout-default .container { position: absolute; }
.layout-default .title { top: 9%; left: 8%; width: 85%; height: 12%; display: flex; align-items: center; justify-content: center; }
.layout-default .container { top: 22%; left: 7%; width: 85%; height: 64%; padding: 0 0.8rem; }
.layout-default h1 { font-size: 3.3rem; }
.layout-default .container h2 { font-size: 2.6rem; font-weight: 700; margin-bottom: 1.2rem; }
.layout-default .container h3 { font-size: 2.2rem; font-weight: 600; }
.layout-default .container p { font-size: 1.6rem; margin-top: 0.6rem; }

.layout-section .container { position: absolute; top: 0; left: 0; width: 100%; height: 100%; padding: 5%; box-sizing: border-box; }
.layout-section h1 { font-size: 4rem; font-weight: 900; position: absolute; top: 38%; left: 8%; }
.layout-section h2 { font-weight: 600; position: absolute; top: 55%; left: 8%;}
.layout-section .illustration { position: absolute; bottom: 5%; right: 5%; width: 35%; z-index: 1; }

.layout-cover .container { position: absolute; top: 22%; left: 7%; width: 85%; height: 64%; display: flex; flex-direction: column; }
.layout-cover .cover-header { text-align: center; }
.layout-cover .cover-body { display: grid; grid-template-columns: 1fr 1.2fr; align-items: center; gap: 2rem; padding: 0.5rem 1rem 0; flex-grow: 1; }
.layout-cover .left-col, .layout-cover .right-col { text-align: center; }
.layout-cover .left-col img, .layout-cover .right-col img { width: 100%; filter: drop-shadow(0 0 15px rgba(0,0,0,0.5));}

.layout-flowchart .title { position: absolute; top: 9%; left: 8%; width: 85%; height: 12%; display: flex; align-items: center; justify-content: center; text-align: center; }
.layout-flowchart .container { position: absolute; top: 22%; left: 7%; width: 85%; height: 64%; padding: 0.5rem; position: relative;}

/* 動畫與互動元件樣式 */
.anim-node { position: absolute; background-color: rgba(255,255,255,0.8); border: 2px solid var(--theme-primary-color); padding: 1rem; border-radius: 8px; text-align: center; font-weight: bold; }
.anim-packet { position: absolute; background: #fff; border-radius: 4px; padding: 0.5rem 1rem; box-shadow: 0 2px 5px rgba(0,0,0,0.2); font-family: monospace; opacity: 0; }
.anim-packet.request { border-left: 5px solid #3b82f6; }
.anim-packet.response { border-left: 5px solid #16a34a; }
.anim-packet.error { border-left: 5px solid #ef4444; }
.anim-packet.flag { border-left: 5px solid var(--text-color-highlight); font-weight: bold; color: var(--text-color-highlight); }
#tcp-container { position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); width: 70%; height: 40%; border: 2px dashed #9ca3af; border-radius: 10px; display: flex; justify-content: center; align-items: center; }
#tcp-reassembled { font-size: 2rem; font-family: monospace; opacity: 0; color: #16a34a; }

#sidebar-toggle { position: absolute; bottom: 3%; left: 3%; z-index: 99; width: 50px; height: 50px; background: rgba(255, 255, 255, 0.25); backdrop-filter: blur(8px); -webkit-backdrop-filter: blur(8px); border: 1px solid rgba(255, 255, 255, 0.3); border-radius: 50%; color: white; font-size: 24px; cursor: pointer; transition: transform 0.2s; }
#sidebar-toggle:hover { transform: scale(1.1); }
#sidebar { position: absolute; top: 0; left: 0; z-index: 100; width: 280px; height: 100%; background: rgba(30, 30, 35, 0.7); backdrop-filter: blur(10px); -webkit-backdrop-filter: blur(10px); border-right: 1px solid rgba(255, 255, 255, 0.2); transform: translateX(-100%); transition: transform 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94); opacity: 0; }
#sidebar.open { opacity: 1; transform: translateX(0); }
#sidebar h3 { color: var(--text-color-light); padding: 1.5rem; margin: 0; border-bottom: 1px solid rgba(255, 255, 255, 0.2); }
#sidebar ul { list-style: none; padding: 0; margin: 0; }
#sidebar ul li a { color: #d1d5db; text-decoration: none; display: block; padding: 1rem 1.5rem; transition: background-color 0.2s, color 0.2s; font-size: 1.2rem; border-bottom: 1px solid rgba(255, 255, 255, 0.1); }
#sidebar ul li a:hover { background-color: var(--theme-primary-color); color: white; }
```

---

## **第二部分：內容資料結構 (Data)**
這是簡報的內容核心。未來若要製作新的簡報，主要就是修改這個區塊的資料。

```javascript
// --- 內容資料結構 ---
// 這是所有投影片的資料來源，請將此物件放入最終的 <script> 標籤內。
const slidesData = [
  {
    id: 'slide-cover',
    type: 'cover',
    lightText: true,
    content: {
      title: 'Wireshark CTF 實戰攻略',
      subtitle: '從零開始的網路封包偵探學',
      imageLeft: 'https://lh3.googleusercontent.com/d/1tYWgK4r2CTrkpHRuKCt5-D-8ifkGPUOW=s1200',
      imageRight: 'https://lh3.googleusercontent.com/d/1gvHGZHv7ABbKbB831vhn-a3594lnpyRS=s1200'
    }
  },
  {
    id: 'slide-intro',
    type: 'section',
    lightText: true,
    content: {
      title: '網路世界的超級透視鏡',
      subtitle: 'Wireshark 能讓我們看見所有看不見的網路訊號',
      illustration: 'https://drive.google.com/thumbnail?id=1T5I_hN1xXYeKdeY7FqERp331TMGvBv_l&sz=s1200'
    }
  },
  {
    id: 'slide-anim-journey',
    type: 'flowchart',
    content: {
      title: '知識動畫：封包的旅程'
    }
  },
  {
    id: 'slide-pcap',
    type: 'default',
    content: {
      title: 'CTF 實戰：拆解封包 (.pcap)',
      body: `<h2>在成千上萬的封包中，找到唯一的 Flag！</h2>
             <ul>
                <li><b class="text-highlight">封包列表 (Packet List):</b> 所有封包的清單。</li>
                <li><b class="text-highlight">封包詳情 (Packet Details):</b> 拆解單一封包的結構。</li>
                <li><b class="text-highlight">封包位元組 (Packet Bytes):</b> 最原始的十六進位內容。</li>
                <li><b class="text-highlight">講師技巧：</b>學會使用「過濾器 (Filter)」是致勝關鍵！</li>
             </ul>`
    }
  },
  {
    id: 'slide-protocols-intro',
    type: 'section',
    lightText: true,
    content: {
      title: '關鍵協議追蹤術',
      subtitle: 'Flag 最喜歡躲在這三種訊號裡',
      illustration: 'https://drive.google.com/thumbnail?id=1-0v84s8oF8yZJgBqgA7FvR-m9xZ4wJ-O&sz=s1200'
    }
  },
  {
    id: 'slide-anim-http',
    type: 'flowchart',
    content: {
      title: '知識動畫：HTTP 請求與回應'
    }
  },
  {
    id: 'slide-tcp-dns',
    type: 'default',
    content: {
      title: '關鍵協議追蹤術 (續)',
      body: `<h2><span class="text-highlight">TCP</span> - 可靠的信差</h2>
             <ul>
                <li>保證資料「完整」且「依序」送達。</li>
                <li>CTF 考點：使用「追蹤 TCP 流量 (Follow TCP Stream)」功能，將破碎的封包拼湊還原。</li>
             </ul>
             <h2><span class="text-highlight">DNS</span> - 網路世界的電話簿</h2>
             <ul>
                <li>將網域名稱 (google.com) 翻譯成 IP 位址。</li>
                <li>CTF 考點：Flag 可能藏在惡意構造的查詢網址中。</li>
             </ul>`
    }
  },
  {
    id: 'slide-anim-tcp',
    type: 'flowchart',
    content: {
      title: '知識動畫：TCP 封包重組'
    }
  },
  {
    id: 'slide-summary',
    type: 'section',
    lightText: true,
    content: {
      title: '總結 & Q/A',
      subtitle: '你已經學會了網路偵探的基礎！'
    }
  }
];
```

---

## **第三部分：核心應用程式引擎 (JavaScript)**
在 `<script>` 標籤中實現此完整邏輯。這個引擎是整個應用的「大腦」，負責讀取資料、生成畫面並處理所有互動。

```javascript
// --- 核心應用程式引擎 ---
document.addEventListener('DOMContentLoaded', () => {
// 步驟 0: 獲取資料與 DOM 節點 (從第二部分複製資料)
const slidesData = [ /* 此處請複製貼上第二部分的完整 slidesData 陣列 */ ];
const app = document.getElementById('presentation-app');

// --- 步驟 1: 根據資料動態生成 HTML ---
let slidesHTML = '';
slidesData.forEach(slide => {
    let contentHTML = '';
    const layoutType = slide.type;
    const content = slide.content;

    if (layoutType === 'cover') {
        contentHTML = `<div class="container"><div class="cover-header"><h1>${content.title}</h1><h2>${content.subtitle}</h2></div><div class="cover-body"><div class="left-col"><img src="${content.imageLeft}" alt=""/></div><div class="right-col"><img src="${content.imageRight}" alt=""/></div></div></div>`;
    } else if (layoutType === 'section') {
        contentHTML = `<div class="container"><h1>${content.title}</h1><h2>${content.subtitle}</h2>${content.illustration ? `<img class="illustration" src="${content.illustration}" alt=""/>` : ''}</div>`;
    } else if (layoutType === 'default') {
        contentHTML = `<div class="title"><h1>${content.title}</h1></div><div class="container">${content.body}</div>`;
    } else if (layoutType === 'flowchart') {
        // 動畫的 HTML 結構較為固定，直接在此處定義
        let animHTML = '';
        if(slide.id === 'slide-anim-journey') {
            animHTML = `<div id="node-user" class="anim-node" style="top: 40%; left: 10%;">你的電腦</div><div id="node-server" class="anim-node" style="top: 40%; left: 75%;">Google 伺服器</div><div id="packet-request" class="anim-packet request">GET /</div><div id="packet-response" class="anim-packet response">200 OK + Homepage</div>`;
        } else if (slide.id === 'slide-anim-http') {
            animHTML = `<div class="anim-node" style="top: 40%; left: 10%;">你的電腦</div><div class="anim-node" style="top: 40%; left: 75%;">目標伺服器</div><div id="http-req1" class="anim-packet request">POST /login (pass:12345)</div><div id="http-res1" class="anim-packet error">403 Forbidden</div><div id="http-req2" class="anim-packet request">POST /login (pass:secret)</div><div id="http-res2" class="anim-packet flag">200 OK + FLAG{...}</div>`;
        } else if (slide.id === 'slide-anim-tcp') {
            animHTML = `<div id="tcp-part1" class="anim-packet" style="top: 10%; left: 20%;">Part 1: FLAG{...</div><div id="tcp-part2" class="anim-packet" style="top: 70%; left: 40%;">Part 2: ...this_is...</div><div id="tcp-part3" class="anim-packet" style="top: 30%; left: 60%;">Part 3: ...a_secret}</div><div id="tcp-container"><div id="tcp-reassembled">FLAG{this_is_a_secret}</div></div>`;
        }
        contentHTML = `<div class="title"><h1>${content.title}</h1></div><div class="container">${animHTML}</div>`;
    }
    slidesHTML += `<div class="slide-frame" id="${slide.id}"><main class="slide-content layout-${layoutType} ${slide.lightText ? 'light-text' : ''}">${contentHTML}</main></div>`;
});

slidesHTML += `<button id="sidebar-toggle" aria-label="開啟選單">☰</button><nav id="sidebar"><h3>投影片目錄</h3><ul></ul></nav>`;
app.innerHTML = slidesHTML;

// --- 步驟 2: 核心互動邏輯 ---
const slides = Array.from(app.querySelectorAll('.slide-frame'));
const sidebarToggle = app.querySelector('#sidebar-toggle');
const sidebar = app.querySelector('#sidebar');
const navList = sidebar.querySelector('ul');
let currentSlideIndex = 0;
let activeAnimation = null;

function showSlide(index) {
    if (index < 0 || index >= slides.length) return;
    if (activeAnimation) { activeAnimation.pause(); anime.remove(activeAnimation.targets); activeAnimation = null; }
    slides.forEach(s => s.classList.remove('active'));
    currentSlideIndex = index;
    const newSlide = slides[currentSlideIndex];
    newSlide.classList.add('active');
    updateNav();
    if (newSlide.querySelector('.layout-flowchart')) { initAnimation(newSlide); }
}

function initAnimation(slide) {
    const allAnimatedElements = slide.querySelectorAll('.anim-packet, #tcp-reassembled');
    allAnimatedElements.forEach(el => { el.style.transform = ''; el.style.opacity = '0'; });
    const slideId = slide.id;
    let timeline = anime.timeline({ easing: 'easeOutExpo', duration: 750 });
    if (slideId === 'slide-anim-journey') {
        const req = slide.querySelector('#packet-request'); const res = slide.querySelector('#packet-response');
        timeline.add({ targets: req, left: ['15%', '70%'], opacity: [1, 1] }).add({ targets: req, opacity: 0, duration: 200 }).add({ targets: res, left: ['70%', '15%'], opacity: [1, 1] }, '-=200').add({ targets: res, opacity: 0, duration: 200 });
    } else if (slideId === 'slide-anim-http') {
        const [req1, res1, req2, res2] = ['#http-req1', '#http-res1', '#http-req2', '#http-res2'].map(s => slide.querySelector(s));
        timeline.add({ targets: req1, left: ['15%', '70%'], opacity: [1, 1], duration: 500 }).add({ targets: req1, opacity: 0, duration: 200 }).add({ targets: res1, left: ['70%', '15%'], opacity: [1, 1] }, '-=200').add({ targets: res1, opacity: 0, duration: 200 }, '+=800').add({ targets: req2, left: ['15%', '70%'], opacity: [1, 1], duration: 500 }).add({ targets: req2, opacity: 0, duration: 200 }).add({ targets: res2, left: ['70%', '15%'], opacity: [1, 1] }, '-=200');
    } else if (slideId === 'slide-anim-tcp') {
        const parts = slide.querySelectorAll('#tcp-part1, #tcp-part2, #tcp-part3'); const reassembled = slide.querySelector('#tcp-reassembled');
        anime.set(parts, { opacity: 1 });
        timeline.add({ targets: parts, left: '50%', top: '50%', translateX: '-50%', translateY: '-50%', delay: anime.stagger(200), easing: 'easeInOutQuad' }).add({ targets: parts, opacity: 0, duration: 300 }).add({ targets: reassembled, opacity: 1, duration: 1000 });
    }
    activeAnimation = timeline;
}

    sidebarToggle.addEventListener('click', e => { e.stopPropagation(); sidebar.classList.toggle('open'); });
    document.addEventListener('click', e => { if (sidebar.classList.contains('open') && !sidebar.contains(e.target) && e.target !== sidebarToggle) { sidebar.classList.remove('open'); } });

    slidesData.forEach((slide, index) => {
        const title = slide.content.title;
        const a = document.createElement('a'); a.href = '#'; a.textContent = title; a.dataset.index = index;
        a.addEventListener('click', e => { e.preventDefault(); showSlide(index); sidebar.classList.remove('open'); });
        const li = document.createElement('li'); li.appendChild(a); navList.appendChild(li);
    });

    function updateNav() {
        navList.querySelectorAll('a').forEach(link => {
            const isActive = parseInt(link.dataset.index) === currentSlideIndex;
            link.style.backgroundColor = isActive ? 'var(--theme-primary-color)' : '';
            link.style.color = isActive ? 'white' : '#d1d5db';
        });
    }

    window.addEventListener('keydown', e => {
        if (e.key === 'ArrowRight' || e.key === 'PageDown') { e.preventDefault(); showSlide(currentSlideIndex + 1); }
        if (e.key === 'ArrowLeft' || e.key === 'PageUp') { e.preventDefault(); showSlide(currentSlideIndex - 1); }
    });

    showSlide(0);
});
```

## **內容表達重點**
* **內容用語**: 所有內容皆完全符合台灣慣用繁體中文用語，標點符號需使用台灣慣用之標點符號（全型）。在知識內容上，若有專有名詞，第一次出現將以原文呈現，並於其後加入中文解釋；第二次開始出現都以原文呈現該知識專有名詞。
* **知識視覺化**: 將複雜的專業知識、數據、流程，透過簡潔明瞭的圖形和圖示轉化為易於理解的視覺資訊。  
* **圖文並茂**: 每個核心概念或數據點都應搭配相關的圖示、插畫或圖表。  
* **手繪親切感**: 整體風格運用手繪元素（邊框、箭頭、字體、圖示處理）營造親和力、降低資訊的嚴肅感。  
* **關聯性表達**: 使用手繪箭頭、連接線、分組框線等方式，清晰表達不同資訊區塊之間的邏輯關係與層次。  
* **案例與引用**: 具體例子、引用名言等，使用對話框、特殊樣式的內容框進行歸納和突出。  
* **關鍵字突顯**: 透過顏色、底線、標記效果等方式，使核心關鍵字易於被使用者捕捉和記憶。  
* **框架化概念**: 重要的概念、模型或結論，使用手繪風格的框架（如內容框、手繪風格框）進行框選強調。  
* **數據簡潔化**: 若不使用圖表，數據資料也應以簡潔、易讀的方式呈現（例如：大數字突出、單位清晰、搭配小圖示）。  
* **故事性與流程感**: 盡可能將資訊組織成具有引導性的閱讀流程，讓使用者能一步步跟隨內容進展。

## **執行輸出**
* **Single HTML File**: 全部的程式碼都在同一個 html 中完成。
* **外部引用圖片**: 若是有需要圖片但沒有可以使用的圖片連結，將以 `<img src="https://placehold.co/{圖片寬度}x{圖片高度}" alt="這邊需要放上 {圖片大小比例} 的圖片"></a>`，其中的 `{圖片大小比例}` 你將依據需求填寫 `{w}x{h}`。
* **DX**: 針對開發者經驗進行最佳化，每一頁投影片需要註解，內容用語需完全符合台灣慣用繁體中文用語。
* **外部函式庫 (External Libraries)**: 為了實現動畫效果，請務必在 HTML 的 `<head>` 中引入 `anime.js` 函式庫。

## **最終 HTML 結構**
請使用以下 HTML5 樣板作為最終輸出的檔案結構。

```html
<!DOCTYPE html>
<html lang="zh-Hant">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Wireshark CTF 實戰攻略</title>
        <script src="https://cdn.jsdelivr.net/npm/animejs@4.0.2/lib/anime.min.js"></script>
        <style>
            /* --- 第一部分：核心設計規範 (CSS) --- */
            /* (請將 CSS 內容完整貼於此處) */
        </style>
    </head>
    <body>
        <div id="presentation-app">
            <!-- 應用程式引擎將會在此處動態生成投影片 -->
        </div>

        <script type="module">
            // --- 核心應用程式引擎 ---
            document.addEventListener('DOMContentLoaded', () => {
                // --- 第二部分：內容資料結構 (Data) ---
                const slidesData = [
                    /* (請將 slidesData 陣列完整貼於此處) */
                ];

                // --- 第三部分：應用程式引擎邏輯 ---
                // (請將 JS 邏輯完整貼於此處)
            });
        </script>
    </body>
</html>
```

## **最終執行命令**
嚴格按照上述三個部分——**1. 設計系統 (CSS)**, **2. 內容協議 (Data)**, **3. 應用程式引擎 (JS)**——的規格，並符合，將它們組合在一起，生成最終的、完整的、單一檔案的 HTML 應用程式。