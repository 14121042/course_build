**環境搭建**


**安裝64位Ubuntu系統（實體安裝、虛擬機安裝均可）**


注意：要求機器至少4Gb Ram，硬盤至少100Gb


**更新系統至最新版本，在終端下輸入**


sudo apt-get update


sudo apt-get upgrade


**安裝編譯必需軟件包**


sudo apt-get install bison build-essential curl flex git gnupg gperf libesd0-dev libncurses5-dev libsdl1.2-dev libwxgtk2.8-dev libxml2 libxml2-utils lzop openjdk-7-jdk openjdk-7-jre pngcrush schedtool squashfs-tools xsltproc zip zlib1g-dev g++-multilib gcc-multilib lib32ncurses5-dev lib32readline-gplv2-dev lib32z1-dev


**建立repo命令**


mkdir -p ~/bin


curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo


chmod a+x ~/bin/repo


echo "export PATH=~/bin:$PATH" >> ~/.bashrc


**同步源碼** 


新建一個儲存源碼的文件夾，這裏以~/android/cm為例


mkdir ~/android


mkdir ~/android/cm


cd ~/android/cm


**初始化源碼目錄**


repo init -u git://github.com/CyanogenMod/android.git -b cm-13.0


**同步機型的源碼(這裏用angler做例子)**


mkdir ~/android/cm/.repo/local_manifests


gedit ~/android/cm/.repo/local_manifests/roomservice.xml


詳情可以參考Root目錄的roomservice.xml


**開始同步代碼**


repo sync


**初始化編譯環境**


cd ~/android/cm


. build/envsetup.sh


lunch


**編譯ROM（看你電腦水平了，快則1小時，慢則30天）**


make otapackage -j4

(四核心就j4，八核心就j8)

**其他指令**


make clobber

(清除上次編譯的文件)
