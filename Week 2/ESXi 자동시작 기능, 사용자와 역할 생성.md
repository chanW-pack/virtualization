# ESXi 자동시작 기능, 사용자와 역할 생성

ESXi에서 기본적인 기능인 자동시작/자동종료 를 실습하여 작성하였다.

자동시작 기능은 서버 정전시나 예상치 못한 서버의 종료 등을 방지하기 위해 많이 사용된다.

말 그대로 ESXi가 부팅되면서 자동 시작할 가상머신을 선택적으로 지정한 뒤 부팅하는 것이다.

## 자동시작 설정하기

![Untitled](https://user-images.githubusercontent.com/84123877/177495071-eff083b0-ea5e-4293-8062-55e5dee6a279.png)

> ESXi 관리자 페이지 > 관리 > 시스템 > 자동시작
> 

여러개의 가상머신일 경우 우선순위에 따라 1번 부팅 > 30초 후 2번 부팅 > 30초 후 3번 부팅 순서로 진행한다.

![Untitled 1](https://user-images.githubusercontent.com/84123877/177495039-88bd5ec5-e35a-4c2b-8ee7-bdf4fceb96b5.png)

가상머신별로 사용 설정 후 시작순서를 조정해주면 된다.

아니면 가상시스템 페이지에서 가상머신 우클릭 후 설정도 가능하다.

![Untitled 2](https://user-images.githubusercontent.com/84123877/177495044-a08fb523-614f-4360-bb2b-eb7ee313fd15.png)

> 자동시작 설정에 대한 자세한 설명 (VW Tool 시작되면 즉시 계속 > 하트비트 대기)
> 

![Untitled 3](https://user-images.githubusercontent.com/84123877/177495047-e4a59cfb-2811-461c-8574-4b810fa13234.png)

---

## 사용자, 역할 생성 및 부여

VMware ESXi를 처음 설치한 이후에 root 계정이 기본적으로 생성되는데 

보안을 위해서 root 계정 접근을 차단하는 것이 좋다.

(root 계정으로 많은 brute force attack 이 들어온다.)

새로운 사용자를 생성하고 root 권한을 부여해보겠다.

![Untitled 4](https://user-images.githubusercontent.com/84123877/177495049-6c5ba1f2-3c95-4f2c-a871-910f9b7bcc33.png)

> 좌측의 관리 메뉴를 선택하고 보안 및 사용자 탭을 클릭한다.
> 

![Untitled 5](https://user-images.githubusercontent.com/84123877/177495051-1f249752-2f95-4c6e-aa25-c61f28b18dc8.png)

> 사용자 추가를 클릭하고 아래 빈칸에 정보를 입력한다. 정보를 입력하고 추가를 누르면 새 유저가 추가된 것을 볼 수 있다.
> 

![Untitled 6](https://user-images.githubusercontent.com/84123877/177495053-8909d49e-3cec-443a-b651-d9fe2e1e6765.png)

> 좌측 메뉴의 호스트들을 우클릭하면 창이 나타난다. 여기서 사용권한을 눌러준다.
> 

![Untitled 7](https://user-images.githubusercontent.com/84123877/177495056-cd8db08d-b5ed-461b-8738-d79f40e67554.png)

> 사용 권한 관리 창이 생성되는데, 사용자 추가를 클릭한다.
> 

![Untitled 8](https://user-images.githubusercontent.com/84123877/177495062-a2c070ff-8b5d-42d3-9da3-47205144d570.png)

![Untitled 9](https://user-images.githubusercontent.com/84123877/177495064-a646dead-d5eb-4840-88a1-86ee3ca89708.png)

> 방금 생성한 사용자를 입력하고 우측에서 관리자를 선택하면 자동으로 모든 권한이 부여된다. 이후 우측 하단 사용자 추가를 눌러 완료한다.
> 

![Untitled 10](https://user-images.githubusercontent.com/84123877/177495065-1528d706-810b-4b7a-89ec-a83b4f622255.png)

> root 권한을 사용 안 함으로 진행했다. root 유저의 역할을 권한 없음 으로 할당하였다
> 

![Untitled 11](https://user-images.githubusercontent.com/84123877/177495067-f009aeb7-0f49-449b-be81-d2bab474d0d6.png)

> 이제 root 로그인을 하면 거부 된다고 나오는 것을 확인할 수 있다.
> 

<aside>
💡 이렇게 보안을 위해 root 계정을 사용하지 않고 다른 계정을 만드는 것을 추천한다.

</aside>

---
