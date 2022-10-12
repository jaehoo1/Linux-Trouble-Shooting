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

### VS Code 한글 입력
snap store에서 받은 버전의 VS Code는 한글 입력이 잘 안된다고 한다(본인도 잘 안됬음).  
[VS Code 공홈](https://code.visualstudio.com/download)에 가서 우분투 버전(`.deb`)을 다운로드 하고 설치
```bash
sudo snap remove code
sudo dpkg -i [deb 파일명]
sudo apt -f install
```