### Wake On Lan
WOL을 설정할 lan 카드 확인
```sh
# ifconfig
enp3s0: 
```
랜카드의 WOL 상태 확인  
g는 활성화 상태  
d는 비활성화 상태
```sh
# ethtool enp3s0 | grep Wake-on
        Supports Wake-on: pumbg
        Wake-on: d
```
활성화 상태로 변경
```sh
# /sbin/ethtool -s enp3s0 wol g
```
위 명령어는 재부팅 시 초기화 됨  
부팅시에 자동 적용되도록 네트워크 인터페이스 파일 수정
```sh
# vi /etc/sysconfig/network-scripts/ifcfg-enp3s0
```
내용 추가
```sh
ETHTOOL_OPTS="wol g"
```
