### wsl/termux 등 최소 설치 직후
apt update && apt -y upgrade  
apt -y install vim

<br/>

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

<br/>

### 데스크톱 / gui
apt-get -y install ubuntu-desktop  
dpkg 에러 날 경우  
+ rm -rf /var/lib/dpkg/info/*  
+ dpkg --configure -a

apt-get install indicator-appmenu-tools  
이후 xrdp나 vnc로 gui 접근

<br/>

### VS Code 한글 입력
snap store에서 받은 버전의 VS Code는 한글 입력이 잘 안된다고 한다(본인도 잘 안됬음).  
[VS Code 공홈](https://code.visualstudio.com/download)에 가서 우분투 버전(`.deb`)을 다운로드 하고 설치
```bash
sudo snap remove code
sudo dpkg -i [deb 파일명]
sudo apt -f install
```

<br/>

### 카카오톡 설치
32비트 아키텍처를 사용 할 수 있도록 설정
```bash
sudo dpkg --add-architecture i386
sudo apt -y update
```
wine 설치를 위해 key 파일 추가
```bash
wget -nc https://dl.winehq.org/wine-builds/winehq.key
sudo apt-key add winehq.key
```
wine 설치
```bash
sudo apt -y install wine
```
wine 설정
```bash
WINEARCH=win32 winecfg
```
Windows 버전 : Windows 10

[카카오톡 공홈](https://www.kakaocorp.com/page/service/service/KakaoTalk)에 가서 Windows버전을 다운받는다.

카카오톡 설치
```bash
LANG="ko_KR.UTF-8" wine KakaoTalk_Setup.exe
```
카카오톡 언어 설정
```bash
vi ~/바탕화면/카카오톡.desktop
```
3번줄 `wine-stable` 명령어 앞에 `LANG="ko_KR.UTF-8"` 추가
```bash
[Desktop Entry]
Name=카카오톡
Exec=env WINEPREFIX="/home/~~~/.wine" LANG="ko_KR.UTF-8" wine-stable C:\\\\windows\\\\command\\\\start.exe /Unix /home/~~~/.wine/dosdevices/c:/users/Public/Desktop/카카오톡.lnk
```
위와 마찬가지로 여기도 추가해준다
```bash
vi ~/.local/share/applications/wine/Programs/카카오톡/카카오톡.desktop
```
바탕화면에서 카카오톡 아이콘을 찾아 우클릭 후 `Allow Launching` 클릭