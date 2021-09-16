- Network
  - [Socket, Socket 프로그래밍](#Socket,-Socket-프로그래밍)
  - 





# Socket, Socket 프로그래밍

## Socket
프로그램이 네트워크에서 데이터를 송수신할 수 있도록 네트워크 환경에 연결할 수 있게 만들어진 연결부  
주어진 기본적인 통신 구조는 잘 알려져있어 보안에 취약하다 그래서 **나만의 통신구조를 설계**하는데 그것이 바로 소켓 프로그래밍  

서버와 통신을 할 때 서버의 특정 App에 접근을 하기 위해서는 특정 Port와 연결이 되어야 한다.  
설계하는 소켓프로그래밍은 이 소켓 부분을 설계에서 어떠한 방식으로 통신을 할지 정해주는 것  

해당 Port에 가면 소켓을 거친 뒤에 App에 접근 & 이용을 한다  

## 소켓의 통신방식
![image](https://user-images.githubusercontent.com/48474613/133589336-3a803196-fcd2-4eff-b873-b143091aa1cf.png)
1. Client class 생성
2. 해당 클래스에 서버의 IP 주소와 Port번호를 넣고 출력 스트림 (Get Outputstream)으로 넘어간 후 Server Socket에 접근
3. Server Socket class는 클라이언트가 접속을 했는지 체크
4. 접근 인식시 Server class가 Socket.accpet() 메소드 실행

++ 하나의 서버에 여러 컴퓨터가 접속시?  
Server Socket하나가 여러개 컴퓨터의 client 접속을 인식  
클라이언트 1개당 1개의 서버 소켓 생성 -> 서버 소켓이 너무 많아지면 과부하 -> 해결하기 위해 Thread가 나옴


## Socket 프로그래밍
> Server와 Client가 특정 Port를 통해 실시간으로 양방향 통신을 하는 방식

Socket 연결은 TCP/IP 프로토콜을 기반으로 맺어진 네트워크 연결 방식  
**Server와 Client가 특정 Port를 통해 연결을 유지하고 있어 실시간으로 양방향 통신을 할 수 있는 방식**
Client가 필요한 경우에 요청을 보낼 수 있는 Http 프로그래밍과 달리 **Socket 프로그래밍은 Server 역시 Client로 요청을 보낼 수 있으며** 계속 연결을 유지하는 연결지향형 방식이기 때문에 실시간 통신이 필요한 경우에 자주 사용

ex) 실시간 Streaming, 채팅..
