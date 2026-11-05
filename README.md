# 🎟️ Q_Ket — Cloud Native Ticketing Platform

**AWS 기반 클라우드 공연 예매 플랫폼**

Q_Ket은 사용자가 공연을 탐색하고, 좌석을 선택하고, 예매 및 결제를 진행할 수 있는 웹 서비스입니다.

AWS 기반 인프라에 애플리케이션을 배포하고, Terraform을 통한 인프라 관리와 Kubernetes 기반 컨테이너 오케스트레이션, GitOps 배포 체계를 적용한 팀 프로젝트입니다.

**프로젝트 기간:** 2026.07 ~ 2026.09

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

### Logging & Monitoring
- Loki·Promtail 기반 서비스 로그 수집 및 Grafana 통합 조회 환경 구축
- Grafana 대시보드에서 CPU·메모리 사용량 등 자원 상태 확인

### AWS Infrastructure & Terraform
- Terraform을 활용한 AWS 인프라 구성 및 관리에 참여
- VPC, Subnet, Security Group 등 네트워크 리소스 구성
- Amazon EKS 기반 Kubernetes 클러스터 구축 및 인프라 모듈 관리

### Kubernetes & Auto Scaling
- Kubernetes 기반 애플리케이션 배포 환경 구성
- Cluster Autoscaler에서 Karpenter로 전환하는 작업에 참여
- 컨트롤러 배치를 막는 Helm 설정을 팀원과 함께 검토·수정
- KEDA를 활용한 Pod 오토스케일링 설정

### CI/CD & GitOps
- GitHub Actions 기반 CI 파이프라인 구성
- Docker 이미지 빌드 및 Amazon ECR 연동
- Helm과 Argo CD를 활용한 GitOps 배포 환경 구성

### Collaboration & Technical Decisions
- 인프라 구성 및 서비스 배포 과정에서 발생한 문제를 팀원들과 공유하고 해결 방안 논의
- 팀원들과 인프라 구성 및 기술 선정 방향 논의
  
## 6. Project Repositories

| Repository | Description |
|---|---|
| [Infra](https://github.com/qKet/Infra) | Terraform 기반 AWS 인프라 및 Kubernetes Add-on |
| [CD](https://github.com/qKet/CD) | Argo CD, Helm 기반 GitOps 배포 관리 |
| [Backend](https://github.com/qKet/backend) | Spring Boot 기반 API 서버 |
| [Frontend](https://github.com/qKet/frontend) | Next.js 기반 웹 애플리케이션 |
| [Docs](https://github.com/qKet/docs) | 프로젝트 설계 및 기술 문서 |

