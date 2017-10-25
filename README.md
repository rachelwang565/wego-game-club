# 危閣精神病院

使用RPG Maker MV打開Game.rpgproject即可

## Git教學
請先從[https://git-scm.com/](https://git-scm.com/)下載最新版本的Git

### 安裝
安裝只要一直按Next就好了，其他設定都不用動，但是有一個地方例外，要選擇`Checkout as-is, commit as-is`

![Checkout as-is, commit as-is](/README/install/7.jpg)

最後點選`Launch Git Bash`

![Launch Git Bash](/README/install/10.jpg)

應該會出現一個黑色視窗畫面

![Black window](/README/install/11.jpg)

沒有的話。請到搜尋Windows中搜尋`Git`，點選`Git Bash`

![Search Git](/README/install/12.jpg)

### 設定使用者
第一次安裝需要設定使用者，好方便讓其他人知道是誰修改了紀錄，在Git Bash(黑色視窗)輸入下面兩個指令，名字跟電子郵件信箱請打`英文或數字`
+ `git config --global user.name "你的名字"`
+ `git config --global user.email "電子郵件信箱"`

![Setup user](/README/setup/1.jpg)

設定完後我們可以輸入`git config -l`看有沒有出現剛剛的設定

![Check user](/README/setup/2.jpg)

### Clone危閣精神病院
> 在這之前，你要先有個[Github](https://github.com/)帳號

先切換到你要存放危閣精神病院的目錄，假設我們要存到本機磁碟(E:)那就要輸入`cd e:`，如果要存放到D槽的Homework資料夾，那就要輸入`cd d:/Homework`，最後我們輸入`git clone https://github.com/rachelwang565/wego-game-club.git`，就會開始下載最新版本的危閣精神病院了！

![Check user](/README/clone/1.jpg)

### 建立自己的Branch

Branch(分支，用高中生比較容易懂的話語就是平行世界)，為了不讓我們做的修改影響到其他人或者反之，我們可以建立一個branch，在新建立的branch中做任意修改，等真的確定改完沒有問題要給夥伴看時，再將兩個branch合併

大家可以找到`master`字樣，通常master代表主分支，下面是建立分支以及切換分支的指令，圖為建立一個lime分支範例

+ `git branch 分支名稱` 建立分支
+ `git checkout 分支名稱` 切換分支
+ `git branch` 顯示目前所有分支

![New Branch](/README/branch/1.jpg)

### 修改些東西然後存檔
當我們在自己的分支做些修改後，我們可以給它設定個紀錄點，紀錄我們這次修改了哪些東西，我們可以用`git status`來看那些東西被修改了

![git status](/README/add_commit/1.jpg)

我們可以用`add`指令新增本次要被儲存的檔案，我通常都用第三個

+ `git add 檔案名稱` 單一新增
+ `git add -A` 新增全部
+ `git add .` 新增所有修改過的檔案，除了被刪除的

然後用`commit`指令給這次的修改設一個記錄點，下面的圖為參考範例
> 正式上我們會說commit(提交)，不會說儲存，存檔，記錄點

+ `git commit -m "簡單的描述修改訊息"` 簡單的描述修改過什麼就好，一般人請使用這個指令
+ `git commit` 會開啟vi編輯器，讓你詳細修改要修改的內容，如果不會vi指令，請一定要照前面打

![Add and Commit](/README/add_commit/2.jpg)

### 合併世界，讓其他人知道

當我們在自己的分支修改完沒問題後，就要將自己做的更動給其他夥伴們使用了，我們要先切回`master`分支，因為這是所有人都共享的世界，只有master分支的內容我們會讓其他人知道
> 我們會盡量讓master分支保持在可以執行，直接發布的狀態

剛回到主世界(master分支)我們要先更新一下自己的訊息，看一下有沒有漏掉什麼有關這個世界的重要訊息，使用`pull`指令可以讓我們跟上最新的進度，如果沒有衝突，就會顯示`Already up-to-date.`，代表沒有其他人在主世界做任何修正，如果有其他人正在更改同一份檔案呢？那就會產生衝突，需要手動處理，實際狀況要等發生才能比較好跟大家說明怎麼處理，現在我們就當作很幸運的`Already up-to-date.`吧

我們已經跟主世界(master)同步好了，接下來就要將本地平行世界(分支)合併到主世界來，使用`merge`指令將分支合併，一樣如果有衝突會需要手動解決，沒有其他狀況我們就能將所有修改的內容同步到網路上的主世界給其他人使用，使用`push`即可
>這邊注意，第一次使用push會需要身分驗證，跳出如下的圖示，因為我們把主世界存放在github網站上，所以會需要github的帳號密碼，輸入一次即可，後面會自動記錄起來

![login](/README/merge_pull_push/1.jpg)

下面整理一下指令，圖為參考
+ `git checkout master` 切回主分支
+ `git pull` 跟網路上的主分支同步，檢查有無最新檔案
+ `git merge 分支名稱` 將本地分支同步，注意看自己在哪個分支，本例我們都在master分支下把其他分支合併進來
+ `git push` 將本地檔案更新到網路上

![merge, pull and push](/README/merge_pull_push/2.jpg)

### 其他

上述指令已經是最精簡了，平時只要依照需求使用即可，如果想知道更詳細的指令可以參考官方文件[https://git-scm.com/docs](https://git-scm.com/docs)
