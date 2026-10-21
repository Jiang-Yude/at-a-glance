# 畫給我看 Draw It For Me

讓 AI 把複雜的東西講到五歲小孩也聽得懂：短短講完，講不清楚就畫給你看。

免費開源，MIT 授權。一個 `SKILL.md` 加一個 HTML 模板，任何 AI 助理都能用。

**[教學文章：怎麼用、為什麼這樣設計](https://jiangyude.com/articles/draw-it-for-me/)**

---

## 這是要解決什麼

你問 AI 一個問題，它很認真：先打招呼、重述你的問題、列出十點、最後再總結一次。

答案其實就一句，但被埋在中間。

這個技能包讓 AI 改成三種回法，看東西有多複雜決定：

| 情況 | AI 會怎麼回 |
|---|---|
| 一兩句講得完 | 第一句就是答案，最多再三點，需要時用生活比喻 |
| 要用圖才講得清，但東西不多 | 直接在對話裡畫一張圖 |
| 東西多、要分好幾張圖 | 做一頁 HTML 圖解 |

圖的看法只有一個原則：**一眼看大概，滑過去看細節。** 框上只寫幾個字，滑鼠移上去才浮出細節；箭頭也能滑，會告訴你「為什麼走到下一步」；重點卡片只露一句話，點開才展開。

## 有什麼

| 檔案 | 用途 |
|---|---|
| `SKILL.md` | 技能包本體。可以直接貼給 Claude、ChatGPT 或任何 AI 助理 |
| `assets/picture-template.html` | 一頁圖解的空白模板：五種基本圖（流程、前後對照、組成、因果、長條），滑鼠浮出細節已寫好 |
| `docs/demo.html` | 填好內容的示範頁：「AI 為什麼講那麼長」 |

## 怎麼用

### 方法一：讓 AI 幫你做（推薦）

把 `SKILL.md` 的內容貼給你的 AI 助理（需要做網頁圖解時，連 `assets/picture-template.html` 一起給它），然後說：

> 畫給我看。

或是：

> 像五歲小孩一樣跟我解釋。

如果你用 Claude Code 或支援技能包的環境，把整個資料夾放進你的 skills 目錄，說「畫給我看」就會自動觸發。

### 方法二：自己填模板

下載 `assets/picture-template.html`，照裡面的註解換內容。每個框、每個箭頭的細節寫在 `data-tip` 裡，滑鼠浮出的效果不用碰 JavaScript。

## 三條規則

1. **一張圖只講一件事。** 一張圖講三件事，五歲小孩就看不懂了。預設最多五張圖，重要資訊放不下就分組，不硬砍。
2. **細節藏在滑鼠底下。** 畫面上只放幾個字，想知道哪裡就滑哪裡。
3. **簡單不等於亂省。** 數字、「不」「沒有」這類否定詞、會出事的風險，一個都不能拿掉。

## 參考與致謝

這個技能包的想法來自幾個開源專案，只取精神，沒有照搬：

- [caveman](https://github.com/JuliusBrussee/caveman)：讓 AI 少講廢話、先講答案
- [ELI5](https://github.com/DreambigOu/ELI5)：講給五歲小孩聽
- [visual-explainer](https://github.com/nicobailon/visual-explainer)：用 HTML 頁面取代終端機裡的文字圖
- Anthropic Thariq 的 [html-effectiveness](https://github.com/ThariqS/html-effectiveness)：HTML 比 Markdown 更適合讓人看懂

示範頁裡的數字：caveman 早期自述平均省約 65% 輸出 token（作者後來說明這個數字未經驗證，見它的 [HONEST-NUMBERS](https://github.com/JuliusBrussee/caveman/blob/main/docs/HONEST-NUMBERS.md)）；獨立作者 Kuba Guzik 在結構化任務上測完整版 caveman，只省約 9% 到 13%（[原文](https://medium.com/@KubaGuzik/i-benchmarked-the-viral-caveman-prompt-to-save-llm-tokens-then-my-6-line-version-beat-it-d8e565f95e15)）。兩者都不是本技能包的實測。

## 作者

江昱德（江江教練）｜[jiangyude.com](https://jiangyude.com)

## 授權

MIT
