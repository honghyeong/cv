# KR-CV

# 90도 성장 곡선 개발자, 홍석민입니다.

# 👋🏻 About Me

## Introduction

- 1년차 Server + Devops Engineer 홍석민입니다.
- Challenging한 태스크를 Computer Scientific 하게 해결하는 것에 푹 빠져있습니다.
- 끊임없는 성장을 위하여 1일 1커밋을 지속하고, Tech Blog를 운영하고 있습니다.
- 더 나은 코드를 위한 고민을 멈추지 않습니다.
  - Clean Code
  - TDD
  - Clean Architecture
- 음악과 봉사, 성장하기에 관심이 많습니다.

## 📞 Contact & Channel

- Email :
  - scarletgold0601@gmail.com
  - hongseoljin@korea.ac.kr
- Github : [https://github.com/honghyeong](https://github.com/honghyeong)
- Tech Blog : [https://5hongmin.tistory.com](https://5hongmin.tistory.com/)

# 🛠️ Skills

### `Programming Language`

- C++
- TypeScript
- Java
- Go
- Python

### `Backend`

- NodeJs, ExpressJS, NestJS
  - TypeORM
- Spring
- gRPC
- Postgres DB, MySQL

### `Devops`

- Docker
- AWS
  - EC2, ECS, RDS, Route 53, CloudWatch, SNS, Lambda, MSK, EventBridge, S3, ECR
- Git, Git Actions ( CI / CD)
- Pulumi
- Nx
- Locust

### `Frontend`

- HTML5, CSS3(SCSS)
- React
- NextJS

### `Collaboration`

- Slack
- Git

# Work Experience

## Corca

### AdTech bidding price 추론 시스템

- 하루에 최대 18500 /sec, 251 M/day의 요청, Docker 컨테이너 당 rps 6~700 를 처리해야하는 시스템
- MSA 아키텍처 설계
  - A/B Testing 가능
  - 하위 호환성 및 버전 관리
  - 장애 분리
- 안정적인 서버의 개발 및 운영
- 아키텍처의 우수성과 ML 리서칭 및 모델의 Continuous Learning
  - CPC, CPA, ROAS의 눈에 띄는 증가

### Dev

- 트래픽(RPS)가 높아짐에 따라 생긴 다양한 문제를 로컬에서 재현하고, Computer Scientific 하게 문제를 정의하고 해결
  - Go 으로 작성한 추론부 컴포넌트에서 Map 자료구조에 동시에 여러 write 요청 발생하여 `race condition` 발생 ⇒ SyncMap, Mutex 패키지를 이용하여 해결
  - HTTP POST request가 쌓여 HTTP Connection( TCP Hand-shaking) 이 증가함에 따라 `too many open files` 문제 발생 ⇒ http connection 재활용하도록하고, http connection에 요청 제한 시간을 부여하여 병목 현상을 해결
  - 추론부에 병목현상이 발생하여 CPU Utilization의 증가로 `scale out 이 과도하게 진행되는 문제` 발생
    - Go tracing tool : jaegar 를 이용하여 각 메소드별 처리시간을 트레이싱하고 HTTP Request 에서의 병목 현상을 파악 ⇒ TCP 에서 UDP으로 통신 프로토콜 바꾸는 것을 고려
    - DSP와 추론부 컴포넌트가 gRPC 통신하는 과정에서 `Network Latency에 의한 병목현상 발생`
      - docker0 bridge로 인한 네트워크 레이턴시를 고려하여, executable file로 변경하여 Docker Contaienr network로 인한 grpc latency를 감소시키는 아이디어 제안
      - 레이턴시의 눈에 띄는 감소 : Docker Container ( `12ms` ) ⇒ executable ( `3.3 ms` )
- 안정적인 서버 개발
  - 비딩 가격 추론부 개발
    - go routine을 이용한 throughput
  - 관리자 컴포넌트 개발
    - A/B Testing
    - 하위 호환성 버전 관리
  - TDD를 통한 명세를 기반으로 개발, 협업 : Unit, Integration, E2E Testing
  - 초당 2만개의 트래픽을 감당할 수 있고 컴포넌트 간 장애를 분리한 MSA 아키텍처 설계

### DevOps : 모니터링 시스템 구축 및 자동화 / 분산 부하 발생기 리서치

- TDD를 기반으로 개발하고, 장애를 분리한 아키텍처를 설계했더라도, 과도한 트래픽에 의해 AWS 환경에서 띄워진 컴포넌트들 어디서도 문제가 생길 수 있기때문에 `Slack 웹훅을 이용한 모니터링 시스템 구축`
  - ECS Task Exited Alerting ⇒ AWS EventBridge + Lambda 를 이용한 슬랙 알람
  - ECS Resource Alerting ⇒ AWS CloudWatch + AWS SNS + AWS Lambda를 이용한 슬랙 알람
  - 관리자 컴포넌트 내부 Slack 알림 서비스 개발
  - 추론부 컴포넌트 내부 Slack 알림 서비스 개발
  - Pulumi 를 통한 CloudWatch, SNS, Lambda 알람 프로비저닝 자동화
- 트래픽 증가로 인한 RDS Queue depth 문제 ⇒ Scale up을 통한 문제 해결
- Pulumi 를 이용한 Infrastructure managing
- Distributed Load Testing 을 통하여 초당 2만개의 요청을 보내 아키텍처의 안정성 검증
  - Terraform
  - Locust

# Personal Experience & Projects

## Club Experience

### KUBIG ( 2021.02 ~ 2022.02 )

- CARLA driving Simulation API 과 Policy gradient method 를 이용한 강화 학습 자율주행 프로젝트
- KLUE 수강신청 리뷰 요약 API 서비스 개발
  - KoBART Fine-tuning
  - Flask REST API Server
- 힙합 & 인디 가사 생성 프로젝트
  - GPT-3 Fine-tuning

### Devkor ( 2021.08 ~ )

- Backend 스터디장
  - 2022.09.13 ~
- devkor 공식 웹사이트 개발 참여 ( Backend, Frontend )
  - 2022.08.31 ~
- Connecthon 해커톤 참여

### KWEB ( 2022.05 ~ )

- 정회원
- backend 스터디 참여

## Lab Experience

### Distributed / Cloud Computing Lab 학부 연구생

- 2021.12 ~ 2022.03
- Kubernetes / Golang

# Presentation & Article

## Education

### 고려대학교 컴퓨터학과

- 2017.03 ~ 2023.02
- GPA : 3.58
