### wsl/termux 등 최소 설치 직후
apt update && apt -y upgrade  
apt -y install vim

### 한글 설치
apt-get install language-pack-ko  
apt-get install language-pack-ko-base  
vim /etc/environment 아래 내용 추가  
```sh
LANG="ko_KR.UTF-8"
LANG="ko_KR.EUC-KR"
LANGUAGE="ko_KR:ko:en_GB:en"
```
vim /etc/default/locale 위와 같은 내용 추가  
vim /etc/profile 아래 내용 추가  
```sh
LANG="ko_KR.UTF-8"
```
reboot

### 데스크톱 / gui
apt-get -y install ubuntu-desktop  
dpkg 에러 날 경우  
+ rm -rf /var/lib/dpkg/info/*  
+ dpkg --configure -a

apt-get install indicator-appmenu-tools  
이후 xrdp나 vnc로 gui 접근
