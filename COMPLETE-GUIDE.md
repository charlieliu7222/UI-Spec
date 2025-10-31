# 📚 UI Spec Builder - 完整組件與功能指南

## 📖 目錄

1. [組件庫](#組件庫)
2. [基礎互動功能](#基礎互動功能)
3. [進階功能](#進階功能)
4. [狀態管理](#狀態管理)
5. [使用範例](#使用範例)
6. [最佳實踐](#最佳實踐)

---

## 🧩 組件庫

### 📐 佈局容器

#### Header
**用途：** 頁面頂部導航區域  
**結構：** `├─ Header (固定在頂部)`  
**常用屬性：**
- `position: fixed` - 固定定位
- `sticky: true` - 黏性定位
- `height: 64px` - 高度設定

**適用互動：**
- onClick - 點擊 Header
- onScroll - 滾動時觸發
- onResize - 尺寸改變

**範例：**
```
├─ Header (固定在頂部, onClick: handleHeaderClick, onScroll: handleScroll)
```

---

#### Toolbar
**用途：** 工具列、操作區  
**結構：** `├─ Toolbar (操作區)`  
**常用屬性：**
- `position: fixed` - 固定在頁面
- `items: [...]` - 工具項目

**適用互動：**
- onSubmit - 表單提交（如搜尋）
- onClick - 按鈕點擊

**範例：**
```
├─ Toolbar (操作區, onSubmit: handleSearch)
```

---

#### Sidebar
**用途：** 側邊欄導航  
**結構：** `├─ Sidebar (側邊欄, width: 300px)`  
**常用屬性：**
- `width: 240px/300px` - 寬度
- `position: left/right` - 位置
- `collapsible: true` - 可收合

**適用互動：**
- onClick - 展開/收合
- onHover - 懸停展開

**範例：**
```
├─ Sidebar (側邊欄, width: 300px, collapsible: true, onClick: handleToggle)
```

---

#### Content
**用途：** 主要內容區域  
**結構：** `├─ Content (主要內容)`  
**常用屬性：**
- `max-width: 1200px` - 最大寬度
- `padding: 24px` - 內距

**適用互動：**
- onScroll - 滾動事件
- onLoad - 內容載入

**範例：**
```
├─ Content (主要內容, max-width: 1200px)
  ├─ Card (title: "卡片標題")
```

---

#### Footer
**用途：** 頁尾資訊  
**結構：** `└─ Footer (頁尾)`  
**常用屬性：**
- `position: fixed` - 固定底部
- `sticky: true` - 黏性底部

**範例：**
```
└─ Footer (頁尾, copyright: "© 2025")
```

---

#### Container
**用途：** 通用容器  
**結構：** `├─ Container (max-width: 1200px)`  
**常用屬性：**
- `max-width` - 最大寬度
- `padding` - 內距
- `margin` - 外距

**範例：**
```
├─ Container (max-width: 1200px)
  ├─ Grid Layout (columns: 3)
```

---

#### Grid Layout
**用途：** 網格佈局  
**結構：** `├─ Grid Layout (columns: 3, gap: 16px)`  
**常用屬性：**
- `columns: 2/3/4` - 欄數
- `gap: 16px/24px` - 間距
- `responsive: true` - 響應式

**範例：**
```
├─ Grid Layout (columns: 3, gap: 16px, responsive: true)
  ├─ Card
  ├─ Card
  ├─ Card
```

---

#### Flex Container
**用途：** 彈性盒佈局  
**結構：** `├─ Flex Container (justify: space-between, align: center)`  
**常用屬性：**
- `justify: flex-start/center/space-between` - 主軸對齊
- `align: flex-start/center/flex-end` - 交叉軸對齊
- `direction: row/column` - 方向
- `wrap: wrap/nowrap` - 換行

**範例：**
```
├─ Flex Container (justify: space-between, align: center, direction: row)
  ├─ Button: "左側按鈕"
  ├─ Button: "右側按鈕"
```

---

### 🔘 基礎組件

#### Button
**用途：** 按鈕  
**結構：** `├─ Button: "按鈕文字" (primary)`  
**樣式變體：**
- `primary` - 主要按鈕
- `secondary` - 次要按鈕
- `danger` - 危險操作
- `success` - 成功操作
- `ghost` - 幽靈按鈕
- `link` - 連結樣式

**常用屬性：**
- `size: small/medium/large` - 尺寸
- `icon: "icon-name"` - 圖標
- `loading: true` - 載入狀態
- `disabled: true` - 禁用狀態

**適用互動：**
- onClick - 點擊事件 ⭐
- onHover - 懸停效果
- onFocus - 獲得焦點

**適用進階功能：**
- loading - 載入狀態
- disabled - 禁用控制
- confirm - 確認對話框
- permission - 權限控制
- tracking - 追蹤點擊

**範例：**
```
├─ Button: "提交表單" (primary, size: large, onClick: handleSubmit, loading: true, confirm: "確定提交?")
```

---

#### Input Field
**用途：** 輸入框  
**結構：** `├─ Input Field (placeholder: "請輸入...", type: text)`  
**類型：**
- `text` - 文字
- `email` - 電子郵件
- `password` - 密碼
- `number` - 數字
- `tel` - 電話
- `url` - 網址
- `search` - 搜尋

**常用屬性：**
- `placeholder` - 佔位文字
- `maxLength: 50` - 最大長度
- `required: true` - 必填
- `disabled: true` - 禁用

**適用互動：**
- onChange - 值改變 ⭐
- onFocus - 獲得焦點
- onBlur - 失去焦點
- onKeyPress - 按鍵事件

**適用進階功能：**
- validation - 驗證規則 ⭐
- debounce - 防抖
- tooltip - 提示訊息
- disabled - 禁用狀態

**適用狀態管理：**
- useState - 綁定值
- watch - 監聽變化

**範例：**
```
├─ Input Field (placeholder: "Email", type: email, onChange: handleEmailChange, onBlur: validateEmail, validation: required, debounce: 300ms, useState: [email, setEmail])
```

---

#### Textarea
**用途：** 多行文字輸入  
**結構：** `├─ Textarea (placeholder: "請輸入內容...", rows: 4)`  
**常用屬性：**
- `rows: 4/6/8` - 行數
- `maxLength: 500` - 最大長度
- `resize: vertical/none` - 調整大小

**適用互動：**
- onChange - 值改變
- onFocus - 獲得焦點
- onBlur - 失去焦點

**適用進階功能：**
- validation - 驗證
- debounce - 防抖

**範例：**
```
├─ Textarea (placeholder: "意見回饋", rows: 6, onChange: handleChange, validation: required, debounce: 500ms)
```

---

#### Select Dropdown
**用途：** 下拉選單  
**結構：** `├─ Select Dropdown (options: [選項1, 選項2, 選項3])`  
**常用屬性：**
- `options: [...]` - 選項列表
- `multiple: true` - 多選
- `searchable: true` - 可搜尋

**適用互動：**
- onChange - 選擇改變 ⭐
- onFocus - 獲得焦點

**適用進階功能：**
- validation - 驗證
- apiCall - 遠端載入選項

**範例：**
```
├─ Select Dropdown (options: [台北, 台中, 高雄], searchable: true, onChange: handleCityChange, validation: required)
```

---

#### Checkbox
**用途：** 核取方塊  
**結構：** `├─ Checkbox: "同意條款"`  
**常用屬性：**
- `checked: true/false` - 預設狀態
- `indeterminate: true` - 不確定狀態

**適用互動：**
- onChange - 勾選狀態改變 ⭐

**適用進階功能：**
- validation - 驗證（必須勾選）

**適用狀態管理：**
- useState - 綁定狀態

**範例：**
```
├─ Checkbox: "同意服務條款" (onChange: handleAgree, validation: required, useState: [agreed, setAgreed])
```

---

#### Radio Button
**用途：** 單選按鈕  
**結構：** `├─ Radio Button Group: [選項1, 選項2]`  
**常用屬性：**
- `options: [...]` - 選項列表
- `defaultValue` - 預設值

**適用互動：**
- onChange - 選擇改變

**範例：**
```
├─ Radio Button Group: [男性, 女性, 其他] (defaultValue: "男性", onChange: handleGenderChange)
```

---

#### Toggle Switch
**用途：** 開關切換  
**結構：** `├─ Toggle Switch: "啟用功能"`  
**常用屬性：**
- `checked: true/false` - 狀態
- `disabled: true` - 禁用

**適用互動：**
- onChange - 狀態改變 ⭐

**適用狀態管理：**
- useState - 綁定狀態

**範例：**
```
├─ Toggle Switch: "啟用通知" (onChange: handleToggle, useState: [enabled, setEnabled])
```

---

#### Slider
**用途：** 滑桿  
**結構：** `├─ Slider (min: 0, max: 100, value: 50)`  
**常用屬性：**
- `min` - 最小值
- `max` - 最大值
- `step: 1` - 步進值
- `marks: true` - 顯示刻度

**適用互動：**
- onChange - 值改變

**適用進階功能：**
- debounce - 防抖
- throttle - 節流

**範例：**
```
├─ Slider (min: 0, max: 100, step: 10, onChange: handleVolumeChange, throttle: 100ms)
```

---

### 🧭 導航組件

#### Navigation Bar
**用途：** 導航列  
**結構：** `├─ Navigation Bar (items: [首頁, 關於, 聯絡])`  
**常用屬性：**
- `items: [...]` - 導航項目
- `position: top/bottom` - 位置
- `sticky: true` - 黏性定位

**適用互動：**
- onClick - 項目點擊
- onHover - 懸停展開子選單

**範例：**
```
├─ Navigation Bar (items: [首頁, 產品, 關於我們], sticky: true, onClick: handleNavClick)
```

---

#### Menu
**用途：** 選單  
**結構：** `├─ Menu (vertical)`  
**類型：**
- `vertical` - 垂直選單
- `horizontal` - 水平選單

**常用屬性：**
- `collapsible: true` - 可收合
- `accordion: true` - 手風琴模式

**適用互動：**
- onClick - 項目點擊
- onExpand - 展開事件

**範例：**
```
├─ Menu (vertical, collapsible: true)
  ├─ MenuItem: "首頁"
  ├─ SubMenu: "產品"
    ├─ MenuItem: "產品 A"
```

---

#### Tabs
**用途：** 分頁標籤  
**結構：** `├─ Tabs (tabs: [標籤1, 標籤2, 標籤3])`  
**常用屬性：**
- `tabs: [...]` - 標籤列表
- `defaultActive: 0` - 預設活動標籤
- `type: line/card` - 樣式

**適用互動：**
- onChange - 切換標籤

**適用狀態管理：**
- useState - 當前標籤

**範例：**
```
├─ Tabs (tabs: [基本資訊, 進階設定, 權限管理], type: card, onChange: handleTabChange, useState: [activeTab, setActiveTab])
```

---

#### Breadcrumb
**用途：** 麵包屑導航  
**結構：** `├─ Breadcrumb (path: 首頁 > 分類 > 頁面)`  
**常用屬性：**
- `path` - 路徑
- `separator: "/" / ">"` - 分隔符

**適用互動：**
- onClick - 項目點擊

**範例：**
```
├─ Breadcrumb (path: 首頁 > 產品列表 > 產品詳情, onClick: handleBreadcrumbClick)
```

---

#### Pagination
**用途：** 分頁器  
**結構：** `├─ Pagination (total: 100, perPage: 20)`  
**常用屬性：**
- `total` - 總數
- `perPage` - 每頁數量
- `current: 1` - 當前頁

**適用互動：**
- onChange - 頁碼改變

**適用進階功能：**
- apiCall - API 請求資料

**範例：**
```
├─ Pagination (total: 100, perPage: 20, onChange: handlePageChange, apiCall: "/api/items")
```

---

#### Stepper
**用途：** 步驟條  
**結構：** `├─ Stepper (steps: [步驟1, 步驟2, 步驟3], current: 1)`  
**常用屬性：**
- `steps: [...]` - 步驟列表
- `current` - 當前步驟

**適用互動：**
- onChange - 步驟改變

**適用狀態管理：**
- useState - 當前步驟

**範例：**
```
├─ Stepper (steps: [填寫資料, 確認資訊, 完成], current: 1, onChange: handleStepChange, useState: [step, setStep])
```

---

### 📊 資料展示

#### Table
**用途：** 資料表格  
**結構：** `├─ Table (columns: [欄位1, 欄位2, 欄位3])`  
**常用屬性：**
- `columns: [...]` - 欄位定義
- `sortable: true` - 可排序
- `selectable: true` - 可選擇
- `pagination: true` - 分頁

**適用互動：**
- onRowClick - 行點擊
- onSort - 排序
- onSelect - 選擇

**適用進階功能：**
- apiCall - API 載入資料
- loading - 載入狀態

**範例：**
```
├─ Table (columns: [姓名, Email, 狀態], sortable: true, pagination: true, onRowClick: handleRowClick, apiCall: "/api/users", loading: true)
```

---

#### List
**用途：** 列表  
**結構：** `├─ List (items: [項目1, 項目2, 項目3])`  
**常用屬性：**
- `items: [...]` - 項目
- `virtualized: true` - 虛擬滾動
- `infinite: true` - 無限滾動

**適用互動：**
- onItemClick - 項目點擊
- onScroll - 滾動載入更多

**範例：**
```
├─ List (items: [...], virtualized: true, onItemClick: handleItemClick, onScroll: loadMore)
```

---

#### Card
**用途：** 卡片容器  
**結構：** `├─ Card (title: "卡片標題")`  
**常用屬性：**
- `title` - 標題
- `bordered: true` - 邊框
- `hoverable: true` - 可懸停

**適用互動：**
- onClick - 點擊卡片
- onHover - 懸停效果

**適用進階功能：**
- animation - 進入動畫

**範例：**
```
├─ Card (title: "產品卡片", hoverable: true, onClick: handleCardClick, animation: fadeIn)
```

---

#### Avatar
**用途：** 頭像  
**結構：** `├─ Avatar (size: 48px, src: "user.jpg")`  
**常用屬性：**
- `size: 32/48/64px` - 尺寸
- `src` - 圖片來源
- `shape: circle/square` - 形狀

**範例：**
```
├─ Avatar (size: 48px, src: "avatar.jpg", shape: circle)
```

---

#### Badge
**用途：** 徽章  
**結構：** `├─ Badge: "新" (color: primary)`  
**常用屬性：**
- `color: primary/success/danger` - 顏色
- `dot: true` - 小圓點樣式

**範例：**
```
├─ Badge: "熱門" (color: danger)
```

---

#### Chip / Tag
**用途：** 標籤  
**結構：** `├─ Chip: "標籤" (closable: true)`  
**常用屬性：**
- `closable: true` - 可關閉
- `color` - 顏色

**適用互動：**
- onClose - 關閉事件

**範例：**
```
├─ Chip: "React" (color: blue, closable: true, onClose: handleClose)
```

---

#### Timeline
**用途：** 時間軸  
**結構：** `├─ Timeline (items: [事件1, 事件2, 事件3])`  
**常用屬性：**
- `items: [...]` - 事件列表
- `mode: left/right/alternate` - 模式

**範例：**
```
├─ Timeline (items: [2024-01: 創立, 2024-06: 上線], mode: alternate)
```

---

### 🔔 反饋組件

#### Alert
**用途：** 警告提示  
**結構：** `├─ Alert: "提示訊息" (type: info)`  
**類型：**
- `info` - 資訊
- `success` - 成功
- `warning` - 警告
- `error` - 錯誤

**常用屬性：**
- `closable: true` - 可關閉
- `icon: true` - 顯示圖標

**適用互動：**
- onClose - 關閉事件

**範例：**
```
├─ Alert: "操作成功！" (type: success, closable: true, onClose: handleClose)
```

---

#### Toast / Snackbar
**用途：** 輕量級通知  
**結構：** `├─ Toast: "操作成功" (type: success, duration: 3000ms)`  
**常用屬性：**
- `duration: 3000ms` - 顯示時長
- `position: top/bottom` - 位置

**範例：**
```
├─ Toast: "已儲存" (type: success, duration: 2000ms, position: top)
```

---

#### Modal / Dialog
**用途：** 模態對話框  
**結構：** `├─ Modal Dialog (title: "標題", width: 500px)`  
**常用屬性：**
- `title` - 標題
- `width` - 寬度
- `closable: true` - 可關閉
- `maskClosable: true` - 點擊遮罩關閉

**適用互動：**
- onOpen - 開啟
- onClose - 關閉
- onConfirm - 確認

**適用進階功能：**
- confirm - 確認對話框

**範例：**
```
├─ Modal Dialog (title: "確認刪除", width: 400px, onConfirm: handleDelete, confirm: "確定刪除嗎?")
```

---

#### Drawer
**用途：** 抽屜  
**結構：** `├─ Drawer (position: right, width: 400px)`  
**常用屬性：**
- `position: left/right/top/bottom` - 位置
- `width/height` - 尺寸

**適用互動：**
- onOpen - 開啟
- onClose - 關閉

**範例：**
```
├─ Drawer (position: right, width: 400px, onOpen: handleOpen, onClose: handleClose)
```

---

#### Tooltip
**用途：** 提示訊息  
**結構：** `├─ Tooltip: "提示文字"`  
**常用屬性：**
- `placement: top/bottom/left/right` - 位置
- `trigger: hover/click` - 觸發方式

**範例：**
```
├─ Tooltip: "點擊編輯" (placement: top, trigger: hover)
```

---

#### Popover
**用途：** 彈出框  
**結構：** `├─ Popover (trigger: click)`  
**常用屬性：**
- `trigger: click/hover` - 觸發方式
- `title` - 標題

**適用互動：**
- onClick - 點擊觸發
- onHover - 懸停觸發

**範例：**
```
├─ Popover (title: "更多選項", trigger: click, onClick: handlePopover)
```

---

#### Progress Bar
**用途：** 進度條  
**結構：** `├─ Progress Bar (value: 60%, color: primary)`  
**常用屬性：**
- `value: 0-100%` - 進度值
- `showInfo: true` - 顯示資訊

**適用狀態管理：**
- useState - 進度值

**範例：**
```
├─ Progress Bar (value: 75%, color: success, showInfo: true, useState: [progress, setProgress])
```

---

#### Loading Spinner
**用途：** 載入動畫  
**結構：** `├─ Loading Spinner (size: medium)`  
**常用屬性：**
- `size: small/medium/large` - 尺寸
- `fullscreen: true` - 全螢幕

**範例：**
```
├─ Loading Spinner (size: large, fullscreen: true)
```

---

#### Skeleton
**用途：** 骨架屏  
**結構：** `├─ Skeleton`  
**常用屬性：**
- `rows: 3` - 行數
- `active: true` - 動畫效果

**範例：**
```
├─ Skeleton (rows: 3, active: true)
```

---

### 🎯 其他組件

#### Dropdown
**用途：** 下拉選單  
**結構：** `├─ Dropdown`  
**適用互動：**
- onClick - 觸發
- onChange - 選擇改變

**範例：**
```
├─ Dropdown (items: [編輯, 刪除, 分享], onClick: handleDropdown)
```

---

#### Accordion
**用途：** 手風琴  
**結構：** `├─ Accordion`  
**常用屬性：**
- `multiple: true` - 多個展開

**適用互動：**
- onChange - 展開/收合

**範例：**
```
├─ Accordion (multiple: false, onChange: handleAccordion)
```

---

#### Carousel
**用途：** 輪播圖  
**結構：** `├─ Carousel`  
**常用屬性：**
- `autoplay: true` - 自動播放
- `interval: 3000ms` - 間隔

**適用互動：**
- onChange - 切換事件

**範例：**
```
├─ Carousel (autoplay: true, interval: 3000ms, onChange: handleSlide)
```

---

#### Divider
**用途：** 分隔線  
**結構：** `├─ Divider`  
**常用屬性：**
- `orientation: horizontal/vertical` - 方向

**範例：**
```
├─ Divider (orientation: horizontal)
```

---

#### Icon
**用途：** 圖標  
**結構：** `├─ Icon (name: "home")`  
**常用屬性：**
- `name` - 圖標名稱
- `size: 16/24/32px` - 尺寸

**範例：**
```
├─ Icon (name: "user", size: 24px)
```

---

#### Image
**用途：** 圖片  
**結構：** `├─ Image (src: "image.jpg")`  
**常用屬性：**
- `src` - 來源
- `alt` - 替代文字
- `lazy: true` - 延遲載入

**適用互動：**
- onLoad - 載入完成
- onError - 載入錯誤

**範例：**
```
├─ Image (src: "banner.jpg", lazy: true, onLoad: handleImageLoad, onError: handleImageError)
```

---

#### Video
**用途：** 影片  
**結構：** `├─ Video (src: "video.mp4")`  
**常用屬性：**
- `src` - 來源
- `autoplay: true` - 自動播放
- `controls: true` - 顯示控制項

**適用互動：**
- onPlay - 播放
- onPause - 暫停
- onEnded - 結束

**範例：**
```
├─ Video (src: "intro.mp4", controls: true, onPlay: handlePlay)
```

---

#### Form
**用途：** 表單容器  
**結構：** `├─ Form`  
**常用屬性：**
- `layout: vertical/horizontal` - 佈局

**適用互動：**
- onSubmit - 提交表單 ⭐
- onChange - 表單值改變

**適用進階功能：**
- validation - 表單驗證 ⭐

**範例：**
```
├─ Form (layout: vertical, onSubmit: handleFormSubmit, validation: required)
  ├─ Input Field (name: "username")
  ├─ Input Field (name: "password", type: password)
  ├─ Button: "登入" (primary)
```

---

## ⚡ 基礎互動功能

### onClick
**圖標：** 👆  
**用途：** 點擊事件  
**適用組件：** Button, Card, Link, Icon, Header, Menu, etc.  
**函數生成：** handleClick  

**使用方式：**
1. 選擇組件行
2. 點擊 onClick 按鈕
3. 自動添加 `onClick: handleClick`

**範例：**
```
├─ Button: "提交" (primary, onClick: handleClick)
├─ Card (title: "產品", onClick: handleCardClick)
├─ Icon (name: "delete", onClick: handleDelete)
```

---

### onChange
**圖標：** 🔄  
**用途：** 值改變事件  
**適用組件：** Input, Select, Checkbox, Radio, Switch, Slider, Textarea  
**函數生成：** handleChange  

**使用方式：**
1. 選擇輸入組件行
2. 點擊 onChange 按鈕
3. 自動添加 `onChange: handleChange`

**範例：**
```
├─ Input Field (placeholder: "Email", onChange: handleEmailChange)
├─ Select Dropdown (options: [...], onChange: handleSelectChange)
├─ Checkbox: "同意" (onChange: handleAgree)
```

---

### onSubmit
**圖標：** 📤  
**用途：** 表單提交事件  
**適用組件：** Form, Toolbar (搜尋表單)  
**函數生成：** handleSubmit  

**使用方式：**
1. 選擇 Form 或 Toolbar 行
2. 點擊 onSubmit 按鈕
3. 自動添加 `onSubmit: handleSubmit`

**範例：**
```
├─ Form (onSubmit: handleFormSubmit)
  ├─ Input Field (name: "email")
  ├─ Button: "提交"
```

---

### onHover
**圖標：** 👋  
**用途：** 滑鼠懸停事件  
**適用組件：** 任何可互動組件  
**函數生成：** handleHover  

**範例：**
```
├─ Card (title: "產品", onHover: showDetails)
├─ Button: "查看" (onHover: handleHover)
```

---

### onFocus
**圖標：** 🎯  
**用途：** 獲得焦點事件  
**適用組件：** Input, Textarea, Select  
**函數生成：** handleFocus  

**範例：**
```
├─ Input Field (placeholder: "搜尋", onFocus: handleFocus)
```

---

### onBlur
**圖標：** 👁️  
**用途：** 失去焦點事件  
**適用組件：** Input, Textarea, Select  
**函數生成：** handleBlur  
**常見用途：** 欄位驗證

**範例：**
```
├─ Input Field (placeholder: "Email", onBlur: validateEmail)
```

---

### onKeyPress
**圖標：** ⌨️  
**用途：** 按鍵事件  
**適用組件：** Input, Textarea  
**函數生成：** handleKeyPress  
**常見用途：** Enter 搜尋、快捷鍵

**範例：**
```
├─ Input Field (placeholder: "搜尋", onKeyPress: handleEnterSearch)
```

---

### onScroll
**圖標：** 📜  
**用途：** 滾動事件  
**適用組件：** Container, Content, List, Header  
**函數生成：** handleScroll  
**常見用途：** 無限滾動、固定 Header

**範例：**
```
├─ Header (固定在頂部, onScroll: handleScroll)
├─ List (items: [...], onScroll: loadMore)
```

---

### onLoad
**圖標：** ⏳  
**用途：** 載入完成事件  
**適用組件：** Image, Video, Component  
**函數生成：** handleLoad  

**範例：**
```
├─ Image (src: "banner.jpg", onLoad: handleImageLoad)
├─ Component (onLoad: initializeComponent)
```

---

### onError
**圖標：** ⚠️  
**用途：** 錯誤事件  
**適用組件：** Image, Video, Form, API 調用  
**函數生成：** handleError  

**範例：**
```
├─ Image (src: "photo.jpg", onError: handleImageError)
├─ Form (onSubmit: handleSubmit, onError: handleFormError)
```

---

### onResize
**圖標：** ↔️  
**用途：** 尺寸改變事件  
**適用組件：** Container, Window, Responsive Layout  
**函數生成：** handleResize  

**範例：**
```
├─ Container (max-width: 1200px, onResize: handleResize)
```

---

### onDrag
**圖標：** 🖱️  
**用途：** 拖曳事件  
**適用組件：** Card, Item, Element, List  
**函數生成：** handleDrag  
**常見用途：** 拖放排序、拖放上傳

**範例：**
```
├─ Card (title: "可拖曳", onDrag: handleDragCard)
├─ List (items: [...], onDrag: handleDragSort)
```

---

## 🚀 進階功能

### validation
**圖標：** ✅  
**用途：** 驗證規則  
**適用組件：** Input, Textarea, Select, Checkbox, Form  
**標記格式：** `validation: required` / `validation: email` / `validation: custom`  

**驗證類型：**
- `required` - 必填
- `email` - Email 格式
- `phone` - 電話格式
- `url` - URL 格式
- `min: 8` - 最小長度
- `max: 50` - 最大長度
- `pattern: /regex/` - 正則表達式
- `custom: validateFunction` - 自訂函數

**使用方式：**
1. 選擇輸入組件
2. 點擊 validation 按鈕
3. 預設添加 `validation: required`
4. 可手動修改為其他驗證規則

**範例：**
```
├─ Input Field (placeholder: "Email", validation: email, onChange: handleChange)
├─ Input Field (placeholder: "密碼", type: password, validation: min:8, onChange: handlePassword)
├─ Checkbox: "同意條款" (validation: required, onChange: handleAgree)
├─ Form (onSubmit: handleSubmit, validation: required)
```

---

### debounce
**圖標：** ⏱️  
**用途：** 防抖，延遲執行  
**適用組件：** Input (搜尋), Textarea  
**標記格式：** `debounce: 300ms`  
**常見值：** 200ms, 300ms, 500ms

**使用場景：**
- 搜尋框即時搜尋
- 自動儲存
- API 請求優化

**範例：**
```
├─ Input Field (placeholder: "搜尋", onChange: handleSearch, debounce: 300ms)
├─ Textarea (placeholder: "內容", onChange: autoSave, debounce: 1000ms)
```

---

### throttle
**圖標：** 🎚️  
**用途：** 節流，限制執行頻率  
**適用組件：** Slider, Scroll, Resize  
**標記格式：** `throttle: 500ms`  
**常見值：** 100ms, 200ms, 500ms

**使用場景：**
- 滾動事件
- 視窗縮放
- 滑桿拖動

**範例：**
```
├─ Slider (min: 0, max: 100, onChange: handleChange, throttle: 100ms)
├─ Container (onScroll: handleScroll, throttle: 200ms)
```

---

### apiCall
**圖標：** 🌐  
**用途：** API 調用  
**適用組件：** Button, Form, Table, Select, Pagination  
**標記格式：** `apiCall: "/api/endpoint"`  

**使用場景：**
- 提交表單到後端
- 載入資料表格
- 遠端搜尋選項
- 分頁載入

**範例：**
```
├─ Button: "儲存" (primary, onClick: handleSave, apiCall: "/api/save")
├─ Table (columns: [...], apiCall: "/api/users", loading: true)
├─ Select Dropdown (searchable: true, apiCall: "/api/cities")
├─ Pagination (total: 100, perPage: 20, apiCall: "/api/items?page={page}")
```

---

### loading
**圖標：** ⌛  
**用途：** 載入狀態  
**適用組件：** Button, Table, Container, Component  
**標記格式：** `loading: true`  

**使用場景：**
- 按鈕提交中
- 資料載入中
- 頁面初始化

**範例：**
```
├─ Button: "提交" (primary, onClick: handleSubmit, loading: true)
├─ Table (columns: [...], apiCall: "/api/data", loading: true)
├─ Container (loading: true)
```

---

### disabled
**圖標：** 🚫  
**用途：** 禁用狀態  
**適用組件：** Button, Input, Select, Checkbox, Switch  
**標記格式：** `disabled: false` / `disabled: if(condition)`  

**使用場景：**
- 條件禁用
- 權限控制
- 表單驗證未通過

**範例：**
```
├─ Button: "提交" (primary, onClick: handleSubmit, disabled: false)
├─ Input Field (placeholder: "Email", disabled: if(!isEditing))
├─ Select Dropdown (options: [...], disabled: if(!hasPermission))
```

---

### animation
**圖標：** ✨  
**用途：** 動畫效果  
**適用組件：** 任何組件  
**標記格式：** `animation: fadeIn` / `animation: slideUp`  

**動畫類型：**
- `fadeIn` - 淡入
- `fadeOut` - 淡出
- `slideUp` - 向上滑入
- `slideDown` - 向下滑入
- `slideLeft` - 向左滑入
- `slideRight` - 向右滑入
- `zoom` - 縮放
- `bounce` - 彈跳
- `shake` - 搖晃
- `pulse` - 脈衝

**範例：**
```
├─ Card (title: "產品", animation: fadeIn)
├─ Modal Dialog (title: "提示", animation: slideDown)
├─ Button: "點我" (animation: pulse)
```

---

### tooltip
**圖標：** 💬  
**用途：** 提示訊息  
**適用組件：** Button, Icon, Input, 任何組件  
**標記格式：** `tooltip: "提示文字"`  

**使用場景：**
- 按鈕說明
- 欄位提示
- 圖標解釋

**範例：**
```
├─ Button: "儲存" (primary, onClick: handleSave, tooltip: "Ctrl+S")
├─ Icon (name: "help", tooltip: "點擊查看幫助")
├─ Input Field (placeholder: "Email", tooltip: "請輸入有效的 Email 地址")
```

---

### conditional
**圖標：** 🔀  
**用途：** 條件顯示  
**適用組件：** 任何組件  
**標記格式：** `conditional: if(condition)`  

**使用場景：**
- 權限控制顯示
- 根據狀態顯示/隱藏
- 響應式顯示

**範例：**
```
├─ Button: "刪除" (danger, onClick: handleDelete, conditional: if(isAdmin))
├─ Container (conditional: if(isLoggedIn))
├─ Alert: "錯誤" (type: error, conditional: if(hasError))
```

---

### permission
**圖標：** 🔐  
**用途：** 權限控制  
**適用組件：** Button, Menu, Container, Component  
**標記格式：** `permission: admin` / `permission: [admin, editor]`  

**權限類型：**
- `admin` - 管理員
- `editor` - 編輯者
- `viewer` - 檢視者
- `user` - 一般用戶
- `guest` - 訪客
- 自訂角色

**使用場景：**
- 按鈕權限
- 選單項目權限
- 頁面區塊權限

**範例：**
```
├─ Button: "刪除" (danger, onClick: handleDelete, permission: admin)
├─ Menu (vertical, permission: [admin, editor])
├─ Container (permission: admin)
```

---

### tracking
**圖標：** 📊  
**用途：** 使用追蹤/分析  
**適用組件：** Button, Link, Form  
**標記格式：** `tracking: analytics` / `tracking: "event-name"`  

**使用場景：**
- 按鈕點擊追蹤
- 表單提交追蹤
- 用戶行為分析

**範例：**
```
├─ Button: "立即購買" (primary, onClick: handleBuy, tracking: "purchase-button")
├─ Link (href: "/product", tracking: "product-link")
├─ Form (onSubmit: handleSubmit, tracking: "signup-form")
```

---

### confirm
**圖標：** ❓  
**用途：** 確認對話框  
**適用組件：** Button, Link, Delete 操作  
**標記格式：** `confirm: "確定要執行嗎?"`  

**使用場景：**
- 刪除確認
- 重要操作確認
- 不可逆操作

**範例：**
```
├─ Button: "刪除" (danger, onClick: handleDelete, confirm: "確定刪除此項目?")
├─ Button: "清空" (secondary, onClick: handleClear, confirm: "這將清空所有資料，確定繼續?")
```

---

## 💾 狀態管理

### useState
**圖標：** 📦  
**用途：** 組件狀態管理  
**適用組件：** 任何需要狀態的組件  
**標記格式：** `useState: [value, setValue]`  

**使用場景：**
- 輸入框值
- 開關狀態
- 當前選擇
- 計數器

**範例：**
```
├─ Input Field (placeholder: "姓名", onChange: handleChange, useState: [name, setName])
├─ Toggle Switch: "通知" (onChange: handleToggle, useState: [enabled, setEnabled])
├─ Tabs (tabs: [...], onChange: handleTab, useState: [activeTab, setActiveTab])
├─ Counter (useState: [count, setCount])
```

---

### computed
**圖標：** 🧮  
**用途：** 計算屬性  
**適用組件：** Display, Label, Summary  
**標記格式：** `computed: calculateFunction`  

**使用場景：**
- 總計計算
- 衍生資料
- 格式化顯示

**範例：**
```
├─ Label: "總價" (computed: calculateTotal)
├─ Text: "剩餘天數" (computed: calculateDaysLeft)
├─ Badge: "進度" (computed: calculateProgress)
```

---

### watch
**圖標：** 👀  
**用途：** 監聽變化  
**適用組件：** 需要響應其他狀態變化的組件  
**標記格式：** `watch: onValueChange`  

**使用場景：**
- 監聽表單變化
- 自動儲存
- 關聯更新

**範例：**
```
├─ Input Field (placeholder: "數量", onChange: handleQuantity, watch: updatePrice)
├─ Select Dropdown (options: [...], onChange: handleCategory, watch: loadSubcategories)
├─ Form (watch: autoSave)
```

---

### store
**圖標：** 🏪  
**用途：** 全局狀態管理  
**適用組件：** 需要全局狀態的組件  
**標記格式：** `store: globalStore` / `store: userStore`  

**使用場景：**
- 用戶資訊
- 購物車
- 主題設定
- 語言切換

**範例：**
```
├─ Header (store: userStore)
├─ Cart Icon (store: cartStore)
├─ Theme Toggle (store: themeStore)
```

---

### localStorage
**圖標：** 💿  
**用途：** 本地持久化儲存  
**適用組件：** 需要持久化的組件  
**標記格式：** `localStorage: "keyName"`  

**使用場景：**
- 記住用戶設定
- 草稿儲存
- 記住登入狀態

**範例：**
```
├─ Toggle Switch: "深色模式" (onChange: handleTheme, localStorage: "theme")
├─ Textarea (placeholder: "草稿", onChange: handleDraft, localStorage: "draft")
├─ Select Dropdown (options: [...], localStorage: "language")
```

---

### sessionStorage
**圖標：** 🔖  
**用途：** 會話儲存  
**適用組件：** 需要會話級儲存的組件  
**標記格式：** `sessionStorage: "keyName"`  

**使用場景：**
- 表單資料暫存
- 頁面狀態
- 臨時資料

**範例：**
```
├─ Form (onSubmit: handleSubmit, sessionStorage: "formData")
├─ Tabs (tabs: [...], onChange: handleTab, sessionStorage: "activeTab")
```

---

## 📝 使用範例

### 範例 1：完整登入表單

```
├─ Container (max-width: 400px, animation: fadeIn)
  ├─ Form (layout: vertical, onSubmit: handleLogin, validation: required, tracking: "login-form")
    ├─ Input Field (placeholder: "Email", type: email, onChange: handleEmailChange, onBlur: validateEmail, validation: email, debounce: 300ms, tooltip: "請輸入有效的 Email", useState: [email, setEmail])
    ├─ Input Field (placeholder: "密碼", type: password, onChange: handlePasswordChange, validation: min:8, tooltip: "至少 8 個字符", useState: [password, setPassword])
    ├─ Checkbox: "記住我" (onChange: handleRemember, localStorage: "rememberMe", useState: [remember, setRemember])
    ├─ Button: "登入" (primary, onClick: handleSubmit, apiCall: "/api/login", loading: true, disabled: if(!isValid), tooltip: "點擊登入")
    ├─ Link: "忘記密碼?" (href: "/reset", tracking: "forgot-password")
```

---

### 範例 2：資料表格頁面

```
├─ Container (max-width: 1200px)
  ├─ Toolbar (操作區, onSubmit: handleSearch)
    ├─ Input Field (placeholder: "搜尋用戶", type: search, onChange: handleSearchChange, onKeyPress: handleEnter, debounce: 300ms)
    ├─ Button: "新增用戶" (primary, onClick: handleAdd, permission: admin, tracking: "add-user")
    ├─ Button: "匯出" (secondary, onClick: handleExport, tracking: "export-users")
  ├─ Table (columns: [姓名, Email, 角色, 狀態, 操作], sortable: true, pagination: true, apiCall: "/api/users", loading: true, onRowClick: handleRowClick, store: usersStore, tracking: "users-table")
  ├─ Pagination (total: 100, perPage: 20, onChange: handlePageChange, apiCall: "/api/users?page={page}", useState: [page, setPage])
```

---

### 範例 3：產品卡片

```
├─ Grid Layout (columns: 3, gap: 24px, responsive: true)
  ├─ Card (title: "產品 A", hoverable: true, onClick: handleCardClick, onHover: showDetails, animation: fadeIn, tracking: "product-card")
    ├─ Image (src: "product-a.jpg", lazy: true, onLoad: handleImageLoad, onError: handleImageError)
    ├─ Badge: "熱門" (color: danger)
    ├─ Button: "加入購物車" (primary, onClick: handleAddToCart, apiCall: "/api/cart/add", loading: true, tooltip: "加入購物車", tracking: "add-to-cart")
  ├─ Card (title: "產品 B", hoverable: true, animation: fadeIn)
  ├─ Card (title: "產品 C", hoverable: true, animation: fadeIn)
```

---

### 範例 4：設定頁面

```
├─ Container (max-width: 800px)
  ├─ Tabs (tabs: [基本設定, 通知, 隱私, 帳號], type: card, onChange: handleTabChange, useState: [activeTab, setActiveTab], sessionStorage: "settingsTab")
  
  <!-- 基本設定 -->
  ├─ Content (conditional: if(activeTab === 0))
    ├─ Form (onChange: handleSettingsChange, watch: autoSave)
      ├─ Input Field (placeholder: "用戶名稱", onChange: handleNameChange, validation: required, debounce: 500ms, useState: [name, setName])
      ├─ Select Dropdown (options: [繁體中文, 简体中文, English], onChange: handleLanguageChange, localStorage: "language", useState: [lang, setLang])
      ├─ Toggle Switch: "深色模式" (onChange: handleTheme, localStorage: "theme", useState: [darkMode, setDarkMode])
      ├─ Button: "儲存" (primary, onClick: handleSave, apiCall: "/api/settings", loading: true, tooltip: "Ctrl+S")
  
  <!-- 通知設定 -->
  ├─ Content (conditional: if(activeTab === 1))
    ├─ Toggle Switch: "Email 通知" (onChange: handleEmailNotif, localStorage: "emailNotif")
    ├─ Toggle Switch: "推播通知" (onChange: handlePushNotif, localStorage: "pushNotif")
    ├─ Toggle Switch: "簡訊通知" (onChange: handleSmsNotif, localStorage: "smsNotif")
```

---

### 範例 5：互動式儀表板

```
├─ Container (max-width: 1400px, onLoad: initializeDashboard, store: dashboardStore)
  ├─ Header (固定在頂部, onClick: handleHeaderClick, onScroll: handleScroll)
  
  ├─ Grid Layout (columns: 4, gap: 20px, responsive: true)
    ├─ Card (title: "總用戶", animation: fadeIn, onClick: handleUserCard)
      ├─ Label: "1,234" (computed: calculateTotalUsers, animation: pulse)
    ├─ Card (title: "今日訪客", animation: fadeIn)
    ├─ Card (title: "銷售額", animation: fadeIn)
    ├─ Card (title: "訂單數", animation: fadeIn)
  
  ├─ Flex Container (justify: space-between, align: center)
    ├─ Tabs (tabs: [日, 週, 月, 年], onChange: handlePeriodChange, useState: [period, setPeriod])
    ├─ Button: "匯出報表" (secondary, onClick: handleExport, apiCall: "/api/report", loading: true, permission: admin)
  
  ├─ Card (title: "銷售趨勢", animation: slideUp)
    ├─ Chart (type: line, apiCall: "/api/chart/sales", loading: true, watch: onPeriodChange)
  
  ├─ Grid Layout (columns: 2, gap: 20px)
    ├─ Card (title: "最新訂單")
      ├─ Table (columns: [訂單號, 客戶, 金額, 狀態], apiCall: "/api/orders/recent", loading: true, onRowClick: handleOrderClick)
    ├─ Card (title: "熱門產品")
      ├─ List (items: [...], apiCall: "/api/products/top", loading: true, onItemClick: handleProductClick)
```

---

### 範例 6：進階搜尋過濾

```
├─ Container (max-width: 1200px)
  ├─ Drawer (position: left, width: 300px, onOpen: handleFilterOpen, onClose: handleFilterClose)
    ├─ Form (onChange: handleFilterChange, watch: applyFilters)
      ├─ Select Dropdown (options: [所有類別, 電子產品, 服飾], onChange: handleCategoryChange, localStorage: "filterCategory")
      ├─ Slider (min: 0, max: 10000, onChange: handlePriceChange, throttle: 200ms, tooltip: "價格範圍")
      ├─ Checkbox Group: [有貨, 特價, 新品] (onChange: handleStatusChange)
      ├─ Button: "套用篩選" (primary, onClick: applyFilters, tracking: "apply-filters")
      ├─ Button: "重設" (secondary, onClick: resetFilters)
  
  ├─ Content (主要內容)
    ├─ Flex Container (justify: space-between, align: center)
      ├─ Label: "找到 {count} 個結果" (computed: calculateResultCount)
      ├─ Select Dropdown (options: [最新, 價格低到高, 價格高到低], onChange: handleSortChange)
    ├─ Grid Layout (columns: 3, gap: 24px, responsive: true, onScroll: loadMore, apiCall: "/api/products", loading: true)
```

---

## ✨ 最佳實踐

### 1. 基礎互動 → 進階功能
先添加基礎互動（如 onClick、onChange），再添加進階功能（如 validation、debounce）。

**好的順序：**
```
1. 選擇組件
2. 添加基礎互動（onClick/onChange）
3. 添加進階功能（validation/debounce）
4. 添加狀態管理（useState/localStorage）
```

---

### 2. 組合使用
多個功能可以組合使用，創造更好的用戶體驗。

**範例：**
```
├─ Input Field (
    placeholder: "Email",
    type: email,
    onChange: handleChange,        ← 基礎互動
    onBlur: validateEmail,          ← 基礎互動
    validation: email,              ← 進階功能
    debounce: 300ms,               ← 進階功能
    tooltip: "請輸入有效 Email",    ← 進階功能
    useState: [email, setEmail]     ← 狀態管理
)
```

---

### 3. 語義化命名
函數名稱要語義化，清楚表達功能。

**好的命名：**
- `handleLogin` ✅
- `handleEmailChange` ✅
- `validateEmail` ✅
- `handleCardClick` ✅

**不好的命名：**
- `handle` ❌
- `click1` ❌
- `func` ❌

---

### 4. 適當的防抖/節流
- 搜尋框：debounce 300ms
- 自動儲存：debounce 1000ms
- 滾動事件：throttle 200ms
- 滑桿拖動：throttle 100ms

---

### 5. 表單驗證
所有輸入欄位都應該有適當的驗證。

**範例：**
```
├─ Form (onSubmit: handleSubmit, validation: required)
  ├─ Input Field (type: email, validation: email)
  ├─ Input Field (type: password, validation: min:8)
  ├─ Checkbox: "同意" (validation: required)
```

---

### 6. 載入狀態
所有非同步操作都應該有載入狀態。

**範例：**
```
├─ Button: "提交" (onClick: handleSubmit, apiCall: "/api/save", loading: true)
├─ Table (apiCall: "/api/users", loading: true)
```

---

### 7. 權限控制
敏感操作要加上權限控制。

**範例：**
```
├─ Button: "刪除" (danger, onClick: handleDelete, permission: admin, confirm: "確定刪除?")
```

---

### 8. 追蹤分析
重要互動要加上追蹤。

**範例：**
```
├─ Button: "立即購買" (primary, onClick: handleBuy, tracking: "purchase-button")
├─ Form (onSubmit: handleSignup, tracking: "signup-form")
```

---

## 🎓 學習路徑

### 初學者
1. 學習基礎組件（Button, Input, Form）
2. 掌握基礎互動（onClick, onChange, onSubmit）
3. 練習簡單的表單

### 進階者
1. 學習進階功能（validation, debounce, apiCall）
2. 掌握狀態管理（useState, localStorage）
3. 練習複雜的頁面佈局

### 專家
1. 組合使用多種功能
2. 創建可複用的組件模式
3. 設計完整的應用架構

---

## 📚 延伸閱讀

- [互動功能使用指南](INTERACTION-GUIDE.md)
- [實現對照指南](IMPLEMENTATION-GUIDE.md)
- [更新總結](UPDATE-SUMMARY.md)

---

**版本：** 2.0  
**最後更新：** 2025-10-31

**祝你設計愉快！** 🎉
