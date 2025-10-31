# 🎯 UI Spec Builder - 互動功能指南

## 🆕 新增功能：互動/功能標記

現在你可以為組件添加各種互動功能標記，讓規格更加完整和清晰！

## 📖 使用方法

### 步驟 1：選擇組件行
在右側「目前結構」區域，**點擊**或**選中**你想添加功能的那一行。

例如：點擊這行
```
├─ Button: "提交表單" (primary)
```

### 步驟 2：選擇互動功能
在左側「⚡ 互動功能」面板中，點擊你想添加的功能按鈕。

### 步驟 3：查看結果
該行會自動添加功能標記：
```
├─ Button: "提交表單" (primary, onClick: handleClick)
```

## 🎨 可用的互動功能

| 功能 | 圖標 | 說明 | 適用組件 |
|------|------|------|----------|
| **onClick** | 👆 | 點擊事件 | Button, Card, Icon, Link |
| **onChange** | 🔄 | 值改變事件 | Input, Select, Checkbox, Radio |
| **onSubmit** | 📤 | 表單提交事件 | Form |
| **onHover** | 👋 | 滑鼠懸停事件 | 任何可互動組件 |
| **onFocus** | 🎯 | 獲得焦點事件 | Input, Textarea, Select |
| **onBlur** | 👁️ | 失去焦點事件 | Input, Textarea, Select |
| **onKeyPress** | ⌨️ | 按鍵事件 | Input, Textarea |
| **onScroll** | 📜 | 滾動事件 | Container, Content |
| **onLoad** | ⏳ | 載入完成事件 | Image, Video, Component |
| **onError** | ⚠️ | 錯誤事件 | Image, Video, Form |
| **onResize** | ↔️ | 尺寸改變事件 | Container, Window |
| **onDrag** | 🖱️ | 拖曳事件 | Card, Item, Element |

## 💡 使用範例

### 範例 1：登入表單

**原始結構：**
```
├─ Form (max-width: 400px)
  ├─ Input Field (placeholder: "Email", type: email)
  ├─ Input Field (placeholder: "密碼", type: password)
  ├─ Button: "登入" (primary)
```

**添加功能後：**
```
├─ Form (max-width: 400px, onSubmit: handleSubmit)
  ├─ Input Field (placeholder: "Email", type: email, onChange: handleEmailChange, onBlur: validateEmail)
  ├─ Input Field (placeholder: "密碼", type: password, onChange: handlePasswordChange)
  ├─ Button: "登入" (primary, onClick: handleLogin)
```

### 範例 2：圖片上傳

**原始結構：**
```
├─ Container
  ├─ Image (src: placeholder.jpg, size: 200x200)
  ├─ Button: "上傳圖片" (secondary)
```

**添加功能後：**
```
├─ Container (onDrag: handleDragOver)
  ├─ Image (src: placeholder.jpg, size: 200x200, onLoad: handleImageLoad, onError: handleImageError)
  ├─ Button: "上傳圖片" (secondary, onClick: handleUpload)
```

### 範例 3：互動式卡片

**原始結構：**
```
├─ Card (title: "產品卡片")
  ├─ Image (src: product.jpg)
  ├─ Button: "加入購物車"
```

**添加功能後：**
```
├─ Card (title: "產品卡片", onClick: handleCardClick, onHover: showDetails)
  ├─ Image (src: product.jpg, onLoad: handleImageLoad)
  ├─ Button: "加入購物車" (onClick: addToCart)
```

### 範例 4：搜尋框

**原始結構：**
```
├─ Input Field (placeholder: "搜尋...", type: search)
```

**添加功能後：**
```
├─ Input Field (placeholder: "搜尋...", type: search, onChange: handleSearch, onKeyPress: handleEnter, onFocus: showSuggestions, onBlur: hideSuggestions)
```

## 🛠️ 快速操作

### 📍 定位選擇
點擊此按鈕會自動：
- 高亮顯示當前選中的行
- 滾動到該行
- 便於確認選擇

### 🗑️ 清除功能
一鍵移除當前行的所有互動功能標記，恢復原始狀態。

## ✨ 功能特色

### 1. 智能函數命名
系統會自動生成語義化的函數名：
- `onClick` → `handleClick`
- `onChange` → `handleChange`
- `onSubmit` → `handleSubmit`
- `onHover` → `handleHover`

### 2. 防重複添加
如果某行已經有某個功能，再次點擊會提示你，避免重複。

### 3. 即時反饋
- 添加成功時會高亮顯示按鈕
- 顯示確認訊息
- 更新選擇資訊

### 4. 保留歷史
所有操作都會保存到歷史記錄，可以使用「↶ 復原」按鈕撤銷。

## 📊 工作流程

```
1. 設計基礎結構
   ↓
2. 點擊要添加功能的組件行
   ↓
3. 在左側面板選擇功能類型
   ↓
4. 系統自動添加功能標記
   ↓
5. 產生規格，查看完整文檔
   ↓
6. 匯出給開發團隊使用
```

## 🎯 最佳實踐

### ✅ 推薦做法

1. **先建結構，後加功能**
   - 先把所有組件和佈局設計好
   - 再為需要互動的組件添加功能

2. **功能要有意義**
   - Button 加 onClick
   - Input 加 onChange
   - Form 加 onSubmit

3. **避免過度標記**
   - 不是每個組件都需要功能
   - 只標記真正需要互動的部分

4. **保持一致性**
   - 相同類型的組件使用相同的功能
   - 統一命名規範

### ❌ 避免做法

1. 不要為靜態組件添加功能（如純文字、圖標）
2. 不要在一個組件上添加太多功能（通常 1-3 個即可）
3. 不要忘記點擊要編輯的行

## 🚀 進階技巧

### 1. 批量操作
如果多個組件需要相同功能：
1. 為第一個組件添加功能
2. 複製該行
3. 修改組件名稱
4. 保留功能標記

### 2. 自定義函數名
你可以手動編輯生成的函數名：
```
(onClick: handleClick) → (onClick: submitForm)
(onChange: handleChange) → (onChange: updateEmail)
```

### 3. 組合使用
多個功能可以組合使用：
```
├─ Input (onChange: handleInput, onFocus: highlight, onBlur: validate, onKeyPress: checkEnter)
```

## 🎨 視覺化輸出

添加互動功能後，在「視覺化」標籤中會看到包含功能標記的 ASCII 圖：

```
╔══════════════════════════════════════════════════╗
║  Button: "提交" (onClick: handleSubmit)          ║
║  Input Field (onChange: handleChange)            ║
╚══════════════════════════════════════════════════╝
```

## 📝 生成的規格文檔

在「AI規格」標籤中，功能標記會自動包含在規格中：

```
組件：Button: "提交"
樣式：primary
互動：onClick: handleSubmit
功能：點擊後觸發表單提交處理函數
```

## 🤝 團隊協作

將帶有功能標記的規格分享給團隊：
1. 設計師知道哪些組件需要互動
2. 開發者清楚要實現哪些事件處理
3. 測試人員了解要測試的互動功能
4. PM 可以追蹤功能完整性

---

## 💬 回饋與建議

使用過程中有任何問題或建議，隨時讓我知道！我們可以：
- 添加更多互動類型
- 改進功能命名
- 增加批量操作
- 優化使用體驗

**祝你設計愉快！** 🎉
