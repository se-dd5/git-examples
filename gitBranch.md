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

# git checkout -b和 branch有甚麼關西
簡單來說，git checkout -b <新分支> 就是把「建立分支」和「切換過去」這兩個動作，合體成一個指令。
它們之間的關係可以用一個公式來表達：

git checkout -b <分支名稱>
＝ git branch <分支名稱>（建立） ＋ git checkout <分支名稱>（切換）

------------------------------
## 🧱 拆解對比：兩種做法的差異
如果您分開操作，需要輸入兩行指令：

   1. git branch dev ── 建立一個叫 dev 的新分支（此時你人還停在原本的分支）。
   2. git checkout dev ── 把工作崗位切換到 dev 分支。

如果您使用快捷指令，只需要一行：

* git checkout -b dev ── 系統直接幫你建好 dev 分支，並瞬間把切換過去。

(註：這個指令中的 -b 其實就是 branch 的意思，用來告訴 Git：「我要建立一個新分支並切過去」。)
------------------------------
## 💡 現代 Git 的新選擇 (git switch)
因為舊的 checkout 指令同時擁有「切換分支」和「還原檔案」的功能，容易讓人混淆。Git 在近年推出了更直覺的新指令：

* 兩步驟分開：git branch dev ➔ git switch dev
* 合體快捷鍵：git switch -c dev （這裡的 -c 是 create 的意思，功能完全等同於 git checkout -b）

您目前是正準備要建立新分支來寫程式，還是不小心在舊分支上改了東西、正要把檔案帶過去新分支呢？

