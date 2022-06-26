# VMware vSphere 7.0 설치

## VMware vSphere 테스트 환경 설치와 구성 및 사양

vSphere 테스트 환경 구현에 들어가기 앞서 기기의 제약사항이 있다.

1. Intel VT 가상화가 지원되는 최신 CPU
2. PC 및 노트북의 메모리가 16GB 이상일 것
3. 내장 디스크가 SSD 일 것 (Os는 SSD, 데이터는 SATA)

위 세가지 조건을 만족시키지 않는 PC에서는 본 환경을 테스트 할 수 없다.

(메모리는 가상 메모리 설정으로 16GB 이상인 것 처럼 속일 수 있다. 자세한 내용은 후술함)

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled.png)

> 대략적인 환경 구성도
> 

최소한의 실습이 가능한 환경으로 구성하였다. 각각의 사양은 다음과 같다.

- ESXi_1 = ESXi 호스트, vCPU: 2, MEM: 4GB, Disk: 40GB
- ESXi_2 = ESXi 호스트, vCPU: 2, MEM: 4GB, Disk: 40GB
- vCenter = 통합 관리 툴, vCPU: 4, MEM: 8GB, Disk 40GB

## VMware Workstation Pro 16 평가판 다운로드

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%201.png)

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%202.png)

> VMware Workstation 16 pro 다운로드 및 설치
> 

본인은 리눅스 학습으로 무료 기간을 소진하여 vmware 가상서버 설치 용도로만 사용하였다.

(ESXi server는 Pro로만 가능하기 때문. 실행은 VMware로도 문제 없다.)

---

## VMware ESXi 설치

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%203.png)

> vSphere, vCenter 등 ISO 파일들
> 

공식 홈페이지를 통해 ISO 파일들을 준비한다.

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%204.png)

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%205.png)

> OS는 미적용인 상태로 ESXi 가상머신을 생성했다.
> 

하이퍼바이저라고 부르며, 이는 가상화 환경을 구축하기 위해 물리적인 서버 위에 설치되는 최소한의 기능만을 탑재한 OS 라고 볼 수 있다. 

![캡처.PNG](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/%EC%BA%A1%EC%B2%98.png)

> ESXi 가상머신 2개, vCenter가 될 Windows 가상머신 1개 생성
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%206.png)

> CD/DVD 에 ESXi ISO 파일을 넣어 주고 실행한다.
> 

ESXi installer 가 실행되면서 설치가 자동으로 진행된다.

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%207.png)

이 화면에서는 PC의 사양을 볼 수 있고 파일을 자동으로 로드한다.

위 사양에서 RAM을 12.1GB 할당한 것을 볼 수 있다.

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%208.png)

> Enter를 눌러서 설치를 진행한다.
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%209.png)

> F11를 눌러서 라이센스를 동의하고 계속 진행한다.
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2010.png)

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2011.png)

> 스캐닝을 진행하고 난 후 설치할 저장소를 선택한다. 현재는 하나밖에 없으므로 Enter로 넘어간다.
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2012.png)

> 키보드 레이아웃 설정창이다. 한글은 없으므로 기본값으로 선택하고 넘어간다.
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2013.png)

> root 계정의 패스워드 설정이다. 최소 7자 이상이 되어야 한다.
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2014.png)

> F11를 눌러서 설치를 계속한다. 설치중에는 기다려주면 된다.
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2015.png)

> 설치가 완료되었다. Enter를 눌러서 재부팅을 진행한다.
> 

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

## VMware vCenter Server 7.0 설치

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2024.png)

> VMware vCenter server ISO를 드라이브에 삽입한다.
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2025.png)

> 설치를 진행한다. vcsa-ui-install > installer.exe
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2026.png)

> 설치 / 업그레이드 / 마이그레이션 / 복원
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2027.png)

> ESXi IP와 사용자이름, 암호를 추가한다.
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2028.png)

> vCenter Server에 대한 VM 설정을 지정한다.
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2029.png)

> 배포 크기를 설정한다. ESXi호스트의 서버 성능, 운영의도에 맞게 설정하면 된다.
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2030.png)

> 데이터스토어를 선택한다. 씬 디스크 모드는 내가 할당할 500GB의 용량을 가지고 있지 않아도 개념적으로 500GB를 할당한 뒤에 내가 사용한 만큼 데이터스토어가 용량을 추가하는 모드다.
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2031.png)

> vCenter Server의 접속시 사용될 IP 또는 FQDN 정보를 입력한다.
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2032.png)

> vCenter Server 서버 접속 시에 사용될 포트 번호 (기본값으로 두었다.)
> 

![11.PNG](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/11.png)

> 1단계 설치를 진행한다.
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2033.png)

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2034.png)

> 2단계 vCenter Server 구성
> 

![Untitled](VMware%20vSphere%207%200%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20241bfdc0e48d46bd8f5be2899f60c334/Untitled%2035.png)

> vCenter Server 접속에 사용될 계정 정보를 입력한다.
> 

이후 2단계 설치 진행 완료

vCenter Server 접속 : https://192.168.111.37:443

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