마이크로서비스 아키텍처를 구성하는 서비스들은 각각 별개의 네트워크 위치 정보(IP, Port)를 갖습니다. 이 서비스들의 위치 정보는 클라우드 같은 환경에서 동적으로 바뀔 수 있고, 예기치 못한 장애로 인해 특정 네트워크 위치 정보의 서비스는 이용이 불가능할 수도 있습니다.

따라서, 이런 분산 시스템에서는 서비스들의 네트워크 위치 정보를 관리하고 가용 상태를 확인해줄 수 있는 기능이 필요로 한데, 이때 해결책으로 제시될 수 있는 디자인 패턴이 서비스 디스커버리입니다.

서비스 디스커버리는 서비스의 네트워크 위치 정보와 서비스의 가용 상태를 관리할 수 있는 서비스 레지스트리를 두고, 클라이언트가 서비스 레지스트리에게 가용 상태에 있는 서비스의 네트워크 위치 정보를 질의하게 함으로써 구현할 수 있습니다.

이러한 서비스 디스커버리는 크게 클라이언트 사이드 디스커버리와 서버 사이드 디스커버리로 구현방식이 나눠집니다. 클라이언트 사이드 디스커버리는 클라이언트가 직접 서비스 레지스트리에 질의하는 방식으로 나눠집니다. 클라이언트 사이드 디스커버리는 클라이언트가 직접 서비스 레지스트리에 질의하는 방식이며, 서버 사이드 디스커버리는 클라이언트와 서버 레지스트리 사이에 로드 밸런서를 위치시키는 방식으로, 로드 밸런서가 클라이언트 대신 서비스 레지스트리에 질의하여 서비스를 호출하는 방식입니다.
