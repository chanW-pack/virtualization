---

## vCenter Server 접속

![Untitled 36](https://user-images.githubusercontent.com/84123877/177449246-758f3498-724e-46a8-85d8-5afdfb5b04b9.png)

> ESXi 접속 후 가상 시스템에 생성되어있는 Center Server 접속
> 

![Untitled 37](https://user-images.githubusercontent.com/84123877/177449247-5cfd7f11-fb9d-4c24-907b-5dfdb29d3f5b.png)

![Untitled 38](https://user-images.githubusercontent.com/84123877/177449249-5f2ed421-00a8-4963-ab7f-7ace95052106.png)

> 생성한 SSO 도메인으로 접속한다.
> 

![Untitled 39](https://user-images.githubusercontent.com/84123877/177449250-c913a847-8f36-410d-884c-e2cad1a26670.png)

> vCenter 접속 완료된 모습
> 

![Untitled 40](https://user-images.githubusercontent.com/84123877/177450081-d7fc00af-15e2-471e-81b0-2dcb79f397d3.png)

> 새 데이터 센터 생성을 진행한다.
> 

![Untitled 41](https://user-images.githubusercontent.com/84123877/177450083-50e1135c-4b55-42fc-a322-2a511baf8b46.png)

![Untitled 42](https://user-images.githubusercontent.com/84123877/177450084-af1c49b1-70a1-45d5-bebe-88d0bde46110.png)

![Untitled 43](https://user-images.githubusercontent.com/84123877/177450085-33b58e2f-65ec-43b6-9dee-6dd1df01f7a9.png)

![Untitled 44](https://user-images.githubusercontent.com/84123877/177450086-fcbe2553-682a-43cb-942c-23f1d4ac4b8c.png)

![Untitled 45](https://user-images.githubusercontent.com/84123877/177450087-6a912966-213d-4d81-bdc3-7284fa3c1975.png)

![Untitled 46](https://user-images.githubusercontent.com/84123877/177450088-36e044c9-6150-4598-9bdc-c13a01f25a58.png)

![Untitled 47](https://user-images.githubusercontent.com/84123877/177450090-c36e570a-d00b-4ae9-badb-b63154e6a787.png)

![Untitled 48](https://user-images.githubusercontent.com/84123877/177450248-cbb9cdac-2798-4cae-acec-9a8ce2ede370.png)

> ESXi 호스트 추가 완료
> 

![Untitled 49](https://user-images.githubusercontent.com/84123877/177450252-8d766173-4359-4207-a2f6-55f323aa2a37.png)

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
