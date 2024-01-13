# Git 指令

## Git 版本
    . git version

## 建立基本資訊 (全域)
    . git config --global user.name (username)
    . git config --global user.email (email)
    (資訊會在 c:/user/username/.gitconfig 檔案內)

## 建立基本資訊 (區域)
    . git config user.name (username)
    . git config user.email (email)
    (資訊會在 .git/config 檔案內)

## 初始化 Git
    . git init

## 將程式放入 暫存區 (加入控管)
    . git add (filename)
    . gti add . --> 將全部未放入暫存區檔案放入暫存區
    (將原始碼編譯成 sha-1格式的object)

## 檢查當前檔案狀態
    . git status
        - 觀察 Git 狀態
            . U : Untracked
            . A : Added
            - M : Modified (進入暫存區後的修改)
            - D : Deleted 
    
    - git ls-files (檢查全部檔案名稱)
        . git ls-files -s (檢查所有檔案所對應的sha-1編碼)

## 暫存區
    - 修改後的恢復
        . git checkout (filename)
    - 修改後確認
        . git add (filename)  --> 再次放入暫存區

## 將程式放入倉庫區
    . git commit -m "commition"

## 目前 commit 狀態
    . git log
        . git log --oneline (單行模式)
        . git log 2 (顯示最後兩筆資料)
        . git log --before='time' (檢視區間日期資料)
        . git shortlog (簡易模式顯示)
        . git log --stat (詳細修改資訊)
        . git log --graph (分支圖)

## 修改最後一次的commit
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

## 恢復檔案
    . git restore 
        . git restore --staged (filename) --> 由暫存區轉回工作區 A -> U
        . git restore (filename) --> 手動刪除時，恢復檔案

## 刪除檔案
    . git rm (filename) --> 倉庫區 -> U
    (檔案需要再Unstaged才能控制 -> 恢復/確認 刪除)
    . git rm --cached (filename) --> 暫存區/倉庫區 -> U





