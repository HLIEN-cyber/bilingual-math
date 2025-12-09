# 自定義圖片添加指南 / Custom Image Guide

[中文](#中文版本) | [English](#english-version)

---

## 中文版本

### 📖 目錄
1. [快速開始](#快速開始)
2. [詳細步驟](#詳細步驟)
3. [圖片要求](#圖片要求)
4. [範例代碼](#範例代碼)
5. [常見問題](#常見問題)

---

### 🚀 快速開始

**三個簡單步驟：**
1. 將圖片文件放入 `images/` 文件夾
2. 在 `index.html` 中添加或修改圖片引用
3. 在瀏覽器中打開 `index.html` 查看效果

---

### 📝 詳細步驟

#### 步驟 1: 準備您的圖片

**推薦的圖片規格：**
- **格式**: PNG（推薦）或 JPG
- **寬度**: 建議 800-1200 像素
- **高度**: 建議 600-1000 像素
- **文件大小**: 建議小於 2MB（以保證加載速度）
- **長寬比**: 建議 4:3 或 16:9

**圖片內容建議：**
- 清晰易讀的文字
- 色彩對比度高
- 如果是漫畫，確保分格清晰
- 背景簡潔，不影響主體

#### 步驟 2: 將圖片添加到項目

1. **找到 `images` 文件夾**
   ```
   bilingual-math-vocab/
   └── images/
       └── 您的圖片放這裡
   ```

2. **複製您的圖片文件到 `images` 文件夾**
   - 例如：`my-custom-comic.png`
   - 建議使用有意義的文件名（英文、數字、連字符）
   - 避免使用空格或特殊字符

3. **文件命名建議：**
   - ✅ 好的命名：`triangle-area-comic.png`
   - ✅ 好的命名：`pythagorean-theorem.jpg`
   - ❌ 避免：`我的圖片 1.png`（含空格和中文）
   - ❌ 避免：`image@#$.png`（特殊字符）

#### 步驟 3: 在 HTML 中添加圖片引用

1. **打開 `index.html` 文件**

2. **找到漫畫部分**（大約在第 487-530 行）：
   ```html
   <!-- Math Comics Section -->
   <div id="math-comics" class="tab-content">
       <div class="comics-grid">
           <!-- 這裡是現有的漫畫卡片 -->
       </div>
   </div>
   ```

3. **添加新的漫畫卡片**：

   **方法 A：修改現有卡片**

   找到任何一個現有的卡片（第 492-503 行為例）：
   ```html
   <div class="comic-card" onclick="viewStaticComic(this.querySelector('.comic-image'))">
       <img src="images/doraemon-spatial-geometry.png"
            alt="Doraemon's Spatial Geometry Adventure"
            class="comic-image">
       <div class="comic-info">
           <div class="comic-title">哆啦A夢的空間幾何大冒險</div>
           <div class="comic-description">
               Doraemon's Spatial Geometry Adventure
           </div>
       </div>
   </div>
   ```

   將 `src="images/doraemon-spatial-geometry.png"` 改為您的圖片文件名：
   ```html
   <img src="images/my-custom-comic.png"
        alt="My Custom Comic"
        class="comic-image">
   ```

   **方法 B：添加新卡片**

   在 `</div><!-- comics-grid -->` 之前添加新的卡片：
   ```html
   <div class="comic-card" onclick="viewStaticComic(this.querySelector('.comic-image'))">
       <img src="images/my-custom-comic.png"
            alt="我的自定義數學漫畫"
            class="comic-image">
       <div class="comic-info">
           <div class="comic-title">三角形面積公式</div>
           <div class="comic-description">
               Triangle Area Formula Comic
           </div>
       </div>
   </div>
   ```

4. **保存文件**

#### 步驟 4: 測試您的圖片

1. **在瀏覽器中打開 `index.html`**
   - 雙擊 `index.html` 文件，或
   - 右鍵選擇"使用瀏覽器打開"

2. **導航到"數學漫畫"標籤**
   - 點擊頁面頂部的"Math Comics"標籤

3. **檢查您的圖片**
   - 確認圖片正確顯示
   - 點擊圖片查看全屏效果
   - 檢查標題和描述是否正確

4. **如果圖片沒有顯示**：
   - 檢查文件路徑是否正確
   - 確認文件名大小寫完全匹配
   - 查看瀏覽器控制台（F12）是否有錯誤信息

---

### 🖼️ 圖片要求

#### 支持的文件格式
- ✅ **PNG** - 推薦用於清晰圖像和透明背景
- ✅ **JPG/JPEG** - 推薦用於照片或複雜圖像
- ✅ **GIF** - 支持，但不推薦用於靜態內容

#### 圖片尺寸指南

**縮略圖顯示（在卡片中）：**
- 顯示尺寸：寬度自適應，高度 200px
- 裁剪方式：`object-fit: cover`（自動裁剪適應）
- 推薦上傳尺寸：800-1200px 寬

**全屏查看（點擊後）：**
- 最大高度：70% 視窗高度
- 適應方式：`object-fit: contain`（保持比例完整顯示）
- 推薦上傳尺寸：1200-1920px 寬

#### 文件大小建議
- **單個圖片**: < 2MB（最佳）
- **可接受範圍**: 2-5MB
- **避免**: > 5MB（會影響頁面加載速度）

**優化圖片大小的方法：**
1. 使用在線工具：TinyPNG、Squoosh
2. 使用圖像編輯軟件：GIMP、Photoshop
3. 調整導出質量：PNG-24 或 JPG 質量 80-85%

---

### 💻 範例代碼

#### 範例 1: 單個自定義圖片

```html
<!-- 在 index.html 的 comics-grid 中添加 -->
<div class="comic-card" onclick="viewStaticComic(this.querySelector('.comic-image'))">
    <img src="images/pythagorean-theorem.png"
         alt="勾股定理圖解"
         class="comic-image">
    <div class="comic-info">
        <div class="comic-title">勾股定理的奧秘</div>
        <div class="comic-description">
            The Pythagorean Theorem Mystery
        </div>
    </div>
</div>
```

#### 範例 2: 多個圖片（完整替換）

```html
<!-- 替換整個 comics-grid 內容 -->
<div class="comics-grid">
    <!-- 第一張圖片 -->
    <div class="comic-card" onclick="viewStaticComic(this.querySelector('.comic-image'))">
        <img src="images/addition-adventure.png"
             alt="加法冒險"
             class="comic-image">
        <div class="comic-info">
            <div class="comic-title">加法大冒險</div>
            <div class="comic-description">
                Addition Adventure Comic
            </div>
        </div>
    </div>

    <!-- 第二張圖片 -->
    <div class="comic-card" onclick="viewStaticComic(this.querySelector('.comic-image'))">
        <img src="images/fraction-fun.png"
             alt="分數樂趣"
             class="comic-image">
        <div class="comic-info">
            <div class="comic-title">分數的樂趣</div>
            <div class="comic-description">
                Fun with Fractions
            </div>
        </div>
    </div>

    <!-- 第三張圖片 -->
    <div class="comic-card" onclick="viewStaticComic(this.querySelector('.comic-image'))">
        <img src="images/geometry-journey.png"
             alt="幾何之旅"
             class="comic-image">
        <div class="comic-info">
            <div class="comic-title">幾何世界之旅</div>
            <div class="comic-description">
                Journey Through Geometry
            </div>
        </div>
    </div>
</div>
```

#### 範例 3: 使用 JPG 格式

```html
<!-- JPG 格式範例 -->
<div class="comic-card" onclick="viewStaticComic(this.querySelector('.comic-image'))">
    <img src="images/calculus-basics.jpg"
         alt="微積分基礎"
         class="comic-image">
    <div class="comic-info">
        <div class="comic-title">微積分入門</div>
        <div class="comic-description">
            Introduction to Calculus
        </div>
    </div>
</div>
```

---

### ❓ 常見問題

#### Q1: 圖片不顯示，顯示破損圖標？
**A:** 檢查以下幾點：
- 文件路徑是否正確（`images/filename.png`）
- 文件名大小寫是否完全匹配
- 文件是否真的存在於 `images` 文件夾中
- 文件格式是否正確（.png, .jpg）

**調試方法：**
1. 打開瀏覽器開發者工具（按 F12）
2. 查看 Console 標籤是否有 404 錯誤
3. 查看 Network 標籤，看圖片請求的狀態

#### Q2: 可以添加多少張圖片？
**A:** 理論上沒有限制，但建議：
- 每頁顯示 6-12 張（良好的用戶體驗）
- 總文件大小建議不超過 20MB
- 考慮頁面加載時間和用戶體驗

#### Q3: 如何調整圖片顯示大小？
**A:** 有兩種顯示尺寸：

**縮略圖（卡片中）：**
- 當前設置：高度 200px，寬度自適應
- 修改位置：`index.html` 第 243-248 行
```css
.comic-image {
    width: 100%;
    height: 200px;  /* 修改這裡可調整縮略圖高度 */
    object-fit: cover;
}
```

**全屏查看：**
- 當前設置：最大高度 70% 視窗
- 修改位置：`index.html` 第 359-364 行
```css
.modal-image {
    max-width: 90%;
    max-height: 70vh;  /* 修改這裡可調整全屏高度 */
}
```

#### Q4: 圖片模糊或質量不好？
**A:** 原因和解決方案：
- **原圖分辨率太低**：使用更高分辨率的圖片（建議 1200px 寬以上）
- **壓縮過度**：使用質量更高的導出設置
- **格式不當**：線條圖、漫畫用 PNG；照片用 JPG

#### Q5: 如何批量添加多張圖片？
**A:** 步驟：
1. 將所有圖片複製到 `images` 文件夾
2. 為每張圖片創建一個卡片代碼塊
3. 使用複製粘貼，只修改：
   - `src` 屬性（文件名）
   - `alt` 屬性（替代文本）
   - `comic-title`（標題）
   - `comic-description`（描述）

**提示**：使用文本編輯器的多行編輯功能可以更快完成

#### Q6: 圖片可以放在其他文件夾嗎？
**A:** 可以，但需要修改路徑：
- 當前路徑：`images/filename.png`
- 子文件夾：`images/subfolder/filename.png`
- 其他位置：使用相對路徑或絕對路徑

**範例：**
```html
<!-- 子文件夾 -->
<img src="images/math-comics/triangle.png" class="comic-image">

<!-- 其他文件夾 -->
<img src="../assets/images/comic.png" class="comic-image">
```

#### Q7: 如何刪除不需要的圖片？
**A:** 兩個步驟：
1. 從 `index.html` 中刪除對應的 `<div class="comic-card">...</div>` 整個區塊
2. （可選）從 `images` 文件夾中刪除圖片文件

#### Q8: 可以添加動畫 GIF 嗎？
**A:** 可以！步驟相同：
```html
<img src="images/animated-math.gif"
     alt="動畫數學教學"
     class="comic-image">
```

**注意**：
- GIF 文件通常較大，注意文件大小
- 動畫會自動播放
- 在模態窗口中也會繼續播放

#### Q9: 圖片顯示被裁剪了？
**A:** 這是 `object-fit: cover` 的效果，有兩種解決方案：

**方案 1：調整圖片比例**
- 確保圖片比例接近卡片顯示比例
- 當前卡片寬高比約為 280:200（約 1.4:1）

**方案 2：修改 CSS**
- 在 `index.html` 第 243-248 行
- 將 `object-fit: cover` 改為 `object-fit: contain`
```css
.comic-image {
    width: 100%;
    height: 200px;
    object-fit: contain;  /* 完整顯示，可能有空白 */
    background-color: #f5f7fa;
}
```

#### Q10: 如何使用網絡圖片（URL）？
**A:** 直接使用完整 URL：
```html
<img src="https://example.com/path/to/image.png"
     alt="網絡圖片"
     class="comic-image">
```

**注意事項：**
- ⚠️ 需要網絡連接
- ⚠️ 圖片來源可能失效
- ⚠️ 可能有跨域問題
- ⚠️ 建議下載到本地使用

---

### 📱 響應式設計

圖片會自動適應不同屏幕尺寸：

**桌面（> 768px）：**
- 網格佈局：3-4 列
- 卡片寬度：最小 280px，自動填充

**平板和手機（≤ 768px）：**
- 網格佈局：1 列
- 卡片寬度：100%
- 自動堆疊顯示

無需額外配置，CSS 會自動處理！

---

### 🎨 進階自定義

#### 修改卡片樣式

**位置**：`index.html` 第 230-241 行

```css
.comic-card {
    background: white;
    border-radius: 12px;  /* 修改圓角大小 */
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);  /* 修改陰影 */
    overflow: hidden;
    cursor: pointer;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.comic-card:hover {
    transform: translateY(-8px);  /* 修改懸停上升高度 */
    box-shadow: 0 8px 24px rgba(0,0,0,0.15);  /* 修改懸停陰影 */
}
```

#### 修改網格佈局

**位置**：`index.html` 第 224-228 行

```css
.comics-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    /* 修改 280px 可以改變卡片最小寬度 */
    gap: 24px;  /* 修改卡片間距 */
    margin-top: 24px;
}
```

---

### 📋 快速檢查清單

添加新圖片前，請確認：

- [ ] 圖片文件已準備好（PNG 或 JPG）
- [ ] 圖片尺寸適當（建議 800-1200px 寬）
- [ ] 文件大小合理（< 2MB）
- [ ] 文件名使用英文、數字、連字符
- [ ] 已將圖片複製到 `images` 文件夾
- [ ] 已在 `index.html` 中添加卡片代碼
- [ ] 文件路徑正確（`images/filename.png`）
- [ ] 已填寫標題和描述
- [ ] 已在瀏覽器中測試顯示效果

---

### 🔧 故障排除

**問題：圖片加載很慢**
- 解決：壓縮圖片文件大小
- 工具：TinyPNG, Squoosh, ImageOptim

**問題：圖片變形或拉伸**
- 解決：檢查 `object-fit` 設置
- 使用 `contain`（完整顯示）或 `cover`（填滿裁剪）

**問題：點擊圖片沒有反應**
- 解決：檢查 `onclick` 屬性是否正確
- 確保 `viewStaticComic()` 函數存在

**問題：控制台顯示 404 錯誤**
- 解決：檢查文件路徑和文件名
- 確保大小寫完全匹配

---

### 📚 相關資源

**圖片優化工具：**
- [TinyPNG](https://tinypng.com/) - PNG/JPG 壓縮
- [Squoosh](https://squoosh.app/) - 在線圖片優化
- [GIMP](https://www.gimp.org/) - 免費圖像編輯器

**學習資源：**
- HTML `<img>` 標籤文檔
- CSS Grid 佈局教程
- 響應式設計基礎

---

## English Version

### 📖 Table of Contents
1. [Quick Start](#quick-start-en)
2. [Detailed Steps](#detailed-steps-en)
3. [Image Requirements](#image-requirements-en)
4. [Example Code](#example-code-en)
5. [FAQ](#faq-en)

---

### 🚀 Quick Start {#quick-start-en}

**Three Simple Steps:**
1. Place image files in the `images/` folder
2. Add or modify image references in `index.html`
3. Open `index.html` in a browser to view the results

---

### 📝 Detailed Steps {#detailed-steps-en}

#### Step 1: Prepare Your Images

**Recommended Image Specifications:**
- **Format**: PNG (recommended) or JPG
- **Width**: 800-1200 pixels recommended
- **Height**: 600-1000 pixels recommended
- **File Size**: < 2MB recommended (for loading speed)
- **Aspect Ratio**: 4:3 or 16:9 recommended

**Image Content Suggestions:**
- Clear and readable text
- High color contrast
- For comics, ensure clear panel divisions
- Simple background that doesn't distract from main content

#### Step 2: Add Images to Project

1. **Locate the `images` folder**
   ```
   bilingual-math-vocab/
   └── images/
       └── Place your images here
   ```

2. **Copy your image file to the `images` folder**
   - Example: `my-custom-comic.png`
   - Use meaningful filenames (English, numbers, hyphens)
   - Avoid spaces or special characters

3. **File Naming Recommendations:**
   - ✅ Good: `triangle-area-comic.png`
   - ✅ Good: `pythagorean-theorem.jpg`
   - ❌ Avoid: `my image 1.png` (contains spaces)
   - ❌ Avoid: `image@#$.png` (special characters)

#### Step 3: Add Image Reference in HTML

1. **Open the `index.html` file**

2. **Find the comics section** (around lines 487-530):
   ```html
   <!-- Math Comics Section -->
   <div id="math-comics" class="tab-content">
       <div class="comics-grid">
           <!-- Existing comic cards are here -->
       </div>
   </div>
   ```

3. **Add a new comic card**:

   **Method A: Modify Existing Card**

   Find any existing card (lines 492-503 for example):
   ```html
   <div class="comic-card" onclick="viewStaticComic(this.querySelector('.comic-image'))">
       <img src="images/doraemon-spatial-geometry.png"
            alt="Doraemon's Spatial Geometry Adventure"
            class="comic-image">
       <div class="comic-info">
           <div class="comic-title">哆啦A夢的空間幾何大冒險</div>
           <div class="comic-description">
               Doraemon's Spatial Geometry Adventure
           </div>
       </div>
   </div>
   ```

   Change `src="images/doraemon-spatial-geometry.png"` to your image filename:
   ```html
   <img src="images/my-custom-comic.png"
        alt="My Custom Comic"
        class="comic-image">
   ```

   **Method B: Add New Card**

   Before `</div><!-- comics-grid -->`, add a new card:
   ```html
   <div class="comic-card" onclick="viewStaticComic(this.querySelector('.comic-image'))">
       <img src="images/my-custom-comic.png"
            alt="My Custom Math Comic"
            class="comic-image">
       <div class="comic-info">
           <div class="comic-title">Triangle Area Formula</div>
           <div class="comic-description">
               Understanding Triangle Areas
           </div>
       </div>
   </div>
   ```

4. **Save the file**

#### Step 4: Test Your Images

1. **Open `index.html` in a browser**
   - Double-click the `index.html` file, or
   - Right-click and select "Open with Browser"

2. **Navigate to the "Math Comics" tab**
   - Click the "Math Comics" tab at the top of the page

3. **Check your images**
   - Verify the image displays correctly
   - Click the image to view fullscreen
   - Check that title and description are correct

4. **If the image doesn't display**:
   - Check that file path is correct
   - Ensure filename case matches exactly
   - Check browser console (F12) for error messages

---

### 🖼️ Image Requirements {#image-requirements-en}

#### Supported File Formats
- ✅ **PNG** - Recommended for clear images and transparent backgrounds
- ✅ **JPG/JPEG** - Recommended for photos or complex images
- ✅ **GIF** - Supported, but not recommended for static content

#### Image Size Guide

**Thumbnail Display (in cards):**
- Display size: Width responsive, height 200px
- Crop method: `object-fit: cover` (auto-crop to fit)
- Recommended upload size: 800-1200px wide

**Fullscreen View (after clicking):**
- Max height: 70% viewport height
- Fit method: `object-fit: contain` (maintain aspect ratio)
- Recommended upload size: 1200-1920px wide

#### File Size Recommendations
- **Single image**: < 2MB (optimal)
- **Acceptable range**: 2-5MB
- **Avoid**: > 5MB (affects page loading speed)

**Methods to Optimize Image Size:**
1. Use online tools: TinyPNG, Squoosh
2. Use image editing software: GIMP, Photoshop
3. Adjust export quality: PNG-24 or JPG quality 80-85%

---

### 💻 Example Code {#example-code-en}

#### Example 1: Single Custom Image

```html
<!-- Add in comics-grid in index.html -->
<div class="comic-card" onclick="viewStaticComic(this.querySelector('.comic-image'))">
    <img src="images/pythagorean-theorem.png"
         alt="Pythagorean Theorem Illustration"
         class="comic-image">
    <div class="comic-info">
        <div class="comic-title">The Pythagorean Theorem Mystery</div>
        <div class="comic-description">
            勾股定理的奧秘
        </div>
    </div>
</div>
```

#### Example 2: Multiple Images (Complete Replacement)

```html
<!-- Replace entire comics-grid content -->
<div class="comics-grid">
    <!-- First Image -->
    <div class="comic-card" onclick="viewStaticComic(this.querySelector('.comic-image'))">
        <img src="images/addition-adventure.png"
             alt="Addition Adventure"
             class="comic-image">
        <div class="comic-info">
            <div class="comic-title">Addition Adventure</div>
            <div class="comic-description">
                加法大冒險
            </div>
        </div>
    </div>

    <!-- Second Image -->
    <div class="comic-card" onclick="viewStaticComic(this.querySelector('.comic-image'))">
        <img src="images/fraction-fun.png"
             alt="Fun with Fractions"
             class="comic-image">
        <div class="comic-info">
            <div class="comic-title">Fun with Fractions</div>
            <div class="comic-description">
                分數的樂趣
            </div>
        </div>
    </div>

    <!-- Third Image -->
    <div class="comic-card" onclick="viewStaticComic(this.querySelector('.comic-image'))">
        <img src="images/geometry-journey.png"
             alt="Journey Through Geometry"
             class="comic-image">
        <div class="comic-info">
            <div class="comic-title">Journey Through Geometry</div>
            <div class="comic-description">
                幾何世界之旅
            </div>
        </div>
    </div>
</div>
```

#### Example 3: Using JPG Format

```html
<!-- JPG format example -->
<div class="comic-card" onclick="viewStaticComic(this.querySelector('.comic-image'))">
    <img src="images/calculus-basics.jpg"
         alt="Introduction to Calculus"
         class="comic-image">
    <div class="comic-info">
        <div class="comic-title">Introduction to Calculus</div>
        <div class="comic-description">
            微積分入門
        </div>
    </div>
</div>
```

---

### ❓ FAQ {#faq-en}

#### Q1: Image doesn't display, shows broken icon?
**A:** Check the following:
- File path is correct (`images/filename.png`)
- Filename case matches exactly
- File actually exists in the `images` folder
- File format is correct (.png, .jpg)

**Debugging Method:**
1. Open browser developer tools (press F12)
2. Check Console tab for 404 errors
3. Check Network tab to see image request status

#### Q2: How many images can I add?
**A:** Theoretically no limit, but recommended:
- 6-12 images per page (good user experience)
- Total file size should not exceed 20MB
- Consider page load time and user experience

#### Q3: How to adjust image display size?
**A:** Two display sizes:

**Thumbnail (in cards):**
- Current setting: height 200px, width responsive
- Modify at: `index.html` lines 243-248
```css
.comic-image {
    width: 100%;
    height: 200px;  /* Modify here to adjust thumbnail height */
    object-fit: cover;
}
```

**Fullscreen View:**
- Current setting: max height 70% viewport
- Modify at: `index.html` lines 359-364
```css
.modal-image {
    max-width: 90%;
    max-height: 70vh;  /* Modify here to adjust fullscreen height */
}
```

#### Q4: Image is blurry or poor quality?
**A:** Causes and solutions:
- **Original resolution too low**: Use higher resolution images (recommend 1200px+ wide)
- **Over-compressed**: Use higher quality export settings
- **Wrong format**: Use PNG for line art/comics; JPG for photos

#### Q5: How to batch add multiple images?
**A:** Steps:
1. Copy all images to `images` folder
2. Create a card code block for each image
3. Use copy-paste, only modify:
   - `src` attribute (filename)
   - `alt` attribute (alternative text)
   - `comic-title` (title)
   - `comic-description` (description)

**Tip**: Use text editor's multi-line editing feature for faster completion

#### Q6: Can images be in other folders?
**A:** Yes, but need to modify path:
- Current path: `images/filename.png`
- Subfolder: `images/subfolder/filename.png`
- Other location: use relative or absolute path

**Example:**
```html
<!-- Subfolder -->
<img src="images/math-comics/triangle.png" class="comic-image">

<!-- Other folder -->
<img src="../assets/images/comic.png" class="comic-image">
```

#### Q7: How to delete unwanted images?
**A:** Two steps:
1. Delete the corresponding `<div class="comic-card">...</div>` block from `index.html`
2. (Optional) Delete the image file from the `images` folder

#### Q8: Can I add animated GIFs?
**A:** Yes! Same steps:
```html
<img src="images/animated-math.gif"
     alt="Animated Math Tutorial"
     class="comic-image">
```

**Note:**
- GIF files are usually larger, watch file size
- Animation will auto-play
- Will continue playing in modal window

#### Q9: Image displays cropped?
**A:** This is the effect of `object-fit: cover`, two solutions:

**Solution 1: Adjust image aspect ratio**
- Ensure image ratio is close to card display ratio
- Current card aspect ratio is about 280:200 (about 1.4:1)

**Solution 2: Modify CSS**
- At `index.html` lines 243-248
- Change `object-fit: cover` to `object-fit: contain`
```css
.comic-image {
    width: 100%;
    height: 200px;
    object-fit: contain;  /* Show complete, may have whitespace */
    background-color: #f5f7fa;
}
```

#### Q10: How to use web images (URLs)?
**A:** Use full URL directly:
```html
<img src="https://example.com/path/to/image.png"
     alt="Web Image"
     class="comic-image">
```

**Notes:**
- ⚠️ Requires network connection
- ⚠️ Image source may become unavailable
- ⚠️ May have CORS issues
- ⚠️ Recommended to download locally

---

### 📱 Responsive Design

Images automatically adapt to different screen sizes:

**Desktop (> 768px):**
- Grid layout: 3-4 columns
- Card width: minimum 280px, auto-fill

**Tablet and Mobile (≤ 768px):**
- Grid layout: 1 column
- Card width: 100%
- Auto-stacking display

No extra configuration needed, CSS handles it automatically!

---

### 🎨 Advanced Customization

#### Modify Card Styling

**Location**: `index.html` lines 230-241

```css
.comic-card {
    background: white;
    border-radius: 12px;  /* Modify corner radius */
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);  /* Modify shadow */
    overflow: hidden;
    cursor: pointer;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.comic-card:hover {
    transform: translateY(-8px);  /* Modify hover lift height */
    box-shadow: 0 8px 24px rgba(0,0,0,0.15);  /* Modify hover shadow */
}
```

#### Modify Grid Layout

**Location**: `index.html` lines 224-228

```css
.comics-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    /* Modify 280px to change card minimum width */
    gap: 24px;  /* Modify card spacing */
    margin-top: 24px;
}
```

---

### 📋 Quick Checklist

Before adding new images, confirm:

- [ ] Image file ready (PNG or JPG)
- [ ] Image dimensions appropriate (recommend 800-1200px wide)
- [ ] File size reasonable (< 2MB)
- [ ] Filename uses English, numbers, hyphens
- [ ] Image copied to `images` folder
- [ ] Card code added to `index.html`
- [ ] File path correct (`images/filename.png`)
- [ ] Title and description filled in
- [ ] Display tested in browser

---

### 🔧 Troubleshooting

**Problem: Image loads slowly**
- Solution: Compress image file size
- Tools: TinyPNG, Squoosh, ImageOptim

**Problem: Image distorted or stretched**
- Solution: Check `object-fit` setting
- Use `contain` (show complete) or `cover` (fill and crop)

**Problem: Clicking image has no response**
- Solution: Check `onclick` attribute is correct
- Ensure `viewStaticComic()` function exists

**Problem: Console shows 404 error**
- Solution: Check file path and filename
- Ensure case matches exactly

---

### 📚 Related Resources

**Image Optimization Tools:**
- [TinyPNG](https://tinypng.com/) - PNG/JPG compression
- [Squoosh](https://squoosh.app/) - Online image optimizer
- [GIMP](https://www.gimp.org/) - Free image editor

**Learning Resources:**
- HTML `<img>` tag documentation
- CSS Grid layout tutorial
- Responsive design basics

---

## 快速參考 / Quick Reference

### 基本模板 / Basic Template

```html
<div class="comic-card" onclick="viewStaticComic(this.querySelector('.comic-image'))">
    <img src="images/YOUR-IMAGE-NAME.png"
         alt="Your Alt Text"
         class="comic-image">
    <div class="comic-info">
        <div class="comic-title">您的標題 / Your Title</div>
        <div class="comic-description">
            Your Description / 您的描述
        </div>
    </div>
</div>
```

### 文件結構 / File Structure

```
bilingual-math-vocab/
├── index.html                 (修改這裡 / Modify here)
├── images/                    (放圖片 / Place images)
│   ├── your-image-1.png
│   ├── your-image-2.jpg
│   └── README.md
└── CUSTOM_IMAGE_GUIDE.md     (本指南 / This guide)
```

---

**版本 / Version**: 1.0
**最後更新 / Last Updated**: 2025-12-09
**維護者 / Maintainer**: Claude Code Assistant

有問題？請查看上方的常見問題部分或聯繫項目維護者。
Questions? Check the FAQ section above or contact the project maintainer.
