# 電子白板相容性修復

保留 v2.2-preview.html 素材及既有多人、聲音分組修補；首頁內嵌預先編譯的 10 個 script，載入原始素材並完成修補後套用。編譯目標 ES2017，不改 Firebase 規則。首頁因包含相容版程式增加至約 1.42 MB。

補上 replaceChildren、Array.at、flatMap、crypto.randomUUID 備援。UUID 使用 crypto.getRandomValues，不降低隨機性。以傳統四邊定位補 inset，並提供不支援 dvh、min、clamp、aspect-ratio 時的版面與 SVG 食材尺寸。

檢查：外層 loader 與全部 10 個 script 均通過 ES2017 語法解析；31 項完整生成頁模擬流程斷言通過（房主、非房主試聽、果凍清除、退出多人及單機重開）。停用上述新 API 的 DOM 模擬可完成首頁初始化，建立全部 7 個人數按鈕，沒有初始化錯誤。

範圍限制：不代表所有舊款 Android WebView 均受支援，仍須具備 Web Audio、SVG、CSS Grid、Promise、Fetch 及多人所需 WebRTC。未使用使用者實體白板測試觸控、喇叭或校園網路。

備份：index-before-whiteboard-fix-20261021.html。
