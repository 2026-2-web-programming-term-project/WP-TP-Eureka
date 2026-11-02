# WP-TP-Eureka

연구실 GPU 서버 자원 예약 및 실시간 모니터링 시스템의 서비스 등록·조회 기능을 담당할 Spring Cloud Netflix Eureka 저장소입니다.

[프로젝트 전체 소개](https://github.com/2026-2-web-programming-term-project/.github#readme)

## 담당 범위

- 서비스 인스턴스의 등록과 상태·주소 조회
- EC2 Auto Scaling에 따른 인스턴스 추가·종료 반영
- 서비스 간 호출에서 사용할 디스커버리 설정 관리

Eureka는 서비스 주소를 발견하기 위한 구성 요소이며, 사용자 업무 요청이 순서대로 통과하는 프록시가 아닙니다.

## 현재 상태

2026-11-02 기준 Spring Boot 초기 프로젝트와 기본 테스트 클래스가 추가되어 있습니다. Eureka Server·Client 등록·조회, peer 구성·컨테이너·HA 연동은 검증 예정입니다.

현재 초기 설정을 바탕으로 다른 서비스와의 Spring Boot·Spring Cloud 버전 정합성, 서비스 등록·조회와 인스턴스 종료 반영을 검증합니다.

## HA 설계 계획

Eureka를 유지하는 경우 단일 인스턴스 장애에 의존하지 않도록 다중 가용 영역의 peer 구성과 클라이언트의 복수 서버 주소를 설계합니다. 레지스트리 연결 장애·복구와 종료 인스턴스의 반영을 확인할 계획입니다.

내부 로드밸런서 등 AWS 측 서비스 발견 방식과의 역할 분담도 확정합니다. 공용 진입점, 서비스 발견, 요청 분산의 책임을 구분하여 설계합니다.

백엔드 제출 마감은 **2026-12-04 23:59 KST**입니다. 현재 운영 배포·HA 검증은 수행하지 않았습니다.

## 담당 WBS

[통합 WBS의 WP-TP-Eureka 작업](https://github.com/2026-2-web-programming-term-project/.github/blob/main/docs/WBS.md#wp-tp-eureka)에서 담당 범위를 관리합니다.

EU-01–03: 기본 설정·Server/Client 등록·peer·장애와 종료 반영

선행 관계·기간·완료 기준·상태는 통합 문서를 기준으로 갱신합니다. [공통 인프라](https://github.com/2026-2-web-programming-term-project/.github/blob/main/docs/WBS.md#infrastructure)와 [통합 검증](https://github.com/2026-2-web-programming-term-project/.github/blob/main/docs/WBS.md#integration)도 함께 확인합니다.

## 라이선스

[Apache License 2.0](LICENSE)
