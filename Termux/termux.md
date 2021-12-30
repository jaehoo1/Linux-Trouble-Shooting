### 안드로이드에 리눅스 컨테이너를 올리는 방법에 대한 고찰
UserLAnd : https://blog.naver.com/PostView.naver?blogId=wonjinho81&logNo=222476337969  
Termux : https://blog.naver.com/PostView.naver?blogId=wonjinho81&logNo=222597996987  
  
### Termux 기본 세팅 (ssh)
termux-setup-storage  
apt update  
apt upgrade  
pkg install openssh  
sshd (pkill sshd)  
whoami  
passwd

### 배포판 설치
apt install proot  
apt install proot-distro  
proot-distro list  
proot-distro install \<package>  
proot-distro login \<package>  
  
Kali linux 설치하다 용량이 부족해서 포기
