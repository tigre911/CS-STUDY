#### **1\. 네트워크의 기초**

네트워크란 노드와 링크가 서로 연결되어 있거나 연결되어 있지 않은 집합체를 의미한다.

[##_Image|kage@K2Nzb/btrMNSt8sxS/j6RcUkSYKmMFwcFHFk7yPK/img.png|CDM|1.3|{"originWidth":400,"originHeight":286,"style":"alignLeft","width":249,"height":178}_##]

여기서 노드란 서버, 라우터, 스위치 등 네트워크 장치를 의미하고 링크는 유선 또는 무선을 의미함.

#### **1.1 처리량과 지연 시간**

네트워크를 구축할때는 좋은 네트와크를 구축해야하는데 좋은 네트워크란 많은 처리량을 처리할 수 있으며 지연 시간이 짧고 장애 빈도가 적으며 좋은 보안을 갖춘 네트워크를 말한다.

**처리량**

처리량이란 링크를 통해 전달되는 단위 시간당 데이터양.

[##_Image|kage@AnC5U/btrMNJxr07x/H4yOgNeCiv2nuktdBnv411/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":345,"style":"alignLeft","width":264}_##]

단위로는 bps(bit per second)를 쓴다.

처리량은 사용자들이 많이 접속할 때마다 커지는 트래픽, 네트워크 장치 간의 대역폭, 네트워크 중간에 발생하는 에러, 장치의 하드웨어 스펙에 영향을 받는다.

\* 대역폭 - 주어진 시간 동안 네트워크 연결을 통해 흐를 수 있는 최대 비트 수

**지연 시간**

지연 시간이란 요청이 처리되는 시간을 말하며 어떤 메시지가 두 장치 사이를 왕복하는데 걸린 시간을 말함.

[##_Image|kage@qms6C/btrMJPsbtrA/cddqdZWDzvzwCqbkxGYS1k/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":293,"style":"alignLeft","width":369,"height":180}_##]

지연 시간은 매체 타입(무선, 유선), 패킷 크기, 라우터의 패킷 처리 시간에 영향을 받음.

#### **1.2 네트워크 토폴로지와 병목 현상**

**네트워크 토폴로지**

네트워크를 설계할 때 고려하는 네트워크 **토폴로지는** 노드와 링크가 어떻게 배치되어 있는지에 대한 방식이자 연결 형태를 의미한다.

**트리 토폴로지**

트리(tree) 토폴로지는 **계층형** 토폴로지라고 하며 **트리 형태**로 배치한 네트워크 구성을 말한다.

[##_Image|kage@xdRdL/btrMNSubTkp/hxOKlyieclarkzDaiRmon0/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":353,"style":"alignLeft","width":326,"height":192}_##]

노드의 추가 , 삭제가 쉬우며 특정 노드에 트래픽이 집중될 때 하위 노드에 영향을 끼칠 수 있다.

**버스 토폴로지**

버스(bus) 토폴로지는 **중앙 통신 회선 하나에 여러 개의 노드**가 연결되어 공유하는 네트워크 구성을 말하며 근거리 통신망(LAN)에서 사용한다.

[##_Image|kage@cwQWxQ/btrMMjMR940/chFBnqHCEVKUbdlxKwKrDK/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":226,"style":"alignLeft","width":321,"height":121}_##]

설치 비용이 적고 신뢰성이 우수하며 중앙 통신 회선에 노드를 추가하거나 삭제하기 쉽다. 그러나 스푸핑이 가능한 문제점이 있다.

**스푸핑**

스푸핑은 LAN상에서 송신부의 패킷을 송신과 관련 없는 다른 호스트에 가지 않도록 하는 스위칭 기능을 마비시키거나 속여서 특정 노드에 해당 패킷이 오도록 처리하는 것을 말한다.

[##_Image|kage@MIe1P/btrMKVFx49x/SkK5OMyapsbVyBEc0GJlv0/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":244,"style":"alignLeft","width":411,"height":167}_##]

위의 그림처럼 스푸핑을 적용하면 올바르게 수신부로 가야 할 패킷이 악의적인 노드에 전달되게 된다.

**스타 토폴로지**

스타 토폴로지는 중앙에 있는 노드에 모두 연결된 네트워크 구성을 말한다.

[##_Image|kage@zi6Pv/btrMOT0dR55/nzeQbjHOWtYBxw8Z1NmRek/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":426,"style":"alignLeft","width":315,"height":224}_##]

노드를 추가하거나 에러를 탐지하기 쉽고 패킷의 충돌 발생 가능성이 적다. 또한, 어떠한 노드에 장애가 발생해도 쉽게 에러를 발견할 수 있으며 장애 노드가 중앙노드가 아닐 경우 다른 노드에 영향을 끼치는 것이 적다.

중앙 노드에 장애가 발생하면 전체 네트워크를 사용할 수 없고 설치 비용이 고가이다.

**링형 토폴로지**

링형(ring) 토폴로지는 각각의 노드가 양옆의 두 노드와 연결하여 전체적으로 고리처럼 하나의 연속된 길을 통해 통신을 하는 망 구석 방식이다.

[##_Image|kage@bpzjWn/btrMOS1qPdz/gVwYrplfGqmGbwEBDN2gW1/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":500,"style":"alignLeft","width":283}_##]

데이터는 노드에서 노드로 이동하고, 각각의 노드는 고리 모양의 길을 통해 패킷을 처리한다.

노드 수가 증가되어도 네트워크상의 손실이 거의 없고 충돌이 발생되는 가능성이 적고 노드의 고장 발견을 쉽게 찾을 수 있다. 하지만 네트워크 구성 변경이 어렵고 회선에 장애가 발생하면 전체 네트워크에 영향을 크게 끼치는 단점이 있다.

**메시 토폴로지**

메시(mesh)토폴로지는 망형 토폴로지라고 하며 그물망 처럼 연결되어 있는 구조이다.

[##_Image|kage@eCrfxh/btrMMjM0P7p/sFZ8pPhE0tBS7C38pueHdK/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":485,"style":"alignLeft","width":263,"height":213}_##]

한 단말 장치에 장애가 발생해도 여러 개의 경로가 존재하므로 네트워크를 계속 사용할 수 있고 트래픽도 분산 처리가 가능하다. 하지만 노드의 추가가 어렵고 구축 비용과 운용 비용이 고가인 단점이 있다.

**병목 현상**

네트워크의 구조라고도 일컫는 토폴로지가 중요한 이유는 병목 현상을 찾을 때 중요한 기준이 되기 때문이다.

[##_Image|kage@bELzbD/btrMK2ENrIg/3reTKIkVoWlUqTbEnjMrf0/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":393,"style":"alignLeft","width":308,"height":202}_##]

▲  회선 추가 전

위의 그림처럼 서비스가 있을 때, 병목 현상이 일어나서 사용자가 서비스를 이용할 때 지연 시간이 길게 발생하고 있다.

관리자가 지연시간을 짧게 만들기 위해 대역폭을 크게 설정했음에도 성능이 개선되지 않았다.

[##_Image|kage@bbT1qv/btrMMkZuF0p/FBgv0CcduQKYeJCXsbgma1/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":402,"style":"alignLeft","width":343,"height":230}_##]

▲  회선 추가 이후

관리자가 서버와 서버간, 게이트웨이로 이어지는 회선을 추가해서 병목현상을 해결했다.

이처럼 네트워크가 어떤 토폴로지를 갖는지, 또한 어떠한 경로로 이루어져 있는지 알아야 병목 현상을 올바르게 해결할 수 있다.

#### **1.3 네트워크 분류**

네트워크는 규모를 기반으로 분류할 수 있다.

사무실과 개인적으로 소유 가능한 규모인 LAN과 서울시 등 시 정도 규모인 MAN, 그리고 세계규모인 WAN으로 나뉜다

LAN(Local Area Network) - 근거리 통신망을 의미, 전송 속도가 빠르고 혼잡하지 않다.MAN(Metropolitan Area Network) - 대도지 지역 네트워크, 전송 속도는 평균 LAN보다는 혼잡WAN(Wide Area Network) - 광역 네트워크 국가 또는 대륙같은 넓은 지역에서 운영, 전송 속도는 낮으며 MAN보다 혼잡

#### **1.4 네트워크 성능 분석 명령어**

애플리케이션 코드상에서는 전혀 문제가 없는데 사용자가 서비스로 부터 데이터를 가지오기 못하는 상황이 발생한다.이는 네트워크 병목 현상일 가능성이 있다. 주된 원인은 다음과 같다\- 네트워크 대역폭\- 네트워크 토폴로지\- 서버 CPU, 메모리 사용량\- 비효율적인 네트워크 구성이때는 테스트를 통해 '네트워크로 인한 문제점'을 인지한 후 네트워크 성능 분석을 해야한다.

**ping**

ping(Packet INternet Groper)은 네트워크 상태를 확인하려는 대상 노드를 향해 일정 크기의 패킷을 전송하는 명령어.이를 통해 해당 노드의 패킷 수신 상태와 도달하기 까지 시간 등을 알 수 있고 해당 노드까지 네트워크가 잘 연결되어 있는지 확인 할 수 있다.ping은 TCP/IP 프로토콜 중에 ICMP 프로토콜을 통해 동작하며ㅡ 이때문에 ICMP 프로토콜을 지원하지 않는 기기를 대상으로는 실행할 수 없거나 네트워크 정책상 ICMP 나 traccerout를 차단하는 대상일 경우 ping 테스팅은 불가능하다.ping\[IP주소 또는 도메인 주소\]로 실행한다.

[##_Image|kage@bF6YRE/btrMOSf9mnE/ebzQMwjDS8W9ORrm8LeLf1/img.png|CDM|1.3|{"originWidth":455,"originHeight":336,"style":"alignLeft","width":356,"height":263}_##]

**netstat**

netstat 명령어는 접속되어 있는 서비스들의 네트워크 상태를 표시하는 데 사용되며 네트워크 접속, 라우팅 테이블, 네트워크 프로토콜 등 리스트를 보여준다. 주로 서비스의 포트가 열려 있는지 확인 할 때 쓴다.

**nslookup**

nslookup은 DNS에 관련된 내용을 확인하기 위해 쓰는 명령어이다. 특정 도메인에 매핑된 IP를 확인하기 위해 사용한다.

**tracert**

윈도우에서 tracert이고 리눅스에서는 traceroute 라는 명령어로 구동된다.목적지 노드까지 네트워크 경로를 확인할 때 사용하는 명령어이다.목적지 노드 까지 구간들 중 어느 구간에서 응답 시간이 느려지는지 등을 확인 할 수 있다.

1.5 네트워크 프로토콜 표준화네트워크 프로토콜이란 다른 장치들끼리 데이터를 주고 받기 위해 설정된 공통된 인터페이스를 말한다.이러한 프로토콜은 IETF라는 표준화 단체가 이를 정한다.

#### **2\. TCP/IP 4계층 모델**

인터넷 프로토콜 스위트는 인터넷에서 컴퓨터들이 서로 정보를 주고받는데 쓰이는 프로토콜의 집합이며, 이를 TCP/IP 4계층 모델로 설명하거나 OSI 7계층 모델로 설명하기도 한다.

**2.1 계층 구조**

TCP/IP 계층은 4계층을 가지고 있다.

[##_Image|kage@dGISjG/btrMNc8shUE/zEz5PFZgE3OsMRoogcypBk/img.png|CDM|1.3|{"originWidth":800,"originHeight":391,"style":"alignLeft","width":604}_##]

이 계층들은 특정 계층이 변경되었을 때 다른 계층이 영향을 받지 않도록 설계되었다.

**애플리케이션 계층**

애플리케이션 계층은 FTP, HTTP, SSH, SMTP, DNS 등 응용 프로그램이 사용되는 프로토콜 계층이며 웹 서비스, 이메일 등 서비스를 실질적으로 사람들에게 제공하는 층이다.

> FTP - 장치와 장치간의 파일을 전송하는데 사용되는 표준 통신 프로토콜  
> HTTP - World Wide Web을 위한 데이터 통신의 기초이자 웹사이트를 이용하는데 쓰는 프로토콜  
> SSH - 보안되지 않은 네트워크에서 네트워크 서비스를 안전하게 운영하기 위한 암호화 네트워크 프로토콜  
> SMTP - 전자 메일 전송을 위한 인터넷 표준 통신 프로토콜  
> DNS - 도메인 이름과 IP주소를 매핑해주는 서버
