# vSphere, ESXi, vCenter 개념 및 차이점

VMware 가상화 플랫폼을 사용하고 있는 사람이라면 한번쯤은 제품군과 관련된 용어들이 헷갈렸을 수도 있을 수도 있을 것 같다.

이번에는 각 용어에 대한 정확한 개념에 대해 알아보고자 한다.

## 전체적인 구성

![Untitled](vSphere,%20ESXi,%20vCenter%20%E1%84%80%E1%85%A2%E1%84%82%E1%85%A7%E1%86%B7%20%E1%84%86%E1%85%B5%E1%86%BE%20%E1%84%8E%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%8C%E1%85%A5%E1%86%B7%20a4d431c70b76474ba603b3cb9692577e/Untitled.png)

## ESXi

![Untitled](vSphere,%20ESXi,%20vCenter%20%E1%84%80%E1%85%A2%E1%84%82%E1%85%A7%E1%86%B7%20%E1%84%86%E1%85%B5%E1%86%BE%20%E1%84%8E%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%8C%E1%85%A5%E1%86%B7%20a4d431c70b76474ba603b3cb9692577e/Untitled%201.png)

**ESXi는 하이퍼바이저 (Hypervisor) 이며**, 가상화 환경에서 가장 중요한 역할을 맡고 있다고 볼 수 있다. 

하이퍼바이저는 가상화 환경을 구축하기 위해 물리적인 서버 위에 설치되는 최소한의 기능만을 탑재한 OS라고 볼 수있다.

우리가 생각하는 **VM 혹은 게스트 OS는 모두 하이퍼바이저 역할을 담당하는 OS가 설치된 ESXi 서버 위에 설치**된다.

ESXi 서버에 VM 생성, 수정, 삭제 및 관리를 하기 위한 엑세스 방법으로는 vSphere Client를 이용한다.

vSphere Client는 총 3가지로 나뉘어지는데,

1. vSphere Client : 별도의 소프트웨어 설치 없이 HTML을 이용한 웹 동작 방식
2. vSphere Web Client : 별도의 소프트웨어 설치 없이 Adobe를 이용한 웹 동작 방식
3. vSphere Windows Cient Program : Windows에 특정 소프트웨어를 설치한 후 프로그램을 통해 접근하는 동작 방식. ESXi 6.0 이하의 버전에서만 사용할 수 있다.

VMware에서도 별도의 소프트웨어 설치가 필요 없으며, 직관적인 UI를 통해 보다 관리가 쉬운 웹 동작 방식을 권장하고 있다.

---

## vCenter

![Untitled](vSphere,%20ESXi,%20vCenter%20%E1%84%80%E1%85%A2%E1%84%82%E1%85%A7%E1%86%B7%20%E1%84%86%E1%85%B5%E1%86%BE%20%E1%84%8E%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%8C%E1%85%A5%E1%86%B7%20a4d431c70b76474ba603b3cb9692577e/Untitled%202.png)

가상화 환경 구축에 있어서 핵심 중 핵심이다. **가상화 구축도 결국엔 물리적인 서버가 있어야만 완성할 수 있다.** 

우리가 생성했다 지웠다 하는 VM도 사실은 앞서 설명한 ESXi라는 하이퍼바이저 OS를 물리적인 서버에 설치하고 그 위에 게스트 OS를 생성 한 것처럼 실제로 물리적인 서버가 존재하게 되는데, 이런 **다수의 ESXi (물리적인 서버)를 하나로 통합하여 관리할 수 있게 해주는 것이 바로 vCenter이다.**

<aside>
💡 운영자 입장에서도 vCenter를 활용하여 여러 ESXi를 보다 쉽게 제어할 수 있다.

</aside>

그 외에도 vCenter가 설치된 환경에서만 제공하는 특별한 기능들도 있다.

1. vSphere vMotion
2. vSphere HA (High Availability)
3. vSphere FT (Fault Tolerance)
4. vSphere DRS (Distributed Resources Scheduler)
5. vSphere SDRS (Stroage Disributed Resource Scheduler)
6. Clone & Template
7. vShpere Distributed Switch 관리
8. 글로벌 패치 관리

위 기능들은 VMware 사용자라면 알아야 할 중요한 역할이라고 하니 다음 페이지에서 개념에 대해 상세하게 다뤄보도록 하겠다.

(페이지링크)

---

## vSphere

**vShpere는 소프트웨어를 모두 포함한 패키지**이다. VMware에서 ESXi, vCenter는 마이크로소프트에서 Excel, Word, PowerPoint 같은 제품군 개념이고, vSphere는 마이크로소프트 Office와 같은 모든 제품을 포괄하고 있는 패키지 개념이라고 이해하면 편하다.

그래서 실제로는 vSphere를 설치한다는 말보다는 vShpere에 포함된 ESXi 나 vCenter를 설치한다라는 말이 보다 명확한 의미를 담고 있다.

마치 “ 내 컴퓨터에 Office 설치해줘 “ 라는 말을 이해하는 것보다 (?? : 엑셀? 워드? 뭘 설치하란거지? ) “ 내 컴퓨터에 MS 엑셀이랑 파워포인트 좀 설치해줘 “ 라는 말이 이해하는데 더 정확한 목적을 알 수 있는 것과 같다. 

---
