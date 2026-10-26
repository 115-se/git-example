`git branch` 是 Git 中用來管理分支的核心指令。你可以用它來**查看**、**建立**、**重新命名**或**刪除**分支。

---

### 1. 查看分支（Listing）

* **查看本地所有分支：**
```bash
git branch

```


*(目前所在的分支前面會標註 `*` 號並以綠色高亮)*
* **查看本地與遠端（Remote）所有分支：**
```bash
git branch -a

```


* **查看各分支最後一次 Commit 資訊：**
```bash
git branch -v

```



---

### 2. 建立分支（Creating）

* **單純建立新分支（停留在當前分支）：**
```bash
git branch <branch-name>

```


*例如：`git branch feature/login*`
* **常見捷徑：建立並直接切換過去**
```bash
# 現代 Git 推薦指令
git switch -c <branch-name>

# 傳統 Git 指令
git checkout -b <branch-name>

```



---

### 3. 刪除分支（Deleting）

* **安全刪除已合併的分支（推薦）：**
```bash
git branch -d <branch-name>

```


*如果該分支的改動尚未合併到當前分支，Git 會阻止刪除以防遺失代碼。*
* **強制刪除分支（即便未合併）：**
```bash
git branch -D <branch-name>

```


* **刪除遠端分支：**
```bash
git push origin --delete <branch-name>

```



---

### 4. 重新命名分支（Renaming）

* **重新命名「當前所在」的分支：**
```bash
git branch -m <new-branch-name>

```


* **重新命名「其他指定」的分支：**
```bash
git branch -m <old-branch-name> <new-branch-name>

```



---

### 快速日常工作流範例

```bash
# 1. 建立並切換到新功能分支
git switch -c feat/cart-page

# 2. 進行開發、提交改動
git add .
git commit -m "feat: add cart summary"

# 3. 切換回 main 分支並合併
git switch main
git merge feat/cart-page

# 4. 刪除已經用完的本地分支
git branch -d feat/cart-page

```