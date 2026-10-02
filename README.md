# git-example

# 專案位置

## 母專案

https://github.com/se-test-example1/git-example

## 分支

https://github.com/se-test-example1/git-example/tree/testbranch

## Fork 後的子專案

https://github.com/shain120/git-example

## Pull Request

https://github.com/se-test-example1/git-example/pull/1

---
1. 建立分支（Branch）
2. 合併分支（Merge）
3. Fork 專案
4. 建立 Pull Request

# Git Branch 分支操作

母專案：

https://github.com/se-test-example1/git-example

建立的分支：

https://github.com/se-test-example1/git-example/tree/testbranch

## 1. Clone 母專案

先將 GitHub 上的 Repository 下載到本機：

```bash
git clone https://github.com/se-test-example1/git-example.git
```

進入專案：

```bash
cd git-example
```

## 2. 查看目前分支

```bash
git branch
```

目前主要分支為：

```text
main
```

## 3. 建立新的分支

建立一個名稱為 `testbranch` 的分支：

```bash
git checkout -b testbranch
```

也可以使用：

```bash
git switch -c testbranch
```

再次查看：

```bash
git branch
```

可以看到：

```text
  main
* testbranch
```

代表目前已經切換到 `testbranch`。

## 4. 修改內容並 Commit

在 `testbranch` 中新增或修改檔案後：

```bash
git add .
```

建立 Commit：

```bash
git commit -m "add branch"
```

## 5. 將分支 Push 到 GitHub

```bash
git push -u origin testbranch
```

完成後 GitHub 上就會出現 `testbranch` 分支。

分支網址：

https://github.com/se-test-example1/git-example/tree/testbranch

# Git Merge 合併分支操作

母專案：

https://github.com/se-test-example1/git-example

分支：

https://github.com/se-test-example1/git-example/tree/testbranch

本次操作示範將：

```text
testbranch
```

合併至：

```text
main
```

## 1. 切換回 main

先確認目前所在目錄：

```bash
cd git-example
```

切換到 `main`：

```bash
git checkout main
```

或：

```bash
git switch main
```

## 2. 更新 main

先取得 GitHub 上最新的內容：

```bash
git pull origin main
```

## 3. 合併 testbranch

執行：

```bash
git merge testbranch
```

這個指令會將 `testbranch` 的修改合併到目前所在的 `main`。

流程為：

```text
main
  |
  +------ testbranch
  |          |
  |          | 修改內容
  |          | commit
  |          |
  <----------+
      merge
  |
 main
```

## 4. Push 到 GitHub

合併完成後：

```bash
git push origin main
```

此時 `testbranch` 的修改就會進入母專案的 `main` 分支。

母專案：

https://github.com/se-test-example1/git-example

# GitHub Fork 操作

母專案：

https://github.com/se-test-example1/git-example

Fork 後的子專案：

https://github.com/shain120/git-example

## 1. 進入母專案

先開啟：

https://github.com/se-test-example1/git-example

## 2. 點選 Fork

在 GitHub Repository 頁面的右上角找到：

```text
Fork
```

點擊後，選擇自己的 GitHub 帳號：

```text
shain120
```

接著按：

```text
Create fork
```

## 3. 建立子專案

GitHub 會複製母專案並建立：

```text
shain120/git-example
```

網址：

https://github.com/shain120/git-example

目前專案關係為：

```text
母專案
se-test-example1/git-example
            |
            | Fork
            v
子專案
shain120/git-example
```

## 4. Clone 自己 Fork 的專案

接下來可以 Clone 自己的 Repository：

```bash
git clone https://github.com/shain120/git-example.git
```

進入：

```bash
cd git-example
```

接著便可以在自己的 Fork Repository 中修改檔案，而不需要直接修改母專案。

## Fork 的用途

Fork 可以讓使用者複製別人的 Repository 到自己的 GitHub 帳號。

修改自己的 Fork 後，可以再透過 Pull Request 將修改提交回原本的母專案。

# GitHub Pull Request 操作

母專案：

https://github.com/se-test-example1/git-example

子專案：

https://github.com/shain120/git-example

本次 Pull Request：

https://github.com/se-test-example1/git-example/pull/1

## 1. 在 Fork 專案修改內容

首先 Clone 自己 Fork 的 Repository：

```bash
git clone https://github.com/shain120/git-example.git
```

進入專案：

```bash
cd git-example
```

修改或新增檔案後：

```bash
git add .
```

建立 Commit：

```bash
git commit -m "fork to shain120"
```

將內容 Push 到自己的 Repository：

```bash
git push origin main
```

## 2. 建立 Pull Request

進入自己的 Fork：

https://github.com/shain120/git-example

在 GitHub 上點選：

```text
Contribute
```

接著選擇：

```text
Open pull request
```

或 GitHub 可能直接顯示：

```text
Compare & pull request
```

## 3. 設定 Pull Request

來源 Repository：

```text
shain120/git-example
```

來源分支：

```text
main
```

目標 Repository：

```text
se-test-example1/git-example
```

目標分支：

```text
main
```

因此資料流為：

```text
shain120/git-example:main
             |
             | Pull Request
             v
se-test-example1/git-example:main
```

## 4. Create Pull Request

輸入標題與內容後：

```text
Create pull request
```

本次建立的 Pull Request 標題為：

```text
fork to shain120
```

Pull Request：

https://github.com/se-test-example1/git-example/pull/1

## 5. Merge Pull Request

母專案管理者確認修改內容沒有問題後，點選：

```text
Merge pull request
```

再按：

```text
Confirm merge
```

完成後，Fork 專案中的修改就會被加入母專案。

本次 Pull Request #1 已成功 Merge。

完整流程：

```text
se-test-example1/git-example
          |
          | Fork
          v
shain120/git-example
          |
          | 修改
          | commit
          | push
          v
    Pull Request #1
          |
          | Merge
          v
se-test-example1/git-example
       main
```
