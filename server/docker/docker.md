# Docker

# Docker

## **Accelerate how you build, share, and run applications**

> 컨테이너 기반의 응용 프로그램의 배포, 확장 및 관리를 자동화할 수 있는 오픈 소스 가상화 플랫폼이다.
>

---

# 컨테이너

컨테이너는 하나의 실물 컴퓨팅 자원을 가상으로 쪼개 사용하거나, 여러 개의 실물 컴퓨팅 자원을 묶어 하나의 자원으로 사용하는 가상화 기술 중 하나이다.

## 사용해야하는 이유

- 하드웨어 리소스 효율
- 효율적 인프라 관리
- 하나의 물리적 머신에서 여러 운영체제 관리 등

## VM vs 컨테이너

Virtual Machine 가상화와 컨테이너 가상화의 차이는 무엇일까

![img1 daumcdn](https://github.com/user-attachments/assets/980d2578-d968-4edf-9976-f9ed7562db94)

VM의 경우 Host OS  위에 가상화를 위한 Hypervisor 엔진, 그리고  Guest OS를 올려 사용한다. 이는 가상화된 하드웨어 위에 OS가 올라가는 형태로 **Host와 거의 완벽히 분리**된다.  그러나 OS위에 OS를 올리기 때문에 **무겁고 느리다**.

반면 컨테이너 기반 가상화는 Docker엔진 위에 Application 실행에 필요한 바이너리만 올라가게 된다.  따라서 Host OS와 Docker 엔진 위에서 바로 동작하고 Host의 커널을 공유하기 때문에 io처리가 쉽게 되어 **높은 성능**을 가진다.

OS가상화는 더 높은 레벨을 격리를 지원해 보안적 측면에서 유리하다. 그럼에도 Docker를 쓰는 이유는 **성능향상, 뛰어난 이식성, 쉽게 Scale Out이 가능한 유연성**으로 보여진다.

# docker image

docker image는 **컨테이너를 실행할 수 있는 실행파일, 설정** 값 등을 말한다. image를 컨테이너에 담고 실행시키면 해당 프로세스가 동작하게 된다.

![img1 daumcdn](https://github.com/user-attachments/assets/f4d70c5a-c9b2-43e9-8b74-e208064c8e57)

참고 자료

: [https://khj93.tistory.com/entry/Docker-Docker-개념](https://khj93.tistory.com/entry/Docker-Docker-%EA%B0%9C%EB%85%90)

: https://adjh54.tistory.com/352

: [https://www.alibabacloud.com/ko/knowledge/what-is-virtualization?_p_lc=1](https://www.alibabacloud.com/ko/knowledge/what-is-virtualization?_p_lc=1)