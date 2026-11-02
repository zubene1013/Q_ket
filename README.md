# 🎟️ Q_Ket — Cloud Native Ticketing Platform

**AWS 기반 클라우드 네이티브 공연 예매 플랫폼**

Q_Ket은 사용자가 공연을 탐색하고, 좌석을 선택하고, 예매 및 결제를 진행할 수 있는 웹 서비스입니다.

AWS 기반 인프라에 애플리케이션을 배포하고, Terraform을 통한 인프라 관리와 Kubernetes 기반 컨테이너 오케스트레이션, GitOps 배포 체계를 적용한 팀 프로젝트입니다.

**프로젝트 기간:** 2026.03 ~ 2026.09 (교육 과정 기간, 실제 프로젝트 기간 확인 필요)  
**프로젝트 유형:** AWS·DevOps 교육 과정 팀 프로젝트  
**GitHub Organization:** https://github.com/qKet

---

## 1. 주요 기능

- **공연 탐색:** 공연 목록 및 상세 정보 조회
- **좌석 예매:** 공연 회차 선택 및 좌석 예약
- **대기열 관리:** Redis 기반 예매 대기열
- **결제:** Toss Payments 연동
- **사용자 인증:** 자체 로그인 및 OAuth2 소셜 로그인
- **관리자 기능:** 공연 및 사용자 관리

## 2. System Architecture

**AWS 인프라 아키텍처**

[전체 AWS 아키텍처 다이어그램 삽입 예정]

주요 인프라 구성은 다음과 같습니다.

- **Network:** VPC, Subnet, Security Group, NAT Gateway
- **Compute:** Amazon EKS, EC2
- **Database:** Amazon RDS, ElastiCache
- **Storage:** Amazon S3, ECR
- **Traffic:** Application Load Balancer, Route 53
- **Infrastructure as Code:** Terraform
- **Container Orchestration:** Kubernetes
- **GitOps:** Argo CD, Helm
- **Monitoring:** Prometheus, Grafana, Loki

## 3. Tech Stack

| 영역 | 기술 |
|---|---|
| Cloud | AWS (EKS, EC2, RDS, S3, ECR, SQS 등) |
| IaC | Terraform |
| Container | Docker, Kubernetes, Helm |
| CI/CD | GitHub Actions, Argo CD |
| Scaling | Karpenter, KEDA |
| Monitoring | Prometheus, Grafana, Loki |
| Backend | Java 21, Spring Boot, MyBatis |
| Frontend | Next.js, React, TypeScript |
| Database | MySQL, Redis |

## 4. Infrastructure & DevOps

### Infrastructure as Code

Terraform을 활용하여 AWS 네트워크, EKS 클러스터, 데이터 계층 및 Kubernetes Add-on을 코드로 관리했습니다.

인프라를 역할별 모듈로 구분하고, 리소스 간 의존성을 고려한 배포 순서를 구성했습니다.

### Kubernetes & Auto Scaling

Amazon EKS 기반의 Kubernetes 환경에 서비스를 배포했습니다.

- Karpenter를 활용한 노드 오토스케일링
- KEDA를 활용한 애플리케이션 Pod 오토스케일링
- AWS Load Balancer Controller를 통한 트래픽 라우팅

### CI/CD & GitOps

GitHub Actions와 Argo CD를 이용한 배포 파이프라인을 구성했습니다.

**배포 흐름**

1. GitHub에 소스코드 Push
2. GitHub Actions를 통한 빌드 및 테스트
3. Docker 이미지 빌드 후 Amazon ECR에 업로드
4. CD 저장소의 이미지 태그 갱신
5. Argo CD에서 변경사항 감지
6. Argo CD 수동 Sync를 통해 EKS에 배포

## 5. My Contributions

*개인 담당 범위 확인 후 구체화 예정*

| 영역 | 담당 업무 및 기여 |
|---|---|
| AWS Infrastructure | [직접 담당한 AWS 리소스 및 설계 내용] |
| Terraform | [작성하거나 개선한 모듈] |
| Kubernetes | [직접 구성한 배포 리소스 및 운영 작업] |
| CI/CD | [구축하거나 개선한 파이프라인] |
| Collaboration | [기술 선정 과정에서 제안한 대안과 의사결정] |

## 6. Troubleshooting

### CORS 문제로 인한 API 요청 실패

**문제 상황**

프론트엔드와 백엔드 연동 과정에서 CORS 문제로 API 요청이 정상적으로 처리되지 않았습니다.

**해결 과정**

- 브라우저 개발자 도구와 API 요청 흐름을 바탕으로 원인 조사
- 프론트엔드 요청과 백엔드 CORS 설정 점검
- 반복적인 테스트를 통해 문제 해결

**결과 및 배운 점**

8시간 이상 문제를 추적하여 API 통신 오류를 해결했습니다.

[정확한 원인, 변경한 설정 및 해결 결과 추가 예정]

### 추가 트러블슈팅

- [인프라 구축 과정에서 해결한 문제]
- [Kubernetes 또는 CI/CD 관련 문제]
- [성능 및 비용 최적화 경험]

## 7. Project Repositories

| Repository | Description |
|---|---|
| [Infra](https://github.com/qKet/Infra) | Terraform 기반 AWS 인프라 및 Kubernetes Add-on |
| [CD](https://github.com/qKet/CD) | Argo CD, Helm 기반 GitOps 배포 관리 |
| [Backend](https://github.com/qKet/backend) | Spring Boot 기반 API 서버 |
| [Frontend](https://github.com/qKet/frontend) | Next.js 기반 웹 애플리케이션 |
| [Docs](https://github.com/qKet/docs) | 프로젝트 설계 및 기술 문서 |
| [Wiki](https://github.com/qKet/CLAUDE_LLM_WIKI) | 아키텍처, 기술 의사결정 및 트러블슈팅 |

---

**Team Q_Ket** | AWS Cloud & DevOps Project

[GitHub Organization](https://github.com/qKet)
