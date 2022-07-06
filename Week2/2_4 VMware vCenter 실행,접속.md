---

## vCenter Server 접속

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2036.png)

> ESXi 접속 후 가상 시스템에 생성되어있는 Center Server 접속
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2037.png)

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2038.png)

> 생성한 SSO 도메인으로 접속한다.
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2039.png)

> vCenter 접속 완료된 모습
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2040.png)

> 새 데이터 센터 생성을 진행한다.
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2041.png)

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2042.png)

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2043.png)

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2044.png)

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2045.png)

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2046.png)

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2047.png)

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2048.png)

> ESXi 호스트 추가 완료
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2049.png)

> ESXi_2 호스트도 추가 완료
> 

## *!!*

# vCenter SSO 도메인을 기본값으로 하지 않았다면?

## *!!*

SSO 도메인 설정 시 기본값 (vshpere.local) 이 아닌 다른값으로 지정한 경우

(본인은 cw.local로 지정하여 접속을 시도하였으나 **접속 불가**한 ****문제 발생함.)

원인 : 원래 처음 접속은 기본값 ( administrator@vsphere.local ) 로 접속을 하는게 맞다!!

접속 한 뒤 사용자들을 추가해주는것이 정석

그러나 다른 도메인으로 지정한 경우에는 그 도메인으로도 접속이 불가하다.

<aside>
💡 그 경우 administrator @ mydomain 으로 로그인하면 진행이 가능해진다.

</aside>

(본인은 이 경우를 몰라 재설정을 위해 다시 설치하였다...)

---

## Ubuntu 가상 서버 설치

[Ubuntu 가상 서버 설치](https://www.notion.so/Ubuntu-b6dd2aaa61ef46c79670edd4259d3343)

---
