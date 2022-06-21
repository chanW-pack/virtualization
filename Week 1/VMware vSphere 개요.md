# VMware vSphere 개요

## VMware vSphere 란?

VMware 가 vSphere라는 이름을 붙이기 시작한 것은 버전 4부터이다.

vSphere로 이름을 바꾸면서 **vSphere를 클라우드 기반으로 만드는 클라우드 OS라고 정의**했다.

기존 VI3의 하이퍼바이저 + 관리 툴 만으로 VMware가 생각하는 비전을 이루기에 부족하다고 생각했는지 이를 지원하는 패키지 여러가지 제품을 묶어서 패키지 형식으로 만든 것이 바로 vSphere 이라고 생각하면 된다.

vSphere 6에 이르면서 호스트에서 지원하는 스펙 및 성능은 나날히 증가하여 현재는 vSphere의 핵심 하이퍼바이저인 ESXi 호스트의 메모리는 12TB까지 지원하며 CPU는 480개, 클러스터 구성 시 호스트는 64개까지 지원한다.

또한, 하나의 VM에서 지원하는 vCPU는 128개까지이며, VM당 최대 지원 가능한 메모리는 4TB까지이다.

하나의 ESXi 호스트에서 제공 가능한 IOPS (Input Output Per Second) 는 100만 IOPS를 이미 넘어섰다. 현재는 진정한 클라우드 OS라 불릴 정도로 Private Cloud 및 Hybird Cloud를 구축할 수 있는 기반 인프라를 제공하고 있다.

---

## VMware vSphere 제품 패키지 종류

클라우드를 지원하기 위해 가장 기본이 되는 제품 (Compute, Networking, Storage) 이 바로 vSphere 제품이다.

vSphere 제품은 기본적으로 3가지 에디션, 즉 Standardm Enterprise, Enterprise Plus 를 제공한다.

vSphere 6 는 CPU 단위로 라이센스를 책정하고 있다.

ESXi 가 탑재될 물리적인 서버의 CPU가 몇 개냐에 따라 라이센스 가격이 달라진다.

통상 x86서버는 CPU가 2개의 제품으로 구성되어 있다. (4개가 탑재되는 경우도 있기 때문에 이 경우에는 4 CPU 라이센스를 구매하면 된다.)

- 세 가지 에디션 구매시 **유지보수 지원을 위해 1년 단위인 SnS** (Support and Subsciption) 도 구매해야 한다.
- **라이센스 외에 vCenter Server의 라이센스도 별도 구매**해야한다.
- 분산 스위치, 네트워크 I/O 컨트롤 및 스토리지 I/O 컨트롤과 같은 고급 기능을 사용하려면 Enterprise Plus 에디션을 구매해야한다. (DRS, 및 DPM 기능까지만 사용하려면 Enterprise 에디션을 사용하면 된다.)
- 기본적인 기능만 필요하다면 Standard 에디션 구매 (소규모 SMB (Small Business) 기업의 경우 Essenital 에디션을 고려하는 것도 좋은 선택이 될 수 있다.)
- Essential 에디션은 ESXi 호스트를 3대까지만 확장할 수 있는 소규모 기업형 제품이다. 이 제품은 Hypervisor 인 ESXi Server만 설치가 가능한 버전이고, 고가용성을 위한 기능은 탑재되어 있지 않다. 사실상 기업형으로 사용하기에 적합한 솔루션은 아니다.
- (기업형으로 사용하기 위해서는 최소한 Essential Plus 제품을 구매해야한다.) 이는 ESXi 호스트를 최대 3대까지 클러스터링하여 사용할 수 있고, 기본적인 vMotion, VMware HA의 최소한의 필수 기능을 사용할 수 있다.
- 추후 Standard 라이센스로 업그레이드 할 수 있는 KIT도 제공하기 때문에 예산 문제로 도입을 망설인다면 향후에 확장해 나가도 문제 없다.

---