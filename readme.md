# Git 指令

### Git 版本
    . git version

### 建立基本資訊 (全域)
    . git config --global user.name (username)
    . git config --global user.email (email)
    (資訊會在 c:/user/username/.gitconfig 檔案內)

### 建立基本資訊 (區域)
    . git config user.name (username)
    . git config user.email (email)
    (資訊會在 .git/config 檔案內)

### 初始化 Git
    . git init

### 將程式放入 暫存區 (加入控管)
    . git add (filename)
    . gti add . --> 將全部未放入暫存區檔案放入暫存區
    (將原始碼編譯成 sha-1格式的object)

### 檢查當前檔案狀態
    . git status
        - 觀察 Git 狀態
            . U : Untracked
            . A : Added
            - M : Modified (進入暫存區後的修改)
            - D : Deleted 
    
    - git ls-files (檢查全部檔案名稱)
        . git ls-files -s (檢查所有檔案所對應的sha-1編碼)

### 暫存區
    - 修改後的恢復
        . git checkout (filename)
    - 修改後確認
        . git add (filename)  --> 再次放入暫存區

### 將程式放入倉庫區
    . git commit -m "commition"

### 目前 commit 狀態
    . git log
        . git log --oneline (單行模式)
        . git log 2 (顯示最後兩筆資料)
        . git log --before='time' (檢視區間日期資料)
        . git shortlog (簡易模式顯示)
        . git log --stat (詳細修改資訊)
        . git log --graph (分支圖)

### 修改最後一次的commit
    . git commit --amend
        - Vim 指令
            . ese -> 切換 normal/insert 模式
            . :w -> 寫入 = 儲存
            . :q -> 離開程式
            :! -> 強制執行
            :q! ->回到上一個動作
            i -> insert
            a -> append
            o -> new line

### 恢復檔案
    . git restore 
        . git restore --staged (filename) --> 由暫存區轉回工作區 A -> U
        . git restore (filename) --> 手動刪除時，恢復檔案

### 刪除檔案
    . git rm (filename) --> 倉庫區 -> U
    (檔案需要再Unstaged才能控制 -> 恢復/確認 刪除)
    . git rm --cached (filename) --> 暫存區/倉庫區 -> U

## 分支 Branch
- 一個指向特定commit 的指針

### 觀察目前分支
    . git branch
    . git branch (name) -> 新增 name 分支

### 切換分支
    . git checkout (name) -> 切換成 name 分支

### 建立 & 切換分支 (一次完成)
    . git checkout -b (name) -> 建立name 分支並切換至 name 分支

### 分支名稱修改
    . git branch -m (old name) (new name)

### 刪除分支
    . git branch -D (name) -> 必須要先切換至其他分支

### 切換到任何commit
    - git checkout (commit-object)

### 合併檔案
    . git merge (branch-name)
        . Accept Current Change -> 保留原始檔案
        . Accept Incoming Change -> 使用新檔案
        . Accept Both Changes -> 兩個檔案都保留
        . Compare Changes -> 比對兩個檔案

### 顯示其他 commit-object
    . git reflog

### 真正意義的回到過去的commit
    . git reset -> 預設模式(mixed) 可反悔
    . git reset --hard (commit-object) -> hard模式 無法反悔
    . git reset --soft (commit-object) -> soft模式 檔案等待commit
