# vSphere 7.0 가상 스위치 생성 (vSwitch 생성) + 물리적 어뎁터 추가

## 가상 스위치 및 포트의 종류들

vSphere에는 두 가지 타입의 가상 스위치가 있다. 하나는 표준(standard), 하나는 분산(distributed) 스위치로, 기본적인 기능은 동일하나 작동하는 방식이 다르다.

또한 VM들과 ESXi 호스트들을 네트워크에 연결하기 위해서는, 가상 스위치가 특정 타입의 연결 및 포트를 사용할 필요가 있다.

가상 포트의 종류로는 세 가지, 즉 VM 포트, VMkernel 포트, Uplink 포트가 있다.

- VM Ports (그룹) : VM들을 가상 네트워크에 연결한다.
- VMkernel 포트 : ESXi 하이퍼바이저(VMkernel)가 ESXi 시스템 트래픽을 관리할 때 사용한다.
- Uplink 포트 (그룹) : 가상 네트워크를 물리 네트워크에 연결한다. 각 업링크 포트는 ESXi 호스트의 물리 네트워크 어댑터와 하나씩 연결된다.

![Untitled](https://user-images.githubusercontent.com/84123877/177473045-ca12912c-69f7-4c82-8928-134cc0308a50.png)

> 가상 스위치와 가상 포트의 종류들
> 

---

## 가상 스위치, 물리적 어뎁터 추가

VMware ESXi 호스트를 설치하고 네트워크 설정을 하게 되면, 기본적으로 물리적 어뎁터 (=랜카드) g하나를 가상 스위치 vSwitch0 으로 설정하게 된다.

1. Management Network : ESXi HOST를 접속하게 되는 IP가 들어간다.
2. VM Network : 가상서버(VM)을 설치하게 되면, 이 Network에 표시된다.
3. 그 외 vMotion 용 네트워크도 일반적으로 vSwitch0으로 구성된다.

![Untitled 1](https://user-images.githubusercontent.com/84123877/177473025-39c766b8-b4f8-49e1-90dd-ec99318d8f4b.png)

그렇다면 다른 물리적 어댑터 (=랜카드)가 가상 스위치 vSwitch0와 다른 네트워크에 연결되어 있다면, 새로운 가상 스위치를 만들고 그 네트워크를 사용하는 가상 머신을 생성할 수 있다.

![Untitled 2](https://user-images.githubusercontent.com/84123877/177473030-30424dde-69ce-447f-ab20-d7fb76815b2a.png)

> ESXi 서버에 물리적인 네트워크 어댑터를 추가해주었다.
> 

![Untitled 3](https://user-images.githubusercontent.com/84123877/177473032-3a529739-45b3-4f24-872b-bd4ea0e577c5.png)

> 가상 스위치 맨 왼쪽 “호스트 네트워킹 추가” 버튼을 누르고, 맨 아래 “표준 스위치용 가상 시스템 포트 그룹” 을 선택한다.
> 

![Untitled 4](https://user-images.githubusercontent.com/84123877/177473035-5e8719c8-8175-4c77-ac79-dd1e1f468966.png)

> 새 표준 스위치를 선택한다.
> 

![Untitled 5](https://user-images.githubusercontent.com/84123877/177473036-b5a2388d-3e4f-48cd-8914-9f9e4c64c9eb.png)

> 할당된 어댑터 + 버튼을 눌러서 활성 어댑터를 추가한다. 확인을 누르면 어댑터 정보와 연결된 네트워크 대역을 표시해 준다. 다음을 클릭한다.
> 

![Untitled 6](https://user-images.githubusercontent.com/84123877/177473038-98ce74e0-a961-4f8b-a4b9-d983174edc4b.png)

> 네트워크 레이블을 입력한다. (네이밍 룰은 없다. 관리자가 임의로 입력한다.) 설정을 검토하고 완료버튼을 누른다.
> 

![Untitled 7](https://user-images.githubusercontent.com/84123877/177473041-09ea53f0-2dda-4e4b-b906-c1a71f150b42.png)

> 가상 스위치 vSwitch1 이 추가되었다.
> 

![Untitled 8](https://user-images.githubusercontent.com/84123877/177473042-ccdb2b2b-0191-432b-af66-f4c99dfae0af.png)

![Untitled 9](https://user-images.githubusercontent.com/84123877/177473044-b6d06cd7-29a9-45b3-a9e2-daa40205c9d6.png)

> 가상 머신의 네트워크 어댑터를 VM Network에서 새로 생성한 네트워크로 변경이 가능하다.

---
