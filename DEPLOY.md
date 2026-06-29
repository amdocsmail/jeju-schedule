# GitHub Pages 部署指南

比照 [expiry-notify](https://github.com/amdocsmail/expiry-notify) 的做法：程式碼推到 GitHub，再從 GitHub Pages 發布靜態網站。

上線後網址（repo 名稱為 `jeju-schedule` 時）：

```
https://amdocsmail.github.io/jeju-schedule/
```

---

## 1. 在 GitHub 建立 repository

1. 登入 [GitHub](https://github.com)（帳號 `amdocsmail`）
2. 開啟快速建立頁：[建立 jeju-schedule](https://github.com/new?name=jeju-schedule&owner=amdocsmail)
3. 可設 **Private** 或 **Public**
4. **不要**勾選 Add README / .gitignore
5. 按 **Create repository**

## 2. 本機推送

```powershell
cd "C:\Users\erichsu\Projects\jeju-schedule"
git push -u origin main
```

> 推送時若跳出 GitHub 登入視窗，照著授權即可。

## 3. 啟用 GitHub Pages

1. Repo → **Settings** → **Pages**
2. **Build and deployment** → **Source** 選 **GitHub Actions**
3. 推送後 Actions 會自動部署（約 1～2 分鐘）
4. 網址：`https://amdocsmail.github.io/jeju-schedule/`

（也可改用 **Deploy from a branch** → `main` / `/ (root)`，效果相同。）

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
