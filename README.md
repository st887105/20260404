// ============================================================
// 車城國小學力檢測AI補救系統 - Google Apps Script 後端 v8.9
// 修正整合記錄：
//   v8.6  gemini-2.0-flash-lite 取代已停用的 gemini-1.5-flash
//   v8.7  多模型自動降級、deadline:30 防止無限等待
//   v8.8  gemini-2.5-flash 優先、BATCH_SIZE=5 減少 80% API 呼叫
//         responseMimeType=application/json 強制 JSON 輸出
//   v8.9  新增 fixGeminiModel()、testGeminiAPI() 診斷函式
//         新增 getPracticeQuestionsForErrors 類似題生成
//         _isValid 過濾純數字、getStudents 欄位修正
//   v8.9p getStudents 補丁：支援「X年X班X號 姓名」混合欄格式自動拆分
//   v8.9q ★ 關鍵修正：getStudents / uploadTaskData 使用 String() 比較
//          修正 Google Sheets 將數字型任務名稱（如"101"）自動轉為 number
//          導致嚴格比較 === 永遠失敗、學生名單無法讀取的問題
