# 🎨 UI Spec Builder

> 一個強大的視覺化 UI 結構規劃工具，讓你輕鬆設計和規劃前端應用程式的介面結構

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-2.0-green.svg)](https://github.com/yourusername/ui-spec-builder)

[English](README_EN.md) | 繁體中文

---

## 📖 目錄

- [✨ 功能特色](#-功能特色)
- [🚀 快速開始](#-快速開始)
- [📚 使用說明](#-使用說明)
- [🧩 組件庫](#-組件庫)
- [⚡ 互動功能](#-互動功能)
- [🎯 使用範例](#-使用範例)
- [📦 文檔](#-文檔)
- [🛠️ 技術棧](#️-技術棧)
- [🤝 貢獻指南](#-貢獻指南)
- [📄 授權](#-授權)

---

## ✨ 功能特色

### 🎯 視覺化編輯
- **實時預覽** - 左側編輯，右側即時顯示樹狀結構
- **拖拉調整** - 可調整面板大小，適應不同工作習慣
- **語法高亮** - ASCII 藝術樹狀結構清晰易讀

### 🧩 豐富組件庫
- **50+ 組件** - 涵蓋佈局、表單、導航、資料展示等
- **一鍵插入** - 點擊即可插入預設結構
- **智能縮排** - 自動處理層級關係

### ⚡ 強大互動功能
- **基礎互動** - onClick, onChange, onSubmit 等 12 種事件
- **進階功能** - validation, debounce, apiCall 等 12 種功能
- **狀態管理** - useState, localStorage, store 等 6 種狀態

### 📊 統計分析
- **即時統計** - 組件數量、行數、互動數量
- **層級深度** - 自動計算結構深度
- **可視化展示** - 數據圖表化呈現

### 💾 專案管理
- **撤銷/重做** - 支援歷史記錄，最多 50 步
- **範本系統** - 內建多種常用範本
- **匯出功能** - 支援多種格式匯出

---

## 🚀 快速開始

### 方法 1：直接使用（推薦）

1. **下載文件**
   ```bash
   git clone https://github.com/yourusername/ui-spec-builder.git
   cd ui-spec-builder
   ```

2. **開啟工具**
   ```bash
   # 直接用瀏覽器開啟
   open ui-spec-builder-advanced.html
   
   # 或使用簡易伺服器
   python -m http.server 8000
   # 然後訪問 http://localhost:8000
   ```

3. **開始設計**
   - 選擇範本或從空白開始
   - 使用組件庫快速搭建結構
   - 添加互動功能
   - 匯出規格文件

### 方法 2：線上使用

訪問 [UI Spec Builder Online](https://yourusername.github.io/ui-spec-builder) （如有部署）

### 系統需求

- 現代瀏覽器（Chrome 90+, Firefox 88+, Safari 14+, Edge 90+）
- 無需安裝任何依賴
- 純前端，單一 HTML 文件

---

## 📚 使用說明

### 基本操作

#### 1️⃣ 建立結構

**手動輸入：**
```
├─ Header (固定在頂部)
├─ Content (主要內容)
  ├─ Button: "點擊" (primary)
  ├─ Table (columns: [欄位1, 欄位2])
└─ Footer (頁尾)
```

**使用組件庫：**
1. 點擊右側組件庫中的組件
2. 組件會自動插入到當前游標位置
3. 調整層級關係（使用空格或 Tab）

#### 2️⃣ 添加互動功能

**方式 A：點擊選擇**
1. 在結構編輯區點擊任意行
2. 點擊左側互動功能按鈕
3. 功能自動添加到選中的行

**方式 B：選中文字**
1. 在結構編輯區選中文字
2. 點擊左側互動功能按鈕
3. 功能添加到選中的組件

**範例：**
```
添加前：
├─ Button: "提交" (primary)

添加 onClick 後：
├─ Button: "提交" (primary, onClick: handleClick)

再添加 loading：
├─ Button: "提交" (primary, onClick: handleClick, loading: true)
```

#### 3️⃣ 使用範本

1. 點擊左上角 **「📋 載入範本」**
2. 選擇需要的範本（管理後台、部落格、電商等）
3. 範本內容自動載入
4. 根據需求調整

#### 4️⃣ 匯出規格

1. 點擊 **「💾 匯出 Spec」**
2. 選擇格式：
   - **📄 純文字** - 複製到文檔
   - **📋 Markdown** - 用於文檔
   - **💻 JSON** - 用於程式處理
3. 下載或複製內容

---

## 🧩 組件庫

### 📐 佈局容器
- Header - 頁面頂部
- Sidebar - 側邊欄
- Content - 內容區域
- Footer - 頁尾
- Container - 容器
- Grid Layout - 網格佈局
- Flex Container - 彈性盒

### 🔘 基礎組件
- Button - 按鈕（7 種樣式）
- Input Field - 輸入框
- Textarea - 多行輸入
- Select Dropdown - 下拉選單
- Checkbox - 核取方塊
- Radio Button - 單選按鈕
- Toggle Switch - 開關
- Slider - 滑桿

### 🧭 導航組件
- Navigation Bar - 導航列
- Menu - 選單
- Tabs - 標籤頁
- Breadcrumb - 麵包屑
- Pagination - 分頁器
- Stepper - 步驟條

### 📊 資料展示
- Table - 表格
- List - 列表
- Card - 卡片
- Avatar - 頭像
- Badge - 徽章
- Chip / Tag - 標籤
- Timeline - 時間軸

### 🔔 反饋組件
- Alert - 警告提示
- Toast - 輕量通知
- Modal Dialog - 對話框
- Drawer - 抽屜
- Tooltip - 提示
- Popover - 彈出框
- Progress Bar - 進度條
- Loading Spinner - 載入動畫

---

## ⚡ 互動功能

### 基礎互動（12 種）

| 功能 | 圖標 | 說明 | 適用組件 |
|------|------|------|----------|
| onClick | 👆 | 點擊事件 | Button, Card, Link, Icon |
| onChange | 🔄 | 值改變事件 | Input, Select, Checkbox |
| onSubmit | 📤 | 表單提交 | Form, Toolbar |
| onHover | 👋 | 滑鼠懸停 | 任何組件 |
| onFocus | 🎯 | 獲得焦點 | Input, Textarea |
| onBlur | 👁️ | 失去焦點 | Input, Textarea |
| onKeyPress | ⌨️ | 按鍵事件 | Input, Textarea |
| onScroll | 📜 | 滾動事件 | Container, List |
| onLoad | ⏳ | 載入完成 | Image, Video |
| onError | ⚠️ | 錯誤事件 | Image, Form |
| onResize | ↔️ | 尺寸改變 | Container, Window |
| onDrag | 🖱️ | 拖曳事件 | Card, Item |

### 進階功能（12 種）

| 功能 | 圖標 | 說明 | 範例 |
|------|------|------|------|
| validation | ✅ | 驗證規則 | `validation: required` |
| debounce | ⏱️ | 防抖延遲 | `debounce: 300ms` |
| throttle | 🎚️ | 節流限制 | `throttle: 500ms` |
| apiCall | 🌐 | API 調用 | `apiCall: "/api/save"` |
| loading | ⌛ | 載入狀態 | `loading: true` |
| disabled | 🚫 | 禁用狀態 | `disabled: false` |
| animation | ✨ | 動畫效果 | `animation: fadeIn` |
| tooltip | 💬 | 提示訊息 | `tooltip: "說明"` |
| conditional | 🔀 | 條件顯示 | `conditional: if(isAdmin)` |
| permission | 🔐 | 權限控制 | `permission: admin` |
| tracking | 📊 | 行為追蹤 | `tracking: analytics` |
| confirm | ❓ | 確認對話框 | `confirm: "確定?"` |

### 狀態管理（6 種）

| 功能 | 圖標 | 說明 | 範例 |
|------|------|------|------|
| useState | 📦 | 組件狀態 | `useState: [value, setValue]` |
| computed | 🧮 | 計算屬性 | `computed: calculateTotal` |
| watch | 👀 | 監聽變化 | `watch: onValueChange` |
| store | 🏪 | 全局狀態 | `store: globalStore` |
| localStorage | 💿 | 本地儲存 | `localStorage: "userData"` |
| sessionStorage | 🔖 | 會話儲存 | `sessionStorage: "tempData"` |

---

## 🎯 使用範例

### 範例 1：簡單登入表單

```
├─ Container (max-width: 400px)
  ├─ Form (onSubmit: handleLogin, validation: required)
    ├─ Input Field (placeholder: "Email", type: email, onChange: handleEmailChange, validation: email)
    ├─ Input Field (placeholder: "密碼", type: password, onChange: handlePasswordChange, validation: min:8)
    ├─ Checkbox: "記住我" (onChange: handleRemember, localStorage: "rememberMe")
    ├─ Button: "登入" (primary, onClick: handleSubmit, apiCall: "/api/login", loading: true)
```

### 範例 2：資料表格頁面

```
├─ Container (max-width: 1200px)
  ├─ Toolbar (操作區, onSubmit: handleSearch)
    ├─ Input Field (placeholder: "搜尋", type: search, onChange: handleSearchChange, debounce: 300ms)
    ├─ Button: "新增" (primary, onClick: handleAdd, permission: admin)
  ├─ Table (columns: [姓名, Email, 狀態], sortable: true, pagination: true, apiCall: "/api/users", loading: true)
  ├─ Pagination (total: 100, perPage: 20, onChange: handlePageChange)
```

### 範例 3：互動式儀表板

```
├─ Container (max-width: 1400px, store: dashboardStore)
  ├─ Header (固定在頂部, onScroll: handleScroll)
  ├─ Grid Layout (columns: 4, gap: 20px, responsive: true)
    ├─ Card (title: "總用戶", animation: fadeIn, onClick: handleUserCard)
    ├─ Card (title: "今日訪客", animation: fadeIn)
    ├─ Card (title: "銷售額", animation: fadeIn)
    ├─ Card (title: "訂單數", animation: fadeIn)
  ├─ Card (title: "銷售趨勢")
    ├─ Chart (type: line, apiCall: "/api/chart/sales", loading: true)
```

---

## 📦 文檔

### 完整指南
- **[組件與功能完整指南](COMPLETE-GUIDE.md)** - 所有組件和功能的詳細說明
- **[互動功能使用指南](INTERACTION-GUIDE.md)** - 互動功能的使用方法
- **[實現對照指南](IMPLEMENTATION-GUIDE.md)** - 規格與實現的對照

### 快速參考
- **組件速查表** - 快速查找組件（見 COMPLETE-GUIDE.md）
- **互動功能速查表** - 快速查找互動功能（見 COMPLETE-GUIDE.md）
- **常見問題** - 使用過程中的常見問題

---

## 🛠️ 技術棧

### 核心技術
- **HTML5** - 結構標記
- **CSS3** - 樣式設計
  - Flexbox / Grid Layout
  - CSS Variables
  - Animations & Transitions
- **Vanilla JavaScript** - 無框架依賴
  - ES6+ 語法
  - 事件處理
  - DOM 操作
  - Local Storage API

### 特色
- ✅ **零依賴** - 無需安裝任何套件
- ✅ **單文件** - 一個 HTML 文件包含所有功能
- ✅ **純前端** - 無需後端服務
- ✅ **響應式** - 適配各種螢幕尺寸
- ✅ **離線可用** - 無需網路連線

---

## 🎨 開發

### 本地開發

```bash
# 複製專案
git clone https://github.com/yourusername/ui-spec-builder.git
cd ui-spec-builder

# 啟動開發伺服器（可選）
python -m http.server 8000

# 或使用 Node.js
npx http-server -p 8000

# 訪問 http://localhost:8000
```

### 文件結構

```
ui-spec-builder/
├── ui-spec-builder-advanced.html    # 主程式（進階版）
├── ui-spec-builder-ascii.html       # 基礎版本
├── interactive-page.html            # 互動功能展示頁面
├── README.md                        # 本文件
├── COMPLETE-GUIDE.md               # 完整使用指南
├── IMPLEMENTATION-GUIDE.md         # 實現指南
└── LICENSE                         # MIT 授權
```

### 自訂組件

你可以編輯 HTML 文件中的 `componentTemplates` 物件來添加自己的組件：

```javascript
const componentTemplates = {
    'custom': {
        name: '自訂組件',
        emoji: '🎯',
        template: '├─ CustomComponent (prop: value)',
        category: 'custom'
    }
};
```

---

## 🤝 貢獻指南

我們歡迎所有形式的貢獻！

### 如何貢獻

1. **Fork 專案**
   ```bash
   git fork https://github.com/yourusername/ui-spec-builder.git
   ```

2. **創建分支**
   ```bash
   git checkout -b feature/amazing-feature
   ```

3. **提交變更**
   ```bash
   git commit -m "Add: 添加某個功能"
   ```

4. **推送分支**
   ```bash
   git push origin feature/amazing-feature
   ```

5. **發起 Pull Request**

### 貢獻類型

- 🐛 **Bug 修復** - 回報或修復問題
- ✨ **新功能** - 添加新組件或功能
- 📝 **文檔** - 改善文檔或範例
- 🎨 **設計** - UI/UX 改進
- ⚡ **效能** - 效能優化
- 🌐 **翻譯** - 多語言支援

### 開發規範

- 使用語義化的提交訊息
- 保持代碼風格一致
- 添加必要的註解
- 更新相關文檔

---

## 📊 專案統計

- **組件數量：** 50+
- **互動功能：** 30+
- **內建範本：** 10+
- **文件大小：** < 200KB
- **支援瀏覽器：** 所有現代瀏覽器

---

## 🗺️ Roadmap

### v2.1（規劃中）
- [ ] 協作功能（多人編輯）
- [ ] 版本控制（Git 整合）
- [ ] 組件商店（社群分享）
- [ ] AI 輔助（智能建議）

### v2.2（規劃中）
- [ ] 代碼生成（React/Vue/Angular）
- [ ] 設計系統整合（Figma/Sketch）
- [ ] 雲端同步
- [ ] 更多範本

---

## 🙏 致謝

感謝所有貢獻者和使用者！

特別感謝：
- 所有提供回饋的使用者
- 開源社群的支持
- Claude AI 的協助

---

## 📞 聯絡方式

- **Issues：** [提交問題](https://github.com/yourusername/ui-spec-builder/issues)
- **Discussions：** [參與討論](https://github.com/yourusername/ui-spec-builder/discussions)

---

## 📄 授權

本專案採用 [MIT License](LICENSE) 授權。

```
MIT License

Copyright (c) 2025

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## ⭐ Star History

如果這個專案對你有幫助，請給我們一個 ⭐ Star！

---

<div align="center">

**用 ❤️ 製作**

[回到頂部](#-ui-spec-builder)

</div>
