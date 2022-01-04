### NMap
nmap은 포트 스캔 프로그램  
  
`nmap [-주옵션] [-부옵션] <IP Ranges>`
  
[주 옵션]  
-sT/ sS/ sA/ sW/ sM  :   TCP 스캔, 차례대로 Connect/SYN/ACK/Window/Maimon 스캔 (-sT: Full connection  / -sS : SYN half 연결)  
-sU : UDP 스캔  
-sP : Ping 스캔 (Ping 을 통해 대상의 alive 여부만 파악), Ping Sweep 에 사용  
\* -sSU 와 같이 하면 TCP/UDP 스캔을 둘다 수행함  
\* 주 옵션이 생략될 경우, root 권한 default는 -sS, 일반권한 default는 -sT)  
  
[부 옵션]  
-P0 -PS : ICMP Ping 금지 / SYN 스캔 사용 (PIng sweep 에서 시간 절약)  
-sV : 포트 어플리케이션 식별  
-O : OS 식별  
-oA <filename> : 결과를 nmap, gnmap, xml 세가지 포맷의 텍스트 파일로 저장  
-p<port ranges> : 스캔 대상 포트 지정 (예시 : 21,22,23,8000-9000)  
-T<0~4> : 속도 옵션, T4 (Aggressive : 가장 빠름), T0 (Paranoid : 가장 느림)  
--min-parallelism <숫자> : 복수의 메소드를 이용해서 동시에 패킷을 전송 (상당히 대량의 패킷 발송하여 빠르게 스캔)  
-PN : 서버 탐색 없이 바로 포트 스캔 시도 (즉, 서버가 존재하는지 확인하는 과정 생략)  
-iL <filename> : 스캔 대상을 파일에서 읽어옴  
-S <IP> -e <interface> -PN : 소스 ip에 지정한 ip를 spoofing 하여 자신의 아이피를 속임  
-D <decoy1,decoy2...>  : 지정된 여러 decoy들로부터 패킷이 유입되는 걸로 위장함 (-sV 에서 사용할 수 없음)  

출처: https://vaert.tistory.com/102 [Vaert Street]
