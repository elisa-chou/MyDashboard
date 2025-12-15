# 📊 工作 Dashboard

一個現代化的工作待辦事項管理系統，支援多裝置同步、拖曳排序、重要標記等功能。

## ✨ 功能特色

### 核心功能
- ✅ **四個分類區塊**
  - 當周待辦（週一至週五）
  - 其他待辦
  - 私人待辦
  - 近期關注

- 🎯 **待辦事項管理**
  - 新增/刪除待辦事項
  - 拖曳移動至不同區塊
  - 標記重要事項（紅色提醒）
  - 添加詳細備註

- 🔐 **安全認證**
  - Google 帳號登入（安全便捷）
  - 自動記住登入狀態（30天）
  - 每個 Google 帳號獨立資料空間

- ☁️ **雲端同步**
  - 使用 Firebase Realtime Database
  - 多裝置即時同步
  - 資料安全備份

- 📱 **響應式設計**
  - 完美支援桌面、平板、手機
  - 觸控友善介面
  - 流暢的拖曳體驗

## 📁 檔案說明

```
Dashboard/
├── index.html                 # 完整功能版本（Google 登入 + Firebase）
├── demo.html                  # 示範版本（本地儲存，可直接開啟測試）
├── design-mockup.html         # 設計稿參考
├── FIREBASE_SETUP.md          # Firebase 設定詳細教學（必讀！）
├── GOOGLE_LOGIN_CHECKLIST.md # 設定檢查清單
├── DEPLOY.md                  # GitHub Pages 部署指南
├── SETUP.md                   # 舊版設定說明（已過時）
├── README.md                  # 專案說明（本檔案）
├── .gitignore                 # Git 忽略檔案清單
└── 需求.txt                   # 原始需求文件
```

## 🚀 快速開始

### 方式一：立即體驗（無需設定）

1. 直接用瀏覽器開啟 `demo.html`
2. 立即開始使用所有功能
3. 資料儲存在本地瀏覽器中

**適合：** 快速測試、個人使用、不需要多裝置同步

### 方式二：完整版本（雲端同步）

1. 參考 `FIREBASE_SETUP.md` 完成 Firebase 設定
2. 參考 `DEPLOY.md` 部署到 GitHub Pages
3. 使用 Google 帳號登入
4. 在其他裝置用相同 Google 帳號登入即可同步

**適合：** 多裝置同步、個人使用、長期使用

## 🎨 使用說明

### 新增待辦
點擊每個區塊右上角的 `+` 按鈕，輸入內容後送出

### 標記重要
點擊待辦事項旁的 `!` 按鈕，該事項會以紅色底色顯示

### 添加備註
點擊待辦事項旁的 `+` 按鈕，在彈出視窗中輸入備註

### 移動事項
拖曳待辦事項左側的 `⋮⋮` 圖示，移動到目標區塊後放開

### 刪除事項
點擊待辦事項旁的 `×` 按鈕，確認後即可刪除

## 📱 響應式斷點

- **桌面版** (> 1024px)：5 欄週間檢視
- **平板版** (768px - 1024px)：3 欄週間檢視
- **手機橫屏** (480px - 768px)：2 欄週間檢視
- **手機直屏** (< 480px)：1 欄檢視

## 🎨 配色方案

| 區塊 | 主色 | 說明 |
|------|------|------|
| 當周待辦 | 藍色系 (#e3f2fd - #bbdefb) | 清新、專注 |
| 其他待辦 | 橙色系 (#fff3e0 - #ffe0b2) | 溫暖、提醒 |
| 私人待辦 | 粉色系 (#fce4ec - #f8bbd0) | 柔和、私密 |
| 近期關注 | 綠色系 (#e8f5e9 - #c8e6c9) | 平靜、成長 |

## 🔧 技術架構

### 前端技術
- **HTML5** - 語意化標籤
- **CSS3** - Grid、Flexbox、Gradient
- **JavaScript (ES6+)** - 原生 JS，無需框架
- **Drag and Drop API** - 拖曳功能
- **Web Crypto API** - 密碼雜湊

### 後端服務
- **Firebase Google Authentication** - Google 帳號登入
- **Firebase Realtime Database** - 即時資料庫
- **GitHub Pages** - 免費靜態網站託管

## 📊 資料結構

```javascript
users/
  └── {userId}/
      └── todos/
          └── {todoId}/
              ├── text: "待辦內容"
              ├── section: "monday|tuesday|...|others|private|focus"
              ├── important: true|false
              ├── note: "備註內容"
              └── createdAt: 1234567890
```

## 🔒 安全規則

Firebase Realtime Database 安全規則：

```json
{
  "rules": {
    "users": {
      "$uid": {
        ".read": "$uid === auth.uid",
        ".write": "$uid === auth.uid"
      }
    }
  }
}
```

## 🌐 部署建議

### Firebase Hosting（推薦）
```bash
# 安裝 Firebase CLI
npm install -g firebase-tools

# 登入 Firebase
firebase login

# 初始化專案
firebase init hosting

# 部署
firebase deploy
```

### 其他選項
- **Vercel** - 自動部署
- **Netlify** - 拖曳上傳
- **GitHub Pages** - 免費託管

## 💡 使用技巧

1. **快速輸入**：在新增視窗按 Enter 鍵快速送出
2. **批次移動**：先將相關事項移到同一區，再一起處理
3. **重要標記**：善用紅色標記，突顯急迫事項
4. **備註詳細**：在備註欄記錄時間、連結、相關人員等細節
5. **每週規劃**：週日晚上規劃下週待辦，週五檢視完成度

## 🔄 更新記錄

### Version 1.0.0 (2024-12-15)
- ✅ 初始版本發布
- ✅ 四個區塊分類系統
- ✅ 完整待辦事項管理
- ✅ Firebase 雲端同步
- ✅ 響應式設計
- ✅ 拖曳排序功能

## 📝 待開發功能

- [ ] 任務完成打勾功能
- [ ] 截止日期提醒
- [ ] 任務優先級設定
- [ ] 標籤分類系統
- [ ] 資料匯出（CSV/JSON）
- [ ] 深色模式
- [ ] 多語言支援
- [ ] 桌面通知
- [ ] 週報自動生成
- [ ] 任務時間統計
- [ ] 觸控優化的拖曳功能（手機）

## 🤝 貢獻

歡迎提出建議和改進！

## 📄 授權

MIT License - 可自由使用和修改

## 💬 支援

如有問題，請參考：
1. `FIREBASE_SETUP.md` - Firebase 設定詳細教學
2. `DEPLOY.md` - GitHub Pages 部署指南
3. `demo.html` - 功能示範版本（可直接開啟測試）
4. Firebase 官方文件

## 🙏 致謝

感謝使用本專案，希望能提升您的工作效率！

---

**開發日期：** 2024年12月15日  
**版本：** 1.0.0  
**狀態：** ✅ 正式版

