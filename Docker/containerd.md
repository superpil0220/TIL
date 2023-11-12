* Docker는 기본적으로 CPU, memory, disk, I/O, network등 포함해서 컨테이너라는 하나의 그룹으로 묶어서 관리
* Docker Engine의 Monolithic한 구조를 나누는 작업을 시작
* 초기 Docker를 개발하면서 하나의 완성된 컨테이너 사용자경험을 만드는 것에 집중하다보니 Docker Engine이라는 하나의 패키지에 API, CLI, 네트워크, 스토리지 등 여러 기능들을 모두 담게 되었음
* Docker에 의존하고 있던 Kubernetes에서는 Docker 버전이 새로 나올때마다 Kubernetes가 크게 영향을 받는 일들이 생김
* Docker를 중심으로 구글 등 컨테이너 기술에 관심있는 여러 집단들이 한데 모여 Open Container Initiative, 이하 OCI라는 프로젝트를 시작하여 컨테이너에 관한 표준을 정하는 일들을 시작
* Docker에서는 OCI 표준을 준수하는 containerd라는 Container Runtime을 만듬
* Kubernetes에서는 OCI 표준을 준수하는 이미지들을 실행할 수 있는 Container Runtime Interface, 이하 CRI 스펙을 버전 1.5부터 제공
* Docker 버전과 무관하게 OCI 표준을 준수하기만 하면 어떤 컨테이너 이미지도 Kubernetes에서 실행가능한 환경이 됨
* Red Hat, Intel, SUSE, Hyper, IBM 쪽에서도 OCI 표준에 따라 Kubernetes 전용 Container Runtime을 만들었는데 이것이 CRI-O 만듬
* containerd와 CRI-O 이 두가지 Container Runtime이 현재 가장 널리 사용
* containerd는 Docker Engine에 기본으로 탑재되어 있어서 지금도 Docker를 사용한다면 내부적으로 사용되는 Container Runtime은 containerd 를 사용
* docker build` 커맨드로 생성되는 이미지들 역시 OCI Image Spec을 준수하기 때문에 별도의 작업없이 containerd로 실행가능
* containerd로의 전환을 통해 Pod은 더 빨리 시작되고, CPU와 메모리의 사용량은 더 줄었음
* 2021년 하반기 출시예정인 kubernetes 1.23과 함께 Container Runtime으로써의 Docker의 지원이 중단

# Reference
1. https://kr.linkedin.com/pulse/containerd는-무엇이고-왜-중요할까-sean-lee
