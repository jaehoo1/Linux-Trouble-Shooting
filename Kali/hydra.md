## THC-Hydra
Please do not use in military or secret service organizations, or for illegal purposes  
(this is non-binding, these *** ignore laws and ethics anyway).  
군사 또는 비밀 서비스 기관이나 불법적인 목적으로 사용하지 마십시오.  
  
hydra는 병렬화된 로그인 크래커로 수많은 프로토콜에 대해 Brute Force 공격을 지원한다  

### Hydra 툴이 크래킹 지원되는 서비스 [(참고)](https://koromoon.blogspot.com/2020/07/hydra.html)
adam6500 asterisk cisco cisco-enable cvs firebird ftp[s] http[s]-{head|get|post} http[s]-{get|post}-form http-proxy http-proxy-urlenum icq imap[s] irc ldap2[s] ldap3[-{cram|digest}md5][s] memcached mongodb mssql mysql nntp oracle-listener oracle-sid pcanywhere pcnfs pop3[s] postgres radmin2 rdp redis rexec rlogin rpcap rsh rtsp s7-300 sip smb smtp[s] smtp-enum snmp socks5 ssh sshkey svn teamspeak telnet[s] vmauthd vnc xmpp  
  
### 옵션[(참고)](https://epicarts.tistory.com/52)
-l 옵션으로 로그인 할 이름을 줄 수 있고 -p 옵션으로 패스워드 옵션을 줄 수 있음  
-L이나 -P 같이 대문자로 사용을 하게 되면 파일 불러옴  
```
 -R        이전에 중단되거나 충돌된 세션을 복원함
  -I        기존 복원 파일을 무시 (10초 동안 기다리지 마십시오)
  -S        SSL 연결 수행
  -s PORT   서비스가 다른 기본 포트일 경우 여기에 정의
  -l LOGIN or -L FILE  지정된 로그인 명으로 로그인하거나 파일로부터 여러 로그인을 로드함
  -p PASS  or -P FILE  지정된 패스워드를 시도하거나 파일로부터 여러 패스워드를 로드함
  -x MIN:MAX:CHARSET  패스워드 무자별대입(bruteforce) 생성, "-x -h" 를 입력하여 도움을 받으십시오
  -y        무차별대입(bruteforce) 에서 기호 사용 금지, 위 참조
  -e nsr    "n" 은 널 패스워드(null password), "s" 는 로그인을 패스워드로 사용하거나(and/or) "r" 은 역방향 로그인을 시도함
  -u        패스워드가 아닌 사용자를 반복함 (effective! implied with -x)
  -C FILE   -L/-P 옵션 대신 콜론(:)으로 구분된 "로그인:패스워드" 형식
  -M FILE   공격할 서버 목록, 한 줄에 한 항목, 포트를 지정할려면 ':'
  -o FILE   찾은 로그인/패스워드 쌍을 stdout 대신 파일에 쓰기
  -b FORMAT -o FILE 형식을 지정 : text(기본값), json, jsonv1
  -f / -F   로그인/패스워드 쌍을 발견되면 종료 (-M : 호스트 당 -f, 전역 -F)
  -t TASKS  대상 당 병렬 연결 수를 지정된 수(TASKS)로 실행 (기본값 : 16)
  -T TASKS  전체를 지정된 수(TASKS)로 병렬 연결 (-M 일 경우 기본값 64)
  -w / -W TIME  응답 대기 시간 (32) / 스레드 당 연결 수 (0)
  -c TIME   모든 스레드에서 로그인 시도당 대기 시간 (-t 1 시행)
  -4 / -6   IPv4 (기본값) / IPv6 주소 사용 (-M 에도 항상 []에 넣으십시오)
  -v / -V / -d 상세 모드 / 시도할 때마다 로그인+패스워드 표시 / 디버그 모드
  -O        이전 SSL v2 및 v3 사용
  -q        연결 오류에 대한 메시지를 출력하지 않음
  -U        서비스 모듈 사용법 세부사항
  -h        더 많은 명령줄 옵션 (완전한 도움말)
  server    대상 : DNS, IP 또는 192.168.0.0/24 (this OR the -M option)
  service   크랙하는 서비스 (지원되는 프로토콜은 아래 참조)
  OPT       일부 서비스 모듈은 추가 입력을 지원함 (모듈 도움말을 보고자 한다면 -U)
```

### 패스워드 사전 파일 추천 링크
https://download.g0tmi1k.com/wordlists/large/

### 예제
`hydra -l root -P [passwdfile] [ip] ssh`  
`hydra -l root -P [passwdfile] -f [ip] ssh`  
`hydra -L [userfile] -P [passwdfile] -f [ip] ftp`
```
  hydra -l user -P passlist.txt ftp://192.168.0.1
  hydra -L userlist.txt -p defaultpw imap://192.168.0.1/PLAIN
  hydra -C defaults.txt -6 pop3s://[2001:db8::1]:143/TLS:DIGEST-MD5
  hydra -l admin -p password ftp://[192.168.0.0/24]/
  hydra -L logins.txt -P pws.txt -M targets.txt ssh
```

============================================================  
#### 원 문서
KOROMOON : https://koromoon.blogspot.com/  
EpicArts : https://epicarts.tistory.com/52
