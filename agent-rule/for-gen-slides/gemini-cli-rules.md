# Gemini CLI Agent Rules - Hand-drawn Style Slide Generation

## CRITICAL: Language Output Requirements
- **ALL SLIDE CONTENT MUST BE IN TRADITIONAL CHINESE (TAIWAN) - NO EXCEPTIONS**
- **Use Taiwan punctuation conventions and terminology exclusively**
- **NEVER use Simplified Chinese or English in slide content**
- **ALL text, titles, descriptions, UI elements, comments, and code comments must use Taiwan Traditional Chinese**
- **Even technical terms should use Taiwan-localized versions when available**
- **Button labels, navigation text, and all interactive elements must be in Traditional Chinese**

## Basic Settings & Behavior Patterns

### Language Configuration
- **Primary Output Language**: Traditional Chinese (Taiwan) - MANDATORY
- **Punctuation**: Taiwan standard punctuation conventions
- **Technical Terms**: Use Taiwan-localized technical terminology

### Output Behavior
- **Completeness Requirement**: Must generate complete HTML files with all necessary CSS and JavaScript
- **Single File**: All code should be integrated into one HTML file to avoid external dependencies
- **Ready to Use**: Generated files should open directly in browsers and function properly

### File Naming Convention
- File name format: `slides-[topic]-[date].html`
- Example: `slides-project-workflow-20240703.html`
- File encoding: UTF-8

## Data-Driven Architecture Rules

### Mandatory Workflow
1. **Data Definition Phase**:
   - Must first confirm with user or generate structured JSON data
   - Data should include: `title`, `nodes`, `connectors`
   - Validate data completeness and logical correctness

2. **Visualization Rendering Phase**:
   - Generate corresponding SVG elements based on JSON data
   - Follow predefined design specifications
   - Ensure responsive layout

3. **Interactive Features Phase**:
   - Implement auto-play and manual control
   - Bind keyboard navigation functionality
   - Add user interface controls

### JSON Data Structure Specification
```json
{
  "title": "流程圖標題",
  "nodes": [
    {
      "id": "專屬識別碼",
      "content": "節點顯示文字",
      "notes": "詳細說明",
      "position": { "x": 100, "y": 50 }
    }
  ],
  "connectors": [
    {
      "id": "連接線專屬識別碼",
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

### Layout Structure Requirements
- **Dual-column Layout**: Left sidebar (20-25%) + Right content area (75-80%)
- **Responsive Breakpoint**: Use collapsible navigation below 768px
- **Fixed Positioning**: Sidebar fixed, content area scrollable

### Typography Specifications
```css
/* Required font imports */
@import url('https://fonts.googleapis.com/css2?family=Kaisei+Decol:wght@400;500;700&family=Yomogi&family=Zen+Kurenaido&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@100..900&family=Noto+Serif+TC:wght@200..900&display=swap');

/* Font priority order */
body {
  font-family: 'Kaisei Decol', 'Noto Sans TC', sans-serif;
}

h1, h2, h3 {
  font-family: 'Yomogi', 'Zen Kurenaido', 'Noto Serif TC', serif;
}
```

## Technical Integration Standards

### Required Library Imports
```html
<!-- Animation libraries -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/animejs/3.2.1/anime.min.js"></script>

<!-- Chart library -->
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

<!-- Icon library -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
```

### Three-Stage Implementation Architecture
1. **Static Rendering Function**: `renderFlowchart(data)`
2. **Animation Timeline**: `anime.timeline()` configuration
3. **Interactive Controls**: Play/Pause/Reset/Next step buttons

### SVG Hand-drawn Style Templates
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

## Quality Control Standards

### Code Quality Requirements
- **Syntax Correctness**: HTML5 standards, CSS3 syntax, ES6+ JavaScript
- **Cross-browser Compatibility**: Support Chrome, Firefox, Safari, Edge
- **Performance Optimization**: Image compression, CSS/JS minification, load time < 3 seconds
- **Accessibility Design**: Comply with WCAG 2.1 AA standards

### Functional Completeness Checklist
- [ ] Slides can switch properly
- [ ] Animation effects work correctly
- [ ] Keyboard navigation functions properly
- [ ] Responsive layout is correct
- [ ] All interactive buttons are functional
- [ ] Flowchart animations are complete
- [ ] **ALL content is in Traditional Chinese (Taiwan)**
- [ ] **NO English or Simplified Chinese text present**
- [ ] **Taiwan punctuation and terminology used throughout**

### Content Quality Standards
- **Visual Consistency**: All elements conform to hand-drawn style
- **Information Hierarchy**: Clear visual hierarchy structure
- **Readability**: Text contrast ratio > 4.5:1
- **Aesthetics**: Harmonious color combinations, balanced layout

## Usage Scenario Guidelines

### Educational Training Slides
- Focus: Concept explanation, step-by-step processes, case studies
- Recommendations: Use icons, dialog boxes, keyword highlighting

### Meeting Presentations
- Focus: Data visualization, decision processes, action plans
- Recommendations: Integrate charts, use progress indicators, highlight conclusions

### Knowledge Sharing Documents
- Focus: Systematic organization, relationship display, in-depth analysis
- Recommendations: Use grouped frames, quote dialog boxes, multi-level headings

### Flowchart Explanations
- Focus: Clear logic, explicit steps, interactive experience
- Recommendations: Progressive disclosure, step-by-step display, manual control options

## Error Handling & Fallback Strategies

### Browser Compatibility Fallbacks
```css
/* backdrop-filter fallback handling */
.glass-effect {
  background: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(10px);
}

/* Browsers that don't support backdrop-filter */
@supports not (backdrop-filter: blur(10px)) {
  .glass-effect {
    background: rgba(255, 255, 255, 0.95);
  }
}
```

### JavaScript Error Handling
```javascript
// Animation library load failure handling
if (typeof anime === 'undefined') {
  console.warn('Anime.js failed to load, using CSS animation fallback');
  // Implement CSS animation fallback solution
}

// Chart library load failure handling
if (typeof Chart === 'undefined') {
  console.warn('Chart.js failed to load, using static charts');
  // Implement static chart fallback solution
}
```

## Output Confirmation Checklist

### Pre-generation Confirmation
- [ ] JSON data structure confirmed correct
- [ ] Usage scenario and target audience understood
- [ ] Technical requirements and browser support confirmed

### Post-generation Verification
- [ ] File opens normally
- [ ] All animation effects work properly
- [ ] Responsive layout is correct
- [ ] No JavaScript errors
- [ ] No CSS style conflicts
- [ ] Content is complete and accurate

---

> **Version Information**
> - Created: 2024-07-03
> - Based on: graphics-record-slides-v03.md
> - Applicable to: Gemini CLI
> - Maintainer: @CXPhoenix
> - Language Rules: English instructions, Traditional Chinese (Taiwan) output mandatory