## VMware vShpere 7.0 설치 2

![Untitled 16](https://user-images.githubusercontent.com/84123877/177447789-426dd724-3edd-4200-bf42-6f19a40a78e6.png)

> 재부팅이 완료되었다. F2를 눌러 시스템 편집으로 이동해 IP를 설정해 주겠다.
> 

![Untitled 17](https://user-images.githubusercontent.com/84123877/177447792-60d59dbd-4247-44f9-98b7-99cde8fc0e0e.png)

> 설정한 root 계정의 패스워드를 입력하여 접속한다.
> 

![Untitled 18](https://user-images.githubusercontent.com/84123877/177447794-3e5d07b6-1ecf-40db-8076-eca61b0184ac.png)

> Configure Network로 접속하여 IPv4, DNS Configuration을 편집하겠다.
> 

![Untitled 19](https://user-images.githubusercontent.com/84123877/177447795-94883554-d87d-4ded-801a-aac8f39c5d15.png)

> IPv4는 ESXi_1 은 192.168.111.37, ESXi_2 은 192.168.111.38 로 설정하겠다.
> 

![Untitled 20](https://user-images.githubusercontent.com/84123877/177447797-c4833e45-af5b-4ebc-8577-a324e9a1a4c5.png)

> DNS Server도 맞춰서 진행한다.
> 

![Untitled 21](https://user-images.githubusercontent.com/84123877/177447798-8f26f231-03c7-4622-887d-35b9023fcec1.png)

> 이후 ESC > Y 로 변경사항을 저장한 뒤, 테스트하겠다.
> 

![Untitled 22](https://user-images.githubusercontent.com/84123877/177447799-39a3ae66-3085-4549-a674-028651d1bec7.png)

> 설정한 아이피로 접속 테스트를 확인했다.
> 

![Untitled 23](https://user-images.githubusercontent.com/84123877/177447802-be42cca4-337e-4ad1-a86d-80168f09a947.png)

> 로그인 후 라이센스를 호스트/관리/라이센싱에 들어가서 할당할 수 있다. (본인은 체험판)
> 

같은 방법으로 ESXi 서버를 하나 더 추가한다. (192.168.111.37)

그래서 총 2개의 ESXi 가 생성되었다.

(192.168.111.37) ESXi 1

(192.168.111.38) ESXi 2

다음은 vCenter를 생성하겠다. vCenter는 다수의 ESXi를  하나로 통합하여 관리할 수 있게 해주는 기능을 가지고 있다.  

운영자 입장에서도 vCenter를 활용하여 여러 ESXi를 보다 쉽게 제어할 수 있다.

---
