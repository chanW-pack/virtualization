# VMware vSphere 7.0 설치

## VMware vSphere 테스트 환경 설치와 구성 및 사양

vSphere 테스트 환경 구현에 들어가기 앞서 기기의 제약사항이 있다.

1. Intel VT 가상화가 지원되는 최신 CPU
2. PC 및 노트북의 메모리가 16GB 이상일 것
3. 내장 디스크가 SSD 일 것 (Os는 SSD, 데이터는 SATA)

위 세가지 조건을 만족시키지 않는 PC에서는 본 환경을 테스트 할 수 없다.

(메모리는 가상 메모리 설정으로 16GB 이상인 것 처럼 속일 수 있다. 자세한 내용은 후술함)

![Untitled](https://user-images.githubusercontent.com/84123877/175814363-094c2903-15f6-4366-9198-e46879ff7059.png)

> 대략적인 환경 구성도
> 

최소한의 실습이 가능한 환경으로 구성하였다. 각각의 사양은 다음과 같다.

- ESXi_1 = ESXi 호스트, vCPU: 2, MEM: 4GB, Disk: 40GB
- ESXi_2 = ESXi 호스트, vCPU: 2, MEM: 4GB, Disk: 40GB
- vCenter = 통합 관리 툴, vCPU: 4, MEM: 8GB, Disk 40GB

## VMware Workstation Pro 16 평가판 다운로드

![Untitled 1](https://user-images.githubusercontent.com/84123877/175814365-e03f46d4-3c10-4315-acba-b4bc1b4a4583.png)

![Untitled 2](https://user-images.githubusercontent.com/84123877/175814388-8cacdab2-f209-4f14-9a3a-a35b6b22bfe4.png)

> VMware Workstation 16 pro 다운로드 및 설치
> 

본인은 리눅스 학습으로 무료 기간을 소진하여 vmware 가상서버 설치 용도로만 사용하였다.

(ESXi server는 Pro로만 가능하기 때문. 실행은 VMware로도 문제 없다.)

---

## VMware ESXi 설치

![Untitled 3](https://user-images.githubusercontent.com/84123877/175814392-87b268f4-b1d2-49b0-89f8-dd0b543d2e56.png)

> vSphere, vCenter 등 ISO 파일들
> 

공식 홈페이지를 통해 ISO 파일들을 준비한다.

![Untitled 4](https://user-images.githubusercontent.com/84123877/175814393-152d758b-c54d-49ea-b5c9-1ff83879c6d8.png)

![Untitled 5](https://user-images.githubusercontent.com/84123877/175814396-38a7b10d-63b4-4d1e-9630-4839f2571d9a.png)

> OS는 미적용인 상태로 ESXi 가상머신을 생성했다.
> 

하이퍼바이저라고 부르며, 이는 가상화 환경을 구축하기 위해 물리적인 서버 위에 설치되는 최소한의 기능만을 탑재한 OS 라고 볼 수 있다. 

![Untitled 6](https://user-images.githubusercontent.com/84123877/175814398-e78f6429-28cb-4635-90b8-6852a37bfcf4.png)

> ESXi 가상머신 2개, vCenter가 될 Windows 가상머신 1개 생성
> 

![Untitled 6](https://user-images.githubusercontent.com/84123877/177438138-a856da06-34fa-4f04-a68b-4e7e70534db0.png)

> CD/DVD 에 ESXi ISO 파일을 넣어 주고 실행한다.
> 

ESXi installer 가 실행되면서 설치가 자동으로 진행된다.

![Untitled 7](https://user-images.githubusercontent.com/84123877/177438133-ed5bfe27-a404-4e28-b936-6713370b53ed.png)

이 화면에서는 PC의 사양을 볼 수 있고 파일을 자동으로 로드한다.

위 사양에서 RAM을 12.1GB 할당한 것을 볼 수 있다.

![Untitled 8](https://user-images.githubusercontent.com/84123877/177438156-720701ce-118d-44ee-bc78-658cee233caf.png)

> Enter를 눌러서 설치를 진행한다.
> 

![Untitled 9](https://user-images.githubusercontent.com/84123877/177438159-d0dea14f-968f-4895-ad92-6461bd053ef2.png)

> F11를 눌러서 라이센스를 동의하고 계속 진행한다.
> 

![Untitled 10](https://user-images.githubusercontent.com/84123877/177438161-bcc09079-a461-44a8-a9f2-5175835023a5.png)

![Untitled 11](https://user-images.githubusercontent.com/84123877/177438164-1fd99ea6-1b6f-4a88-bc2c-f8fb6f967014.png)

> 스캐닝을 진행하고 난 후 설치할 저장소를 선택한다. 현재는 하나밖에 없으므로 Enter로 넘어간다.
> 

![Untitled 12](https://user-images.githubusercontent.com/84123877/177438166-7b58a462-c29e-47c0-999a-76792ee7aa53.png)

> 키보드 레이아웃 설정창이다. 한글은 없으므로 기본값으로 선택하고 넘어간다.
> 

![Untitled 13](https://user-images.githubusercontent.com/84123877/177438168-e970559d-19af-45da-95fd-5459357e0fcb.png)

> root 계정의 패스워드 설정이다. 최소 7자 이상이 되어야 한다.
> 

![Untitled 14](https://user-images.githubusercontent.com/84123877/177438171-1cb0b109-fe10-4019-ba78-b3910372e8fc.png)

> F11를 눌러서 설치를 계속한다. 설치중에는 기다려주면 된다.
> 

![Untitled 15](https://user-images.githubusercontent.com/84123877/177438173-c171af77-8b59-4e23-abea-cb1066364d88.png)

> 설치가 완료되었다. Enter를 눌러서 재부팅을 진행한다.
> 


