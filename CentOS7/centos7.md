### GRUB 기본부팅
https://ghostweb.tistory.com/826

### telnet
systemctl restart telnet.socket  
https://itdev4u.tistory.com/entry/CentOS-Telnet-%EC%84%A4%EC%B9%98

### 로그인 시 경고문
issue, issue.net	/etc/issue

### cd .. 차단
http://bywoong.com/post/1771

### 홈이탈방지
아래 디렉토리들의 권한을 변경하여 다른 폴더로의 접근 막음  
chmod -R  
/usr/local  
/boot  
/mnt  
/opt  
/bin  
/var

### VNC
systemctl start vncserver@:1.service  
https://blog.naver.com/haengro/220346527168

### vsftpd(ftp)
systemctl restart vsftpd.service  
https://goddaehee.tistory.com/73  
https://ckbcorp.tistory.com/1202  
\+ chroot_local_user=YES 활성화

### proftpd(ftp)
시작 :	/usr/local/proftpd/sbin/proftpd  
종료 :	ps -ef | grep proftpd  
 &nbsp; kill -9 UID  
ftp user 확인  
ps aux | grep vsftpd  

### ssh
systemctl restart sshd.service  
https://itdev4u.tistory.com/entry/CentOS-SSH-%EC%84%A4%EC%B9%98  
ssh [계정]@[ip]

### postgreSQL & DBeaver
systemctl start postgresql  
https://gsk121.tistory.com/392  
https://medium.com/@jinseok.choi/centos-7%EC%97%90%EC%84%9C-postgresql-11-%EC%84%A4%EC%B9%98%ED%95%98%EA%B8%B0-77bc0da9d0af  
https://meyouus.tistory.com/243  
https://zipeya.tistory.com/entry/postgresql-DB%EC%83%9D%EC%84%B1-%EB%B0%8F-%EC%A0%91%EC%86%8D-%EC%8B%9C-Peer-authentication%EC%97%90%EB%9F%AC-%EB%B0%9C%EC%83%9D-%EC%8B%9C-%ED%95%B4%EC%95%BC%ED%95%A0-%EA%B2%83  
https://nirsa.tistory.com/257  

### psql 명령어
https://dbrang.tistory.com/749

### APM 참고
https://www.manualfactory.net/10101  
https://zetawiki.com/wiki/CentOS_APM_%EC%84%A4%EC%B9%98_(yum)  

### php (사용할 기능들을 미리 고려해서 버전을 정해야 함. 기본 : 5.4)
yum install -y php*  
https://www.opentutorials.org/module/1701/10235  

### MariaDB
yum install -y mariadb*  
https://jeongyd.tistory.com/54  
https://bamdule.tistory.com/59  

### MySQL utf-8
https://zetawiki.com/wiki/MySQL_%EC%BA%90%EB%A6%AD%ED%84%B0%EC%85%8B_utf8_%EC%84%A4%EC%A0%95

### DB 작업
https://bebhionn.tistory.com/8?category=239054  
https://m.blog.naver.com/bgpoilkj/220751401209

### php + mariadb 한글 깨짐
https://jhrun.tistory.com/140

### php reference
https://www.w3schools.com/php/func_mysqli_fetch_array.asp

### 채팅서버(irssi, unrealircd)
https://marcolenzo.eu/2016/01/30/install-unrealircd-server-on-centos-7/  
https://lovename.org/entry/irc-%EC%84%9C%EB%B2%84%EA%B5%AC%EC%B6%95  
https://operatingsystems.tistory.com/entry/Vul-IRC-%EC%84%9C%EB%B2%84-%EA%B5%AC%EC%B6%95  
unrealircd 설치된 경로로 이동  
./unrealircd start stop  

### 채팅클라이언트
yum -y install irssi  

### 방화벽 firewalld
http://help.nanuminet.com/bbs/board.php?bo_table=manual&wr_id=281  
https://m.blog.naver.com/tequini/220981170535

### SAMBA
yum -y install samba  
smbpasswd -a root  
vi /etc/samba/smb.conf  
```sh
[root]
        comment = "코멘트"
        path = /root  # 경로
        valid users = root <user> # 접근 가능한 유저
        read only = no  # 읽기 전용
        writable = yes  # 쓰기 가능
        public = no
        browseable =yes
        printable = no
        create mask = 0750
```
firewall-cmd --permanent --zone=public --add-service=samba  
firewall-cmd --reload  
systemctl enable smb	systemctl start smb

### SAMBA selinux
https://m.blog.naver.com/PostView.naver?blogId=hdlee91&logNo=150063056693&proxyReferer=https:%2F%2Fwww.google.com%2F

### 로그서버
https://www.manualfactory.net/12970  

### DNS bind
https://it-serial.tistory.com/13  
https://it-serial.tistory.com/14?category=958591

### sendmail
https://m.blog.naver.com/PostView.naver?blogId=picablue6252&logNo=221502528457&proxyReferer=https:%2F%2Fwww.google.com%2F

### rsync mirror
https://blog.daum.net/boo-t/11397665  
https://lifegoesonme.tistory.com/373  
https://nota.tistory.com/77  
https://banitos.tistory.com/1
