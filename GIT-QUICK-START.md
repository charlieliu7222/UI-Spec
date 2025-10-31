# 🚀 Git 快速開始指南

本指南將協助你把 UI Spec Builder 上傳到 GitHub。

---

## 📋 準備工作

### 1. 確認已安裝 Git
```bash
git --version
```

如果未安裝，請到 [git-scm.com](https://git-scm.com/) 下載安裝。

### 2. 設定 Git 用戶資訊（首次使用）
```bash
git config --global user.name "你的名字"
git config --global user.email "your.email@example.com"
```

---

## 🎯 上傳到 GitHub

### 步驟 1：在 GitHub 建立新倉庫

1. 登入 [GitHub](https://github.com)
2. 點擊右上角的 **+** → **New repository**
3. 填寫資訊：
   - **Repository name:** `ui-spec-builder`（或你想要的名稱）
   - **Description:** `視覺化 UI 結構規劃工具`
   - **Public** 或 **Private**（依你的需求）
   - ❌ **不要勾選** Initialize this repository with a README
4. 點擊 **Create repository**

### 步驟 2：初始化本地倉庫

在專案資料夾中執行：

```bash
# 進入專案目錄
cd /path/to/ui-spec-builder

# 初始化 Git 倉庫
git init

# 添加所有文件
git add .

# 提交變更
git commit -m "Initial commit: UI Spec Builder v2.0"
```

### 步驟 3：連接遠端倉庫

```bash
# 添加遠端倉庫（替換成你的 GitHub 用戶名和倉庫名）
git remote add origin https://github.com/你的用戶名/ui-spec-builder.git

# 或使用 SSH（如果已設定 SSH Key）
git remote add origin git@github.com:你的用戶名/ui-spec-builder.git
```

### 步驟 4：推送到 GitHub

```bash
# 推送到主分支
git branch -M main
git push -u origin main
```

如果遇到認證問題，GitHub 現在要求使用 **Personal Access Token (PAT)** 而非密碼。

---

## 🔑 設定 GitHub Personal Access Token

### 1. 產生 Token

1. 進入 GitHub → **Settings** → **Developer settings** → **Personal access tokens** → **Tokens (classic)**
2. 點擊 **Generate new token** → **Generate new token (classic)**
3. 填寫資訊：
   - **Note:** `ui-spec-builder`
   - **Expiration:** 選擇有效期限
   - **Select scopes:** 勾選 `repo`（完整的倉庫存取權限）
4. 點擊 **Generate token**
5. **複製 Token**（只會顯示一次！）

### 2. 使用 Token 推送

```bash
# 當提示輸入密碼時，貼上你的 Personal Access Token
git push -u origin main

# 用戶名：你的 GitHub 用戶名
# 密碼：貼上剛才複製的 Token
```

### 3. 儲存憑證（避免每次輸入）

```bash
# Windows
git config --global credential.helper wincred

# macOS
git config --global credential.helper osxkeychain

# Linux
git config --global credential.helper cache
```

---

## 📝 常用 Git 命令

### 查看狀態
```bash
git status
```

### 添加新文件
```bash
# 添加特定文件
git add 文件名

# 添加所有變更
git add .
```

### 提交變更
```bash
git commit -m "提交訊息"
```

### 推送到遠端
```bash
git push
```

### 拉取最新變更
```bash
git pull
```

### 查看提交歷史
```bash
git log --oneline --graph --all
```

### 創建分支
```bash
git branch 分支名稱
git checkout 分支名稱

# 或一次完成
git checkout -b 分支名稱
```

### 切換分支
```bash
git checkout 分支名稱
```

### 合併分支
```bash
# 先切換到目標分支
git checkout main

# 合併其他分支
git merge 分支名稱
```

---

## 📂 文件結構確認

確保你的專案包含以下文件：

```
ui-spec-builder/
├── ui-spec-builder-advanced.html    ✅ 主程式
├── ui-spec-builder-ascii.html       ✅ 基礎版本
├── interactive-page.html            ✅ 展示頁面
├── README.md                        ✅ 說明文件
├── COMPLETE-GUIDE.md               ✅ 完整指南
├── IMPLEMENTATION-GUIDE.md         ✅ 實現指南
├── LICENSE                         ✅ 授權文件
└── .gitignore                      ✅ Git 忽略文件
```

---

## 🌐 設定 GitHub Pages（可選）

讓你的工具可以線上訪問！

### 1. 推送到 GitHub 後

1. 進入你的 GitHub 倉庫
2. 點擊 **Settings**
3. 左側選單點擊 **Pages**

### 2. 設定來源

- **Source:** Deploy from a branch
- **Branch:** main
- **Folder:** / (root)
- 點擊 **Save**

### 3. 等待部署

幾分鐘後，你的網站就會在以下網址上線：
```
https://你的用戶名.github.io/ui-spec-builder/ui-spec-builder-advanced.html
```

---

## 🔄 更新到 GitHub

當你修改文件後：

```bash
# 1. 查看變更
git status

# 2. 添加變更
git add .

# 3. 提交變更
git commit -m "Update: 更新說明"

# 4. 推送到 GitHub
git push
```

---

## 📊 提交訊息規範（建議）

使用語義化的提交訊息：

- `feat:` 新功能
- `fix:` 修復 Bug
- `docs:` 文檔更新
- `style:` 樣式調整
- `refactor:` 重構代碼
- `test:` 測試相關
- `chore:` 維護任務

**範例：**
```bash
git commit -m "feat: 添加進階互動功能面板"
git commit -m "fix: 修復組件插入位置錯誤"
git commit -m "docs: 更新 README 使用說明"
```

---

## ❓ 常見問題

### Q1: 忘記提交訊息怎麼辦？
```bash
# 修改最後一次提交訊息
git commit --amend -m "新的提交訊息"
```

### Q2: 想取消還未提交的變更？
```bash
# 取消所有未提交的變更
git checkout .

# 取消特定文件的變更
git checkout -- 文件名
```

### Q3: 想刪除最後一次提交？
```bash
# 保留變更，只刪除提交
git reset --soft HEAD~1

# 完全刪除變更和提交
git reset --hard HEAD~1
```

### Q4: 如何查看遠端倉庫？
```bash
git remote -v
```

### Q5: 如何更改遠端倉庫地址？
```bash
git remote set-url origin 新的倉庫地址
```

---

## 🎓 推薦資源

- **Git 官方文檔：** https://git-scm.com/doc
- **GitHub 教學：** https://docs.github.com/en/get-started
- **Git 視覺化練習：** https://learngitbranching.js.org/
- **Git Cheat Sheet：** https://education.github.com/git-cheat-sheet-education.pdf

---

## 🎉 完成！

恭喜！你的 UI Spec Builder 現在已經在 GitHub 上了！

接下來你可以：
- ⭐ 分享你的專案給其他人
- 📝 持續更新和改進
- 🤝 接受社群貢獻
- 🌐 設定 GitHub Pages 讓工具線上可用

祝你開發愉快！ 🚀
