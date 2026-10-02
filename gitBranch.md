# gitBranch 怎麼用
在 Git 中，git branch 指令主要用於「管理」和「查看」分支。
如果您是想要建立、切換或刪除分支，最常搭配使用的是 git branch 和 git checkout（或較新的 git switch）。
以下為您整理最常用的四大核心操作：
## 1. 查看分支 (List)

* git branch：列出本地端所有的分支（前面有 * 號且顯示綠色的代表你目前所在的分支）。
* git branch -a：列出「本地端」與「遠端 (Remote)」所有的分支。

## 2. 建立與切換分支 (Create & Switch)
微軟建議使用較直覺的 switch 指令來切換分支：

* 建立新分支：git branch <新分支名稱>（例如：git branch dev）
* 切換到該分支：git switch <分支名稱>（例如：git switch dev）
* 【最常用】建立並直接切換過去：

git switch -c <新分支名稱>

(註：如果您習慣舊指令，建立並切換是 git checkout -b <新分支名稱>)

## 3. 刪除分支 (Delete)
當分支任務完成（例如功能已合併）需要刪除時：

* 安全刪除（已合併）：git branch -d <分支名稱>
* 強制刪除（未合併也想丟棄）：git branch -D <分支名稱>

## 4. 改名字 (Rename)

* 修改目前所在的分支名稱：git branch -m <新名稱>

------------------------------
## 💡 實戰範例流程
假設您要在剛剛的 peter 資料夾下開發一個新功能：

   1. git switch -c feature-login （建立並切換到名為 feature-login 的新分支）
   2. 修改程式碼...
   3. git add . 加上 git commit -m "完成登入功能" （提交程式碼）
   4. git switch main （切換回主分支）
   5. git merge feature-login （將新功能合併進主分支）

請問您目前是想要單純查看現在有哪些分支，還是準備要為專案建立新的開發分支呢？如果您遇到了特定的 Git 錯誤訊息，也可以直接貼給我看！

