# GitHub Pages 部署指南

比照 [expiry-notify](https://github.com/amdocsmail/expiry-notify) 的做法：程式碼推到 GitHub，再從 GitHub Pages 發布靜態網站。

上線後網址（repo 名稱為 `jeju-schedule` 時）：

```
https://amdocsmail.github.io/jeju-schedule/
```

---

## 1. 在 GitHub 建立 repository

1. 登入 [GitHub](https://github.com)（帳號 `amdocsmail`）
2. 點 **Create repository**
3. **Repository name**：`jeju-schedule`
4. 可設 **Private** 或 **Public**（Pages 兩者皆可，Public 較單純）
5. **不要**勾選 Add README / .gitignore（保持空 repo，避免衝突）
6. 建立後複製網址：`https://github.com/amdocsmail/jeju-schedule.git`

## 2. 本機推送（第一次）

在專案資料夾執行：

```powershell
cd "C:\Users\erichsu\Projects\jeju-schedule"

git init
git branch -M main
git add .
git commit -m "Add Jeju schedule site for GitHub Pages"
git remote add origin https://github.com/amdocsmail/jeju-schedule.git
git push -u origin main
```

> 推送時若跳出 GitHub 登入視窗，照著授權即可（與 expiry-notify 相同）。

## 3. 啟用 GitHub Pages

1. 開啟 repo → **Settings** → 左側 **Pages**
2. **Build and deployment** → **Source** 選 **Deploy from a branch**
3. **Branch**：`main`　**Folder**：`/ (root)`
4. 按 **Save**
5. 等 1～3 分鐘，頁面上會出現綠色網址：`https://amdocsmail.github.io/jeju-schedule/`

## 4. 之後更新網站

修改 `index.html` 或 PDF 後：

```powershell
cd "C:\Users\erichsu\Projects\jeju-schedule"
git add .
git commit -m "Update schedule"
git push
```

推送完成後，GitHub Pages 會自動重新發布（通常 1～2 分鐘內生效）。

---

## 檔案說明

| 檔案 | 用途 |
|------|------|
| `index.html` | 網站首頁（行事曆、行程、班機、接送） |
| `rongfu-jeju-20260806-0810.pdf` | 完整行程 PDF（「開啟完整行程 PDF」連結） |

`index.html` 必須在 repo 根目錄，Pages 才會正確顯示首頁。
