![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2016.png)

> 재부팅이 완료되었다. F2를 눌러 시스템 편집으로 이동해 IP를 설정해 주겠다.
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2017.png)

> 설정한 root 계정의 패스워드를 입력하여 접속한다.
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2018.png)

> Configure Network로 접속하여 IPv4, DNS Configuration을 편집하겠다.
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2019.png)

> IPv4는 ESXi_1 은 192.168.111.37, ESXi_2 은 192.168.111.38 로 설정하겠다.
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2020.png)

> DNS Server도 맞춰서 진행한다.
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2021.png)

> 이후 ESC > Y 로 변경사항을 저장한 뒤, 테스트하겠다.
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2022.png)

> 설정한 아이피로 접속 테스트를 확인했다.
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2023.png)

> 로그인 후 라이센스를 호스트/관리/라이센싱에 들어가서 할당할 수 있다. (본인은 체험판)
> 

같은 방법으로 ESXi 서버를 하나 더 추가한다. (192.168.111.37)

그래서 총 2개의 ESXi 가 생성되었다.

(192.168.111.37) ESXi 1

(192.168.111.38) ESXi 2

다음은 vCenter를 생성하겠다. vCenter는 다수의 ESXi를  하나로 통합하여 관리할 수 있게 해주는 기능을 가지고 있다.  

운영자 입장에서도 vCenter를 활용하여 여러 ESXi를 보다 쉽게 제어할 수 있다.

---
