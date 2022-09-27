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

**전송 계층**

전송 계층은 송신자와 수신자를 연결하는 통신 서비스를 제공하며 연결 지향 데이터 스트림 지원, 신뢰성, 흐름 제어를 제공하며, 애플리케이션과 인터넷 계층 사이의 데이터가 전달 될때의 중계 역할을 한다.

예로는 TCP, UDP 등이 있다.

TCP는 패킷 사이의 순서를 보장하고 연결지향 프로토콜을 사용해서 연결을 함. 신뢰성을 구축해서 수신여부를 확인하며 '가상회선 패킷 교환 방식'을 사용한다.

UDP는 순서를 보장하지 않고 수신 여부를 확인하지 않으며 단순히 데이터만 주는 '데이터그램 패킷 교환 방식'을 사용한다.

**가상회선 패킷 교환 방식**

가상회선 패킷 교환방식은 각 패킷에는 가상회선 식별자가 포함되며 모든 패킷을 전송하면 가상회선이 해제되고 패킷들은 전송된 순서대로 도착하는 방식을 말한다.

[##_Image|kage@cptpwk/btrMU6mwEs2/Pb0nun511eKK9cWDY15dFK/img.png|CDM|1.3|{"originWidth":577,"originHeight":406,"style":"alignLeft"}_##]

위의 그림을 보게되면 3,2,1로 이루어진 패킷이 회선을 따라 순서대로 도착하는 것을 알 수 있다.

**데이터그램 패킷 교환 방식**

데이터그램 패킷 교환 방식이란 패킷이 독립적으로 이동하며 최적의 경로를 선택하여 간다. 하나의 메시지에서 분할된 여러 패킷은 서로 다른 경로로 전송될 수 있으며 도착한 순서가 다를 수 있는 방식을 뜻한다.

[##_Image|kage@bxM3pq/btrMWRI3Tdq/1yiFuxmFhDZ9Ng5rPqljLk/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":448,"style":"alignLeft"}_##]

위의 그림을 보면 3,2,1로 이루어진 패킷이 순서도 다르고 어떠한 회선을 중심으로 가는 것이 아니라 따로따로 이동하며 순서도 다르게 도착하는 것을 알 수 있다.

TCP 연결 성립과정

TCP는 신뢰성을 확보할 때 '3-웨이 핸드쉐이크'라는 작업을 진행한다.

[##_Image|kage@cbRct2/btrMVG8TjWg/VaEOR7xNEG6wyjgvspikYK/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":632,"style":"alignLeft","width":446,"height":470}_##]

위의 그림처럼 클라이언트와 서버가 통신할 때 다음과 같은 세 단계의 과정을 거친다

1.  SYN 단계
2.  SYN + ACK 단계
3.  ACK 단계

이렇게 3-웨이 핸드셰이크 과정 이후 신뢰성이 구축되고 데이터 전송을 시작한다. 참고로 TCP는 이 과정이 있기 때문에 신뢰성이 있는 계층이라고 하며 UDP는 이과정이 없기 때문에 신뢰성이 없는 계층이라고 한다.

> SYN - 연결 요청 플래그  
> ACK - 응답 플래그  
> ISN - 초기 네트워크 연결을 할 때 할당된 32비트 고유 시퀀스 번호

TCP 연결 해제 과정

TCP가 연결을해제할 때는 4-웨이 핸드셰이크과정이 발생한다.

[##_Image|kage@b5307f/btrMVthwWSp/bonKVf2squ7wfa4KvQWJ5K/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":377,"style":"alignLeft","width":438,"height":275}_##]

1번:먼저 클라이언트가 연결을 닫으려고 할 때 FIN으로 설정된 세그먼트를 보낸다. 그리고 클라이언트는 FIN\_WAIT\_! 상태로 들어가고 서버의 응답을 기다린다.

2번: 서버는 클라이언트 ACK라는 승인 세크먼트를 보낸다. 그리고 CLOSE\_WAIT 상태에 들어간다. 클라이언트가 세그먼트를 받으면 FIN\_WAIT\_2 상태에 들어간다.

3번: 서버는 ACK를 보내고 일정 시간 이후에 클라이언트에 FIN이라는 세그먼트를 보낸다.

4번:클라이언트는 TIME\_WAIT 상태가 되고 다시 서버로 ACK를 보내서 서버는 CLOSED 상태가 된다. 이후 클라이언트는 어느 정도의 시간을 대기한 후 연결이 닫히고 클라이언트오 ㅏ서버의 모든 자원의 연결이 해제된다.

**인터넷 계층**

인터넷 계층은 장치로부터 받은 네트워크 패킷을 ip주소로 지정된 목적지로 전송하기위해 사용되는 계층이다.

IP, ARP, ICMP 등이 있으며 패킷을 수신해야 할 상대의 주소를 지정하여 데이터를 전달한다.

상대방이 제대로 받았는지에 대해 보장하지 않는 비연결형적인 특징을 가지고 있다.

**링크계층**

링크 계층은 전선, 광섬유, 무선 등으로 실질적으로 데이터를 전달하며 장치간에 신호를 주고 받는 '규칙'을 정하는 계층이다. 네트워크 접근 계층이라고 한다.

이를 물리 계층과 데이터 링크 계층으로 나누기도 하는데 물리계층은 무선 LAN과 유선 LAN을 통해 0과 1로 이루어진 데이터를 보내는 계층을 말하며, 데이터링크 계층은 '이더넷 프레임'을 통해 에러 확인, 흐름 제어, 접근 제어를 담당하는 계층을 말한다.

**유선 LAN**

유선 LAN을 이루는 이더넷은 IEEE802.3이라는 프로토콜을 따르며 전이중화 통신을 쓴다.

**\*전이중화 통신**

전이중화 통신은 양쪽 장치가 동시에 송수신할 수 있는 방식을 말한다. 이는 송신로와 수신로로 나눠서 데이터를 주고받으며 현대의  고속 이더넷은 이방식을 기반으로 통신하고 있다.

[##_Image|kage@cpJV81/btrM8kLVFoK/IyEBqTpag0zSYObknauSFK/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":375,"style":"alignLeft","width":382,"height":239}_##]

**\*CSMA/CD**

참고로 이전에는 유선 LAN에 '반이중화 통신' 중 하나인 CSMA/CD 방식을 썼다.

이 방식은 데이터를 보낸 후 충돌이 발생한다면 일정 시간 이후 재전송하는 방식을 말한다. 이는 수신로와 송신로를 각각 둔 것이 아니고 한 경로를 기반으로 데이터를 보내기 때문에 데이터를 보낼 때 충돌에 대해 대비해야 했기 때문이다.

**무선 LAN**

무선 LAN 장치는 수신과 송신에 같은 채널을 사용하기 때문에 반 이중화 통신을 사용한다.

**\*반이중화 통신**

반이중화 통신은  양쪽 장치는 서로 통신할 수 있지만, 동시에는 통신할 수 없으며 한 번에 한 방향만 통신할 수 있는 방식을 말한다.

[##_Image|kage@o7INg/btrM8gbFHSu/sLk4VkNyFfoOKXo4yZ27F1/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":379,"style":"alignLeft","width":368,"height":232}_##]

일반적으로 장치가 신호를 수신하기 시작하면 응답하기 전에 전송이 완료될 때까지 기다려야 한다. 또한, 둘 이상의 장치가 동시에 전송하면 충돌이 발생하여 메시지가 손실되거나 왜곡될 수 있기 때문에 충돌 방지 시스템이 필요하다.

**\*CSMA/CA**

CSMA/CA는 반이중화 통신 중 하나로 장치에서 데이터를 보내기 전에 캐리어 감지 등으로 사전에 가능한 충돌을 방지하는 방식을 사용하며 과정은 다음과 같이 이루어진다.

1\. 데이터를 송신하기 전에 무선 매체를 살핀다.

2\. 캐리어 감지 : 회선이 비어 있는지 판단한다.

3\. IFS : 랜덤 값을 기반으로 정해진 시간만큼 기다리며, 만약 무선 매체가 사용중이면 점차 그간격을 늘려가며 기다린다.

4\. 이후에 데이터를 송신한다.

전이중화 통신은 양방향 통신이 가능하므로 충돌 가능성이 없기 때문에 충돌을 감지하거나 방지하는 메커니즘이 필요하지 않다.

**와이파이**

전자기기들이 무선 LAN 신호에 연결할 수 있게 하는 기술.

유선 LAN에 흐르는 신호를 무선 LAN 신호로 바꿔준다.

**BSS**

기본 서비스 집합을 의미. 단순 공유기를 통해 네트워크에 접속하는 것이 아닌 동일 BSS 내에 있는 AP들과 장치들이 서로 통신이 가능한 구조를 말한다.

근거리 무선통신을 제공하고, 하나의 AP만을 기반으로 구축이 되어 있어 사용자가 한곳에서 다른 곳으로 자유롭게 이동하며 네트워크에 접속하는 것은 불가능하다.

**ESS** 

하나이상 연결된 BSS 그룹이다. 장거리 무선통신을 제공하며 BSS 보다 더 많은 가용성과 이동성을 지원한다.

즉, 사용자는 한 장소에서 다른 장소로 이동하며 중단없이 네트워크에 계속 연결 할 수 있다.

[##_Image|kage@9k3oK/btrM8gCHzw3/u5SXsIfFQ3kxcCkNNadzM1/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":347,"style":"alignLeft","width":431,"height":249}_##]

**이더넷 프레임**

참고로 데이터 링크 계층은 이더넷 프레임을 통해 전달받은 데이터의 에러를 검출하고 캡슐화하며 다음과 같은 구조를 가진다.

[##_Image|kage@9U2FS/btrNb84xOBV/kdqATRtvuj185xkzl85rV0/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":138,"style":"alignLeft","width":539,"height":124}_##]

• Preamble: 이더넷 프레임이 시작임을 알림.

• SFD(Start Frame Delimiter): 다음 바이트부터 MAC 주소 필드가 시작됨을 알림.

• DMAC, SMAC: 수신, 송신 MAC 주소.

• EtherType: 데이터 계층 위의 계층인 IP 프로토콜을 정의합니다. 예를 들어 IPv4 또는 IPv6.

• Payload: 전달받은 데이터

• CRC: 에러 확인 비트

**\* MAC 주소**

컴퓨터나 노트북 등 각 장치에는 네트워크에 연결하기 위한 장치(LAN 카드)가 있는데, 이를 구별하기 위한 식별번호를 말한다. 6바이트(48비트)로 구성된다.

**계층 간 데이터 송수신 과정**

컴퓨터를 통해 다른 컴퓨터로 데이터를 요청한다면 예를 들어 HTTP를 통해 웹 서버에 있는 데이터를 요청한다면 다음과 같은 일이 일어난다.

[##_Image|kage@bM4HXi/btrNcXBcLqw/va3s9atHNUwQjbS5UULNjK/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":480,"style":"alignLeft","width":444}_##]

애플리케이션 계층에서 전송 계층으로 보내는 요청(request) 값들이 캡슐화 과정을 거쳐 전달되고, 다시 링크 계층을 통해 해당 서버와 통신을 하고, 해당 서버의 링크 계층으로부터 애플리케이션까지 비캡슐화 과정을 거쳐 데이터가 전송된다.

**캡슐화 과정**

캡슐화 과정은 상위 계층의 헤더와 데이터를 하위 계층의 데이터 부분에 포함시키고 해당 계층의 헤더를 삽입하는 과정을 말합니다.

[##_Image|kage@dJKvEo/btrM8lD0ePi/rlipyZUomnsHiPdA9p4zkk/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":217,"style":"alignLeft","width":456,"height":165}_##]

애플리케이션 계층의 데이터가 전송 계층으로 전달되면서 ‘세그먼트’ 또는 ‘데이터그램’화되며 TCP(L4) 헤더가 붙여지게 된다. 그리고 이후 인터넷 계층으로 가면서 IP(L3) 헤더가 붙여지게 되며 ‘패킷’화가 되고, 이후 링크 계층으로 전달되면서 프레임 헤더와 프레임 트레일러가 붙어 ‘프레임’화가 됨.

**비캡슐화 과정**

비캡슐화 과정은 하위 계층에서 상위 계층으로 가며 각 계층의 헤더 부분을 제거하는 과정을 말합니다.

[##_Image|kage@TDKBa/btrNcAM1KTi/U7fDtfaHQRSAihwEfrVyEK/img.jpg|CDM|1.3|{"originWidth":600,"originHeight":217,"style":"alignLeft","width":437,"height":158}_##]

이렇게 캡슐화된 데이터를 받게 되면 링크 계층에서부터 타고 올라오면서 프레임화된 데이터는 다시 패킷화를 거쳐 세그먼트, 데이터그램화를 거쳐 메시지화가 되는 비캡슐화 과정이 일어난다. 그 이후 최종적으로 사용자에게 애플리케이션의 PDU인 메시지로 전달됨.

#### **2.2 PDU**

네트워크의 어떠한 계층에서 계층으로 데이터가 전달될 때 한 덩어리의 단위를 PDU (Protocol Data Unit)라고 한다.

PDU는 제어 관련 정보들이 포함된 ‘헤더’, 데이터를 의미하는 ‘페이로드’로 구성되어 있으며 계층마다 부르는 명칭이 다름

• 애플리케이션 계층: 메시지

• 전송 계층: 세그먼트(TCP), 데이터그램(UDP)

• 인터넷 계층: 패킷

• 링크 계층: 프레임(데이터 링크 계층), 비트(물리 계층)

예를 들어 애플리케이션 계층은 ‘메시지’를 기반으로 데이터를 전달하는데, HTTP의 헤더가 문자열인 것을 예로 들 수 \\

다.

잠시  curl 명령어를 이용하여 [www.naver.com으로](http://www.naver.com으로) HTTP 요청을 해서 PDU 테스팅을 해보게 되면

```
Server: NWS
Content-Type: text/html; charset=UTF-8
Cache-Control: no-cache, no-store, must-revalidate
Pragma: no-cache
P3P: CP="CAO DSP CURa ADMa TAIa PSAa OUR LAW STP PHY ONL UNI PUR FIN COM NAV INT DEM STA PRE"
X-Frame-Options: DENY
X-XSS-Protection: 1; mode=block
Strict-Transport-Security: max-age=63072000; includeSubdomains
Referrer-Policy: unsafe-url
Content-Encoding: gzip
Content-Length: 59601
Date: Wed, 26 Jan 2022 05:14:10 GMT
Connection: keep-alive
Vary: Accept-Encoding
```

‘curl [www.naver.com](http://www.naver.com)’이란 명령어를 통해 요청했고 다음과 같은 응답헤더 값이 나오는데, 이는 모두 문자열인 것을 알 수 있다. 

PDU 중 아래 계층인 비트로 송수신하는 것이 모든 PDU 중 가장 빠르고 효율성이 높다. 하지만 애플리케이션 계층에서는 문자열을 기반으로 송수신을 하는데, 그 이유는 헤더에 authorization 값 등 다른 값들을 넣는 확장이 쉽기 때문이다.
