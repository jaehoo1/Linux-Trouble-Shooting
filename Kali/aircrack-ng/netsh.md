### netsh (Windows cmd)
Netsh는 현재 실행 중인 컴퓨터의 네트워크 구성을 표시하거나 수정할 수 있는 명령줄 스크립팅 유틸리티입니다... [(더 읽기)](https://docs.microsoft.com/ko-kr/windows-server/networking/technologies/netsh/netsh-contexts)  
  
예전에 연결했었던 와이파이 비밀번호를 잊었을 때 netsh로 볼 수 있다  
윈도우가 연결되어 있는 모든 네트워크 목록 표시  
`netsh wlan show profile`  
네트워크 범위 밖에 있는 목록에 보안키 표시  
`netsh wlan show profile name="network_name" key=clear`  
  
Mac 명령어  
`security find-generic-password -wa network_name`
