# Sudo-user-create

# 我們要的效果是 把專案從github拉最新的下來 以便可以測試到最新的修改。
# 所以在專案的 deploy key 新增公鑰


## 環境安裝

新增一個共通使用者：＄ adduser username kingman


切換身份到Kingman :  su -l kingman

一、安裝git

  安裝git: apt-get install git

  查看git版本：git version

  設定git用戶：
  git config --global user.name "woider"
  git config --global user.email "********@gmail.com"


二、開啟ＳＳＨ服務

  Ubuntu 安装 SSH：apt-get install ssh

  查看 SSH狀態：ps -e | grep sshd 

三、生成 SSH KEY
  ssh-keygen

  ssh-keygen -f ~/.ssh/deploy_key_repo1

             -f  文件名稱  
生成 SSH KEY：  ssh-keygen -t rsa -C  "*****@gmail.com"

             -t創建密鑰的類型       -C“備註“

 四、在git上新增SSH key
  找到SSH key 的public鑰匙🔑

  登入GitHub，打開並新增專案的deploy key

五、clone專案到本機

  git clone  專案的clone

  Clone到本機的專案會自動關聯雲端專案，可以通過  git remote -v  命令查看關聯狀態

ps.此過程是 讓電腦重新找鑰匙🔑

eval "$(ssh-agent -s)"

ssh-add -K ~/.ssh/deploy_key_repo1
ssh-add ~/.ssh/deploy_key_repo1

