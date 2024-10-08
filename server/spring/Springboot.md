스프링 부트(Spring Boot)는 웹 프로그램을 쉽고 빠르게 만들 수 있도록 도와주는 자바 웹 프레임워크이다.  스프링 부트는 프레임워크에 톰캣(Tomcat)이라는 서버를 내장하고 편의 기능을 추가하여 개발자 사에에서 인기가 많다. 톰캣은 클라이언트의 요청을 해석하여 그에 맞는 자바 프로그램을 실행한 후 그 결과를 응답해주는 웹애플리케이션 서버이다.

### 웹 프레임워크

웹에 필요한 기능을 만들어 놓은 스타터키트이다. 그리고 자바로 만든 웹 프레임워크중 하나가 스프링 부트이다.

### 톰캣 내장 서버

스프링 부트에는 톰캣 서버가 내장되어있어 설정도 자동적용되고 배포되는 jar파일에도 톰캣 서버가 내장되어 실행되기 때문에 WAS(Wdb Application Server)를 신경쓰지 않아도 된다. WAS는 웹 애플리케이션과 서버 환경을 연결하는 중간 역할을 하는 소프트웨어 플랫폼이다.

### 웹 서비스

클라이언트와 서버는 다음과 같은 관계를 가진다.

![Untitled](https://github.com/user-attachments/assets/4c8cd92f-20ed-44a7-9cb6-fab919299950)

브라우저에서 서버로 요청을 보낼 때는 서버의 주소나 서버의 주소를 대체할 수 있는 도메인명을 알아야 한다. 주소 창에 도메인을 입력하면 웹 서버가 호출되고 서버는 요청에 대한 응답으로 HTML문서나 다른 리소스들을 브라우저에 표시한다.

### IP주소와 포트번호

서버는 웹 서비스뿐만 아니라 FTP, 이메일 서비스 등도 운용할 수 있다. 이땐 같은 IP를 사용하고 포트로 서비스를 구분한다. 아래는 대표적인 서비스의 종류이다.

![Untitled 2png](https://github.com/user-attachments/assets/451aa4a8-ff40-4815-8543-1e2c93ed5630)

> 위는 기본 포트번호이다. 클라이언트나 서버등 대부분 이 번호를 기본값으로 설정한다. 하지만 필요에 따라 포트번호를 별도로 정의하고 변경할 수 있다. HTTP의 포트 80대신 8080을 사용할 수 있다.
>

### localhost:8080

localhos는 내 컴퓨터의 IP주소를 의미하고 8080은 8080번 포트로 서비스를 운용하겠다는 뜻이다. \