- MVC

  MVC(Model, View, Controller)는 하나의 애플리케이션, 프로젝트를 구성할때 그 구성요소를 세 가지의 역할로 구분한 디자인패턴이다.

  ### Model

  Model은 소프트웨어나 애플리케이션에서 정보 및 데이터 부분을 의미한다. 이는 Controller에게 받은 데이터를 조작(가공)하는 역할을 수행한다고 볼 수 있다. 즉, **데이터와 관련된 부분을 담당하며 값과 기능을 가지는 객체**이다.

  Model은 다음 규칙을 따라야 한다.

    1. 사용자가 편집하길 원하는 모든 데이터를 가지고 있어야 한다.
    2. View나 Controller에 대해서 어떤 정보도 알지 말아야 한다.
    3. 변경이 일어나면, 변경 통지에 대한 처리방법을 구현해야만 한다.

  ### View

  View는 입력값이나 체크박스 등과 같은 사용자 인터페이스 요소를 나타낸다. 이는 **Controller에게 받은 Model의 데이터를 사용자에게 시각적으로 보여주기 위한 역할을 수행**한다.

  View는 다음 규칙을 따라야 한다.

    1. Model이 가지고 있는 정보를 따로 저장해서는 안된다.
    2. Model이나 Controller를 알고 있을 필요가 없다.
    3. 변경이 일어나면 변경통지에 대한 처리방법을 구현해야만 한다.

  ### Controller

  Controller는 Model과 Ciew 사이에서 데이터 흐름을 제어한다. 사용자가 접근한 URL에 따라 요청을 파악하고 URL에 적절한 Method를 호출하여 Service에서 비즈니스 로직을 처리한다. 이후 Model에 저장하여 View에게 전달하는 역할을 수행한다. 결국 **Controller는 Model과 View의 역할을 분리하는 중요한 요소**이다.

  Controller는 다음 규칙을 따라야 한다.

    1. Model이나 View에 대해서 알고 있어야 한다.
    2. Model이나 View의 변경을 모니터링 해야 한다.


## Spring MVC

스프링 프레임워크에서 MVC2 모델을 좀 더 발전시킨 웹 모듈이다.



프론트 컨트롤러가 우선적으로 클라이언트로부터 모든 요청을 받게 된다. 실제 요청 처리는 개별 컨트롤러 클래스로 위임한다.

개별 컨트롤러 클래스는 핸들러(Handler)라고도 하며, DI를 통해 생성해둔 Bean을 통해 비지니스 로직 처리 결과를 Model에 담아 다시 프론트 컨트롤러로 보낸다. 프론트 컨트롤러는 받은 Model을 알맞은 View 템플릿으로 전달하여 반영시키고, 최종적으로 클라이언트로 보낼 화면을 응답결과로 전송한다.

![img1.daumcdn.png](..%2F..%2F..%2FUsers%2Freviv%2FDownloads%2Fimg1.daumcdn.png)
## Filter

필터는 요청이 DispatcherServlet에 의해 다뤄지기 전, 후에 작동된다.

필터는 주로 요청에 대한 인증, 권한 체크 등을 하는데 쓰인다.  들어온 요청이 DispatcherServlet에 전달되기 전에 헤더를 검사해 인증 토큰이 있는지 없는지, 올바른지 아닌지 검사한다.

![blr7x6q.png](..%2F..%2F..%2FUsers%2Freviv%2FDownloads%2Fblr7x6q.png)
## DispatcherServlet

- 가장 앞 단에서 클라이언트의 요청을 처리하는 Controller로 요청부터 응답까지 전반적인 처리과정을 통제한다.
- Front Controller역할을 수행하며 Request를 각각의 Controller에게 위임한다.

1. 클라이언트가 서버에 요청을 하면, Front Contrlloer인 DispatcherServlet 클래스가 요청을 받는다 .
2. DispatcherServlet은 프로젝트 파일 내의 servlet-context.xml파일의 @Controller인자를 통해 등록한 요청 위임 컨트롤러를 찾아 매핑된 컨트롤러가 존재하면 @RequestMapping을 통해 요청을 처리할 메소드로 이동한다.
3. 컨트롤러는 해당 요청을 처리한 Service를 받아 비즈니스 로직을 서비스에게 위임한다.
4. Service는 요청에 필요한 작업을 수행하고, 요청에 대해 DB에 접근해야 한다면 DAO에 요청하여 처리를 위임한다.
5. DAO는 DB정보를 DTO를 통해 받아 서비스에게 전달한다.
6. 서비스는 전달받은 데이터를 컨트롤러에게 전달한다.
7. 컨트롤러는 Model객체에게 요청에 맞는 View정보를 담아 DispatcherServlet에게 전송한다.
8. DispatcherServlet은 ViewResolver에게 전달받은 View정보를 전달한다.
9. ViewResolver는 응답할 View에 대한 JSP를 찾아 DispatcherServlet에게 전달한다. (JSP는 JavaServerPages의 약자로 HTML코드에 JAVA 코드를 넣어 동적웹페이지를 생성하는 웹어플리케이션 도구이다. )
10. DispatcherServlet은 응답할 뷰의 Render를 지시하고 뷰는 로직을 처리한다.
11. DispatcherServlet은 클라이언트에게 Rending된 뷰를 응답하며 요청을 마친다.