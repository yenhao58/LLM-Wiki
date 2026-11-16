# 維護日誌

## [2026-11-16] setup | 初始化大型語言模型知識庫

建立中文版規範、使用說明、原始來源目錄、Wiki 索引與各類知識頁目錄。

## [2026-11-16] ingest | Karpathy 的 LLM Wiki

收錄使用者提供的 [原文](../raw/karpathy-llm-wiki.md)，新增 [來源摘要](sources/karpathy-llm-wiki.md) 並更新索引。這筆來源記錄的是知識庫設計。

## [2026-11-16] ingest | 2025 年版全國扯鈴比賽規則

依使用者指定新增[來源摘要](sources/diabolo-competition-rules-2025.md)及[參賽與看賽重點](syntheses/diabolo-competition-guide-2025.md)，並更新索引。來源頁已連結使用者上傳原檔，本地 PDF 待補。

## [2026-11-16] ingest | 四項民俗體育規則簡報

核對四份 PDF，補齊扯鈴、跳繩、陀螺及踢毽來源頁的器材、指定動作、得分與失誤條件，建立四份筆記、逐頁稿及[簡報入口](../presentations/index.html)。新增來源的本地文字摘錄已收錄，PDF 原始檔透過來源頁連結。本地 PDF 及陀螺花式時間扣分適用方式待確認。

## [2026-11-16] fix | 簡報入口改為單檔整合

問題：`presentations/index.html` 以相對連結開啟 `diabolo.html` 等四個檔案，在只載入單一檔案的預覽視窗（ChatGPT HTML 預覽、沙箱 iframe、部分檔案檢視器）中會被攔下，顯示「這項內容已遭到封鎖」，看不到簡報。

處理：把四份簡報的 22 張投影片整併進 [簡報入口](../presentations/index.html)，改用頁內標籤與換頁控制切換，不再跨文件跳轉；網址以 `#diabolo` 等錨點記錄所在項目，切換時用 `history.replaceState`，被沙箱限制時自動忽略。停用 JavaScript 時退化為可捲動長頁，四份簡報仍可完整閱讀。四份獨立簡報檔保留，`原始 PDF` 連結改為標示需登入並以新視窗開啟；首頁不再顯示 PDF 與獨立檔案的說明段落。`slides_fix_inspect/` 同步更新，`folk-sports-rules-slides-fixed.zip` 重新打包。

驗證：以本機 HTTP 服務載入入口頁，四張卡片、運動標籤、上／下一頁、頁碼選單與 `#shuttlecock` 直接連結均正常，主控台無錯誤；`diabolo.html` 等獨立檔仍可單獨開啟。待辦：ChatGPT 檔案庫的 PDF 連結未登入時回 401，本地仍無 PDF 備份。

## [2026-11-16] setup | 擴充 AGENTS.md 簡報網站與發布規則

把專案範圍補成「LLM Wiki ＋ 民俗體育簡報網站」，目錄表加入 `notes/`、`slides/`、`presentations/`、打包 zip 與檢查副本。新增「簡報網站」一節，寫明三條硬規則（不得跨檔連結、不引用外部資源、一個 deck 一張 article）、新增運動與投影片的逐步流程、以及每次改完要跑的驗證清單；另加「版本控制與發布」一節，記錄分支、`.gitignore` 排除項、提交訊息格式與 GitHub Pages 網址。專案已推上 `https://github.com/yenhao58/LLM-Wiki`，公開網址 `https://yenhao58.github.io/LLM-Wiki/presentations/` 已可開啟。
