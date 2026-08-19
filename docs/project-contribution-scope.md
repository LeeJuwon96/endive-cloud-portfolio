# 개인 기여 범위와 근거

## 확인 기준

- GitHub 계정: [`LeeJuwon96`](https://github.com/LeeJuwon96)
- Git 작성자: `LEE JU WON`, `LeeJuwon96`
- 확인 대상: 팀의 4개 저장소 `main` 브랜치에 반영된 커밋과 변경 파일
- 주의: 커밋 수에는 초기 설정·통합·보완 커밋이 포함될 수 있으므로 기능 개수나 기여율로 해석하지 않습니다.

## 개인 담당 범위

| 영역 | 직접 구현·개선한 내용 | 대표 저장소 |
|---|---|---|
| CI | 저장소별 Jenkinsfile, Multibranch 검증, 서비스 이미지 빌드·헬스체크·ECR Push | service, platform, infra, docs |
| CD/GitOps | 서비스 매니페스트 이전, Kustomize base·서울·도쿄 overlay, 태그 자동 갱신, Argo CD Application | service, platform |
| 모니터링 | 중앙 Prometheus·Grafana 구성, AWS remote_write, 리전 대시보드, 노드 이름 정규화 | platform, infra |
| 로깅·알림 | Alloy→Loki, 서울·도쿄 로그 대시보드, Prometheus 규칙, Alertmanager→Discord | platform, infra |
| DR 연동 | 모니터링·로깅·Repository Secret·앱 Secret·Application 복구 플레이북 | infra |
| 장애 해결 | CI 순환 방지, IP 표시 개선, Pod 네트워크 사전 검사, Ingress·초기화 복구 | service, platform, infra |

## 대표 커밋

### endive-service

- [`1ea7635`](https://github.com/ktcloud4-endive/endive-service/commit/1ea7635) — main 이미지 빌드 및 ECR Push
- [`fa398a3`](https://github.com/ktcloud4-endive/endive-service/commit/fa398a3) — 전체 브랜치 검증과 main 배포 분리
- [`39f9126`](https://github.com/ktcloud4-endive/endive-service/commit/39f9126) — GitOps 이미지 태그 갱신
- [`0b59fc5`](https://github.com/ktcloud4-endive/endive-service/commit/0b59fc5) — 서비스 매니페스트 저장소 이전
- [`6565c88`](https://github.com/ktcloud4-endive/endive-service/commit/6565c88) — 멀티 리전 Overlay
- [`56cd4be`](https://github.com/ktcloud4-endive/endive-service/commit/56cd4be) — 웹 Ingress와 초기화 복구

### endive-platform

- [`d5e1b0d`](https://github.com/ktcloud4-endive/endive-platform/commit/d5e1b0d) — Argo CD GitOps 배포 구성
- [`c50defb`](https://github.com/ktcloud4-endive/endive-platform/commit/c50defb) — 리전별 Argo CD Application
- [`4974637`](https://github.com/ktcloud4-endive/endive-platform/commit/4974637) — AWS Kubernetes 대시보드
- [`84f53da`](https://github.com/ktcloud4-endive/endive-platform/commit/84f53da) — 노드 이름 표시 개선
- [`d2cc763`](https://github.com/ktcloud4-endive/endive-platform/commit/d2cc763) — 서울·도쿄 로그 대시보드 분리
- [`a124d4c`](https://github.com/ktcloud4-endive/endive-platform/commit/a124d4c) — Alertmanager 규칙·알림 구성

### endive-infra

- [`edbdf93`](https://github.com/ktcloud4-endive/endive-infra/commit/edbdf93) — AWS 모니터링 복구
- [`fcbf611`](https://github.com/ktcloud4-endive/endive-infra/commit/fcbf611) — AWS 로깅 복구
- [`ce4937d`](https://github.com/ktcloud4-endive/endive-infra/commit/ce4937d) — Argo CD 저장소 인증 복구
- [`69d031b`](https://github.com/ktcloud4-endive/endive-infra/commit/69d031b) — 애플리케이션 Secret 복구
- [`2de1762`](https://github.com/ktcloud4-endive/endive-infra/commit/2de1762) — 리전별 Application 복구

### endive-docs

- [`4dc6110`](https://github.com/ktcloud4-endive/endive-docs/commit/4dc6110) — main 문서 검증
- [`d2a9106`](https://github.com/ktcloud4-endive/endive-docs/commit/d2a9106) — 전체 브랜치 문서 검증

## 팀 성과와 개인 기여의 구분

### 팀 프로젝트의 전체 결과

- OpenStack과 AWS를 연결한 하이브리드·멀티 리전 환경
- Terraform과 Ansible을 이용한 인프라·클러스터 자동 구성
- 서울 장애를 가정한 도쿄 리전 서비스 복구 시연
- Kubernetes 기반 행사 정보 서비스와 데이터베이스 복구

### 다른 팀원 담당으로 구분한 부분

- AWS 네트워크·EC2·ECR 복제를 포함한 Terraform 기반 인프라 생성
- Kubernetes 기본 클러스터와 데이터베이스 설치·백업·복구의 핵심 플레이북
- 행사 API, 프론트엔드, 데이터 수집기, 위험 분석 로직 등 애플리케이션 기능 개발

### 개인 포트폴리오에서 다루는 부분

- 위 팀 인프라 위에 구축한 CI/CD와 GitOps 배포 흐름
- OpenStack 중앙 관제와 AWS 클러스터의 메트릭·로그·알림 통합
- 리전 재구축 후 운영 구성을 되살리는 Ansible 구성요소와 장애 해결 과정
