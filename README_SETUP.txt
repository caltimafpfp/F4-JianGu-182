F4撿骨182｜GitHub Pages + Firebase 轉移版
==========================================

這份網站已經完成：
1. 沿用目前 F4 官網排版，不重新設計。
2. 前台支援 Firebase Firestore。
3. Firebase 尚未設定前，會暫時讀取舊 Supabase 公開資料，方便測試。
4. 管理後台在 /admin/。
5. 後台有「從舊 Supabase 匯入全部資料」按鈕，可一次搬資料到 Firebase。
6. Firestore Rules 已附上。

建議正式上線順序
----------------
A. 建立 Firebase 專案。
B. 建立 Firestore Database。
C. Authentication 開啟 Email/Password，並在 Firebase Console 建立一個管理員使用者。
D. Firebase 專案設定 > 新增 Web App，複製 firebaseConfig。
E. 把 firebaseConfig 貼進 firebase-config.js。
F. firestore.rules 的 ADMIN_EMAIL@example.com 改成管理員 Email，發布 Rules。
G. 開啟 /admin/ 登入，按「從舊 Supabase 匯入全部資料」。
H. 確認前台公告、下載、LINE、倍率、遊戲介紹都正常。
I. 再把整個資料夾上傳到 GitHub Repository，開啟 GitHub Pages。
J. 全部確認正常後，才停止使用 Supabase / 舊 Vercel。

圖片
----
目前沿用現有 F4 網站的圖片網址。
之後若要改成永久本地圖片，把圖片放進 assets/，再把 index.html 對應 img src 改成 assets/檔名即可。

注意
----
Firebase 前端 config 不是密碼，不需要藏起來。
真正的安全性由 Firestore Rules 決定；請務必把 rules 裡的 ADMIN_EMAIL 改成你的管理員 Email。
