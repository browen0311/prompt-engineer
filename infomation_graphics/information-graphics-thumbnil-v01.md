# 資訊圖表縮圖提示詞 V1

## 概述
此提示詞用於生成如頂尖顧問製作的高品質部落格文章縮圖。創建視覺精緻、內容一目了然的16:9比例資訊圖表風格縮圖。

## 基本結構
```
請使用HTML/CSS製作[文章標題]的縮圖
尺寸為16:9（1920x1080px）
運用Font Awesome圖示提高資訊圖表的可讀性與專業性
並使用以下色彩配置與字體
```

## 色彩調色盤定義（可自訂）
```
<palette>
<color name='圖形設計-1' rgb='21403A' r='33' g='63' b='58' />
<color name='圖形設計-2' rgb='F2F2F2' r='242' g='242' b='242' />
<color name='圖形設計-3' rgb='D9D9D9' r='216' g='216' b='216' />
<color name='圖形設計-4' rgb='404040' r='63' g='63' b='63' />
<color name='圖形設計-5' rgb='0D0D0D' r='12' g='12' b='12' />
</palette>
```

## 字體定義（建議使用中文字體）
```
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Kaisei+Decol:wght@700&family=Zen+Kurenaido&display=swap" rel="stylesheet">
Kaisei Decol: CSS class
.kaisei-decol-bold {
  font-family: "Kaisei Decol", serif;
  font-weight: 700;
  font-style: normal;
}
Zen Kurenaido: CSS class
.zen-kurenaido-regular {
  font-family: "Zen Kurenaido", sans-serif;
  font-weight: 400;
  font-style: normal;
}
```

## 設計元素
請包含以下元素：
1. **標題區塊**:
   - 主標題（大而醒目的字體 - 使用Kaisei Decol）
   - 副標題（補充資訊 - 使用Zen Kurenaido）
   - 相關的Font Awesome圖示
2. **視覺元素**:
   - 右側放置相關圖形/插圖
   - 徽章或標籤（顯示主題或類別）
3. **內容特點**:
   - 以圖示展示3-4個主要重點
   - 每個重點簡短扼要
4. **專業元素**:
   - 漸層背景
   - 細緻的網格圖案
   - 適當的陰影效果

---

> Reference
>
> [@Sunwood-ai-labs](https://github.com/Sunwood-ai-labs/MysticLibrary)