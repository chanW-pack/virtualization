# virtualization

## Week 1 

- [x86 가상화를 이해하기 위한 기초 지식](https://github.com/chanW-pack/virtualization/blob/main/Week%201/1_1%20x86%20%EA%B0%80%EC%83%81%ED%99%94%EB%A5%BC%20%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0%20%EC%9C%84%ED%95%9C%20%EA%B8%B0%EC%B4%88%20%EC%A7%80%EC%8B%9D.md)
  - 가상화란? 서버 가상화의 특징, 가상화의 장점 
- [하이퍼바이저란 무엇인가?](https://github.com/chanW-pack/virtualization/blob/main/Week%201/1_1.a%20%ED%95%98%EC%9D%B4%ED%8D%BC%EB%B0%94%EC%9D%B4%EC%A0%80%EB%9E%80%20%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80.md) 
  - 하이퍼바이저 개념, 하이퍼바이저 두가지 방식, 컨테이너 가상화
- [전가상화와 반가상화](https://github.com/chanW-pack/virtualization/blob/main/Week%201/1_1.b%20%EC%A0%84%EA%B0%80%EC%83%81%ED%99%94%EC%99%80%20%EB%B0%98%EA%B0%80%EC%83%81%ED%99%94.md) 
  - CPU의 인스트럭션 실행 (링(RIng) 구조), 반가상화 (Paravitulization), 전가상화 (Full Virtualization)
- [VMware vSphere 개요](https://github.com/chanW-pack/virtualization/blob/main/Week%201/1_2%20VMware%20vSphere%20%EA%B0%9C%EC%9A%94.md) 
  - VMware vSphere 개념, VMware vSphere 제품 패키지 종류
- [VMware vSphere 가상화 기초 지식](https://github.com/chanW-pack/virtualization/blob/main/Week%201/1_3%20VMware%20vSphere%20%EA%B0%80%EC%83%81%ED%99%94%20%EA%B8%B0%EC%B4%88%20%EC%A7%80%EC%8B%9D.md) 
  - vSphere CPU 가상화 동작의 개요, vSphere 메모리 가상화 기술 개요, 스토리지 가상화의 핵심 기술
  - VMware에서 지원하는 전송 방식, VMware의 (논리) 스토리지 가상화 방식, 네트워크 가상화의 핵심 기술
  - vSphere 가상 네트워크 스위치의 특징

## Week 2

- [VMware vSphere 7.0 설치](https://github.com/chanW-pack/virtualization/blob/main/Week%202/2_1%20VMware%20vSphere%207.0%20%EC%84%A4%EC%B9%98.md)
- [VMware vSphere 7.0 설치_2](https://github.com/chanW-pack/virtualization/blob/main/Week%202/2_2%20VMware%20vSphere%207.0%20%EC%84%A4%EC%B9%98%202.md) 

- [VMware vCenter 7.0 설치](https://github.com/chanW-pack/virtualization/blob/main/Week%202/2_3%20VMware%20vCenter%207.0%20%EC%84%A4%EC%B9%98.md)
- [VMware vCenter 7.0 실행,접속](https://github.com/chanW-pack/virtualization/blob/main/Week%202/2_4%20VMware%20vCenter%207.0%20%EC%8B%A4%ED%96%89%2C%EC%A0%91%EC%86%8D.md) 

- [Ubuntu 가상 서버 설치](https://github.com/chanW-pack/virtualization/blob/main/Week%202/2_5%20Ubuntu%20%EA%B0%80%EC%83%81%20%EC%84%9C%EB%B2%84%20%EC%84%A4%EC%B9%98.md)
- [vSphere, ESXi, vCenter 개념 및 차이점](https://github.com/chanW-pack/virtualization/blob/main/Week%202/2_6%20vSphere%2C%20ESXi%2C%20vCenter%20%EA%B0%9C%EB%85%90%20%EB%B0%8F%20%EC%B0%A8%EC%9D%B4%EC%A0%90.md)
- [vSphere 7.0 가상 스위치 생성 (vSwitch 생성) + 물리적 어댑터 추가](https://github.com/chanW-pack/virtualization/blob/main/Week%202/2_7%20vSphere%207.0%20%EA%B0%80%EC%83%81%20%EC%8A%A4%EC%9C%84%EC%B9%98%20%EC%83%9D%EC%84%B1%20(vSwitch%20%EC%83%9D%EC%84%B1)%20%2B%20%EB%AC%BC%EB%A6%AC%EC%A0%81%20%EC%96%B4%EB%8C%91%ED%84%B0%20%EC%B6%94%EA%B0%80.md) 

- [ESXi 자동시작 기능, 사용자와 역할 생성](https://github.com/chanW-pack/virtualization/blob/main/Week%202/ESXi%20%EC%9E%90%EB%8F%99%EC%8B%9C%EC%9E%91%20%EA%B8%B0%EB%8A%A5%2C%20%EC%82%AC%EC%9A%A9%EC%9E%90%EC%99%80%20%EC%97%AD%ED%95%A0%20%EC%83%9D%EC%84%B1.md)
- [ESXi 사용자 지정 포트 열기 + 외부 접속을 위한 콘솔 포트 변경](https://github.com/chanW-pack/virtualization/blob/main/Week%202/ESXi%20%EC%82%AC%EC%9A%A9%EC%9E%90%20%EC%A7%80%EC%A0%95%20%ED%8F%AC%ED%8A%B8%20%EC%97%B4%EA%B8%B0%20%2B%20%EC%99%B8%EB%B6%80%20%EC%A0%91%EC%86%8D%EC%9D%84%20%EC%9C%84%ED%95%9C%20%EC%BD%98%EC%86%94%20%ED%8F%AC%ED%8A%B8%20%EB%B3%80%EA%B2%BD.md)


