# AI 協同開發指南與實踐：尋找你的「未知」（Finding your unknowns）

本專案是一個將 Anthropic 團隊的開發哲學 **《A field guide to Claude Fable 5: Finding your unknowns》** 內化為實際工作流的實作專案。專案本身即是人機協作（Human-AI Collaboration）的產出成果。

---

## 🔗 參考來源
*   **原文網址**：[Anthropic Blog: A field guide to Claude Fable 5: Finding your unknowns](https://claude.com/blog/a-field-guide-to-claude-fable-finding-your-unknowns)
*   **原作者**：Thariq Shihipar (Anthropic 技術團隊成員)

---

## 📂 專案檔案結構 (Directory Map)

*   [README.md](file:///Users/lanss/projects/2_Practice/1150714_test/README.md)：本協作說明文件。
*   [index.html](file:///Users/lanss/projects/2_Practice/1150714_test/index.html)：互動式 Notion 風格導讀網頁。包含：
    *   **大師思維導讀**：融合吳恩達（落地工作流）、簡立峰（ROI戰略）與陳縕儂（互動設計）的隱形大師濾鏡。
    *   **嵌入式原文圖片**：直接嵌入插圖並支援「點擊燈箱（Lightbox）放大」功能。
    *   **動態 Mermaid 流程圖**：引入 Mermaid.js 在網頁中動態渲染，並同樣支援向量燈箱放大，確保縮放無損。
    *   **工具箱卡片**：將黃金協作 Prompts 模組化，提供「一鍵複製」按鈕。
*   [claude_fable_unknowns_guide.md](file:///Users/lanss/projects/2_Practice/1150714_test/claude_fable_unknowns_guide.md)：精簡的 Markdown 摘要指南，適合在 Obsidian、Typora 等筆記軟體中直接開啟與離線閱讀。

---

## 🧭 人機對齊實作流程 (AI-Native Alignment Loop)

在與 AI（如 Claude Code 或 Antigravity）協作時，我們實踐了以下三階段的「超敏捷工作流」：

```mermaid
flowchart TD
    subgraph 1. 實作前 (Pre-implementation)
        A[AI 盲點檢視 Blind Spot Pass] --> B[AI 逐題訪談 Interview]
        B --> C[快速拋棄式原型 Prototype]
        C --> D[核准實作計畫 Plan]
    end
    
    subgraph 2. 實作中 (During-implementation)
        D --> E[偏差與決策記錄 Deviations]
        E -->|更新實作筆記| F[implementation-notes.md]
    end
    
    subgraph 3. 實作後 (Post-implementation)
        F --> G[程式碼異動隨堂測驗 Quiz]
        G -->|完全答對且掌握邏輯| H[安全合併 Merge]
    end
```

---

## 💡 如何在日常開發中使用這些工具？

1.  **開啟對話前**：若專案規模較大或技術不熟悉，請先不要讓 AI 直接寫程式，而是使用 [index.html](file:///Users/lanss/projects/2_Practice/1150714_test/index.html) 中 **「實作前：盲點檢視」** 的複製按鈕，要求 AI 為你整理出專案中的「未知未知（Unknown Unknowns）」。
2.  **規劃階段**：複製 **「實作前：深度訪談」** 的 Prompt，讓 AI 成為你的 SA 訪談者，釐清架構上的分歧。
3.  **開發中**：要求 AI 維持一份實作筆記以記錄偏離原定 spec 的部分。
4.  **合併前**：複製 **「實作後：隨堂測驗」** Prompt，確保自己完全掌握 AI 生成的代碼細節後，才進行 merge。

---

## 🎨 生圖 Prompts

### 原始 Midjourney 概念版本
如果需要為此專案生成宣傳 Banner，可直接使用以下生圖關鍵字：

*   **解構地圖與疆域**：
    > *A futuristic digital cartography scene, a developer using holographic interface to overlay a glowing golden tech map onto a physical dark silicon motherboard territory. Matrix code streams, neural networks, abstract glowing symbols representing unknown variables, morandi cool color palette (soft blues, teals, and sand gold), clean tech minimalist aesthetic, ultra-detailed, 16:9 aspect ratio --ar 16:9*
*   **人機協同 pair-programming**：
    > *A software engineer pair programming with a friendly, glowing semi-transparent AI holographic assistant. They are looking at a vertical digital board showing a structured system architecture plan. Warm and cozy modern home-office desk setup, soft volumetric lighting, sketchnote doodle style diagrams on the background glass wall, clean tech illustration, --ar 16:9*

### 生圖時的踩坑
第一版直接照抄原文 Midjourney 提示詞生成，畫風偏寫實科技感；使用者要求改成 Taiwan kawaii + 日系可愛風、且要有粉圓體中文標籤後，把上面兩則 Prompt 改寫成含明確中文文字內容與 kawaii 風格描述，重新生成才符合需求。

### 實際採用版本（Taiwan kawaii + 粉圓體，已用 codex exec image_gen 生成）
`index.html` 導讀正文中實際嵌入的插圖，是把上面的概念改寫成日系 kawaii 風格、並要求使用粉圓體中文標籤後生成的版本，輸出檔案在 [images/](file:///Users/lanss/projects/2_Practice/1150714_test/images/)：

*   **地圖與疆域的落差** → `images/map-territory.webp`
    > *Use the image_gen tool to create a WIDE HORIZONTAL landscape infographic-style illustration at 1792x1024. Taiwan kawaii cute illustration style, Japan kawaii aesthetic, chibi characters, rounded soft shapes, pastel color palette (soft blue, mint, sand gold, cream white background). Use 粉圓體（rounded Taiwan Chinese font）for all Chinese text, big and clearly readable. Scene: on the LEFT side, a cute chibi software engineer character happily holding up a glowing golden holographic paper map labeled「地圖」in large rounded Chinese text. On the RIGHT side, a chunky adorable island-shaped landmass covered in cute tiny circuit-board patterns and building blocks, labeled「疆域」in large rounded Chinese text. In the middle gap, draw sparkly stars and a small cute question-mark cloud character labeled「未知」in rounded Chinese text. Soft rounded clouds in the sky, warm friendly lighting, clean minimal kawaii infographic composition, 16:9 landscape.*
*   **人機協作的三階段循環** → `images/pair-programming.webp`
    > *Use the image_gen tool to create a WIDE HORIZONTAL landscape infographic-style illustration at 1792x1024. Taiwan kawaii cute illustration style, Japan kawaii aesthetic, chibi characters, rounded soft shapes, pastel color palette (soft blue, mint, sand gold, cream white background). Use 粉圓體for all Chinese text, big and clearly readable. Scene: on the LEFT, a happy chibi software engineer character sitting at a cozy desk, next to a friendly round glowing semi-transparent AI blob character with cute sparkly eyes. Together they look at a large floating circular loop diagram on the RIGHT side, made of three big rounded pastel bubble nodes connected by curved arrows going clockwise: top bubble labeled「實作前」, right bubble labeled「實作中」, left bubble labeled「實作後」, all in large rounded Chinese text（粉圓體）. Small cute icons inside each bubble: a magnifying glass in 實作前, a notebook in 實作中, a checkmark in 實作後. Warm cozy home-office background, soft volumetric lighting, clean minimal kawaii infographic composition, 16:9 landscape.*

---

## 🤝 與 AI 協同開發的歷程紀錄

這份文件本身，就是照著上面「人機對齊實作流程」跑出來的成果。以下依實際發生順序整理，方便之後回顧當初的決策脈絡：

1.  **初版導讀**：讀完原文三份素材（README、精簡 md、互動 html）後，先產出一版加入 Claude 觀點的深度導讀，融入原文摘要與批判性評論。
2.  **發現「兩篇拼接」問題**：使用者指出全文讀起來像「原文摘要 + 後加觀點」兩篇文章硬接在一起。依 deep-guide skill 的精神，重新整合成單一敘事（五幕結構），拿掉會暴露「這是後加內容」的視覺分隔線與標籤樣式。
3.  **拆解生圖 Prompt 專區**：原本集中在文末的兩組 Midjourney 生圖 Prompt，改成逐段審視內容後，分散嵌入到語意對應的段落（地圖疆域段、三階段協作段）。
4.  **白話化改寫**：使用者確認目標讀者是「0 觀念的新手」後，把長句拆短、拿掉 SA / SRS / UML / Edge Case 等專業術語，全文改用具體例子取代抽象詞。
5.  **修正 Mermaid 語法錯誤**：使用者回報「人機對齊迴路圖」的 Mermaid 語法有誤，排查發現是 `subgraph` 標題含括號卻沒加引號，導致解析失敗；修正後用 `mmdc`（mermaid-cli）實際渲染驗證通過。
6.  **用 codex exec 生圖 → 轉 webp**：呼叫 `codex exec` 的內建 `image_gen` 工具，依兩組 Prompt 生成 PNG，再用 `cwebp` 轉檔壓縮（3.1MB → 349KB、2.3MB → 166KB）。
7.  **風格調整為 Taiwan kawaii + 粉圓體**：使用者要求圖片改成日系可愛風、且要有粉圓體中文標籤，重新改寫 Prompt（明確指定中文文字內容與 kawaii 視覺元素）並重新生成，實際打開圖片確認內容後才回報完成。
8.  **嵌入對應段落**：把兩張圖分別放進 HTML 中對應的 🎨 Prompt 卡片位置，套用既有的 `.article-image` 樣式與點擊燈箱效果。
9.  **生圖 Prompt 移回 README**：圖片確定嵌入正文後，HTML 裡的生圖 Prompt 卡片（含複製按鈕）功能上已重複，予以移除，Prompt 原文改放回本檔案，方便之後需要重新生圖或修改風格時查閱。

這個過程本身，其實就是「地圖與疆域」概念的一次實際示範：每一次使用者的糾正（兩篇拼接、術語太難、Mermaid 語法錯、圖片風格不對），都是把「Claude 以為講清楚了」跟「使用者真正想要的樣子」之間的落差，一次次縮小的過程。
