

## VMware vCenter Server 7.0 설치

![Untitled 24](https://user-images.githubusercontent.com/84123877/177449105-abe677ab-68aa-455e-a5ac-fd35c2373e2e.png)

> VMware vCenter server ISO를 드라이브에 삽입한다.
> 

![Untitled 25](https://user-images.githubusercontent.com/84123877/177449109-739ad04e-6d63-4d0a-873e-0d04c97ac965.png)

> 설치를 진행한다. vcsa-ui-install > installer.exe
> 

![Untitled 26](https://user-images.githubusercontent.com/84123877/177449111-c3e69f3d-1090-4db2-831b-65350625af6a.png)

> 설치 / 업그레이드 / 마이그레이션 / 복원
> 

![Untitled 27](https://user-images.githubusercontent.com/84123877/177449113-4646a616-a67f-451f-8019-de94981c6e30.png)

> ESXi IP와 사용자이름, 암호를 추가한다.
> 

![Untitled 28](https://user-images.githubusercontent.com/84123877/177449115-d74fea80-22aa-4ba6-a2ed-49540208302c.png)

> vCenter Server에 대한 VM 설정을 지정한다.
> 

![Untitled 29](https://user-images.githubusercontent.com/84123877/177449117-9faf0d9f-e5f7-438c-bae1-549631c6fd59.png)

> 배포 크기를 설정한다. ESXi호스트의 서버 성능, 운영의도에 맞게 설정하면 된다.
> 

![Untitled 30](https://user-images.githubusercontent.com/84123877/177449118-a0ef2f15-a283-4ed5-8508-830f0d66231c.png)

> 데이터스토어를 선택한다. 씬 디스크 모드는 내가 할당할 500GB의 용량을 가지고 있지 않아도 개념적으로 500GB를 할당한 뒤에 내가 사용한 만큼 데이터스토어가 용량을 추가하는 모드다.
> 

![Untitled 31](https://user-images.githubusercontent.com/84123877/177449119-c4e93894-ebd6-448c-ba3b-6ff6b80fa003.png)

> vCenter Server의 접속시 사용될 IP 또는 FQDN 정보를 입력한다.
> 

![Untitled 32](https://user-images.githubusercontent.com/84123877/177449236-047fe849-d415-429c-87e8-119dc6560878.png)

> vCenter Server 서버 접속 시에 사용될 포트 번호 (기본값으로 두었다.)
> 

![11](https://user-images.githubusercontent.com/84123877/177449402-56dfbe85-76af-4a0a-8c09-24f5ba1239dd.png)

> 1단계 설치를 진행한다.
> 

![Untitled 33](https://user-images.githubusercontent.com/84123877/177449240-06e4f70f-c653-4e40-8320-c6eebc443e0e.png)

![Untitled 34](https://user-images.githubusercontent.com/84123877/177449244-96254cb9-6a73-4ff1-b3ad-7481043886ea.png)

> 2단계 vCenter Server 구성
> 

![Untitled 35](https://user-images.githubusercontent.com/84123877/177449245-6b176546-4e2d-40af-9237-3dea9753742a.png)

> vCenter Server 접속에 사용될 계정 정보를 입력한다.
> 

이후 2단계 설치 진행 완료

vCenter Server 접속 : https://192.168.111.37:443
