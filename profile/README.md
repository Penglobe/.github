
# 🐧 Penglobe - 생활 속 실천을 가치로 전환하는 환경 금융 플랫폼
**🏆 신한금융 SW 아카데미 5기 — 최우수상 수상작**  

> “**걸을수록, 지구가 가벼워집니다.**”  
> 개인의 친환경 실천을 **데이터와 보상**으로 연결하는 플랫폼입니다.  
> 실시간 이동·식습관·미션 데이터를 기반으로 **탄소 절감량을 시각화하고 보상으로 전환**합니다.

---

## 📽️ 데모 & 자료

* 🎬 [**시연 영상**](https://drive.google.com/file/d/1e97pq4gYXMU9lzTcpQ6OluwVyoFs7QQT/view?usp=sharing) — 실제 앱 시연 장면
* 🎤 [**사용자 인터뷰 영상**](https://drive.google.com/file/d/19bxkwbrXZdF3JYh2HtyigsmyPSMhiUoA/view?usp=sharing) — 실제 사용자 반응 인터뷰
* 🧾 [**프로젝트 발표자료 (PPT)**](./Penglobe_PPT.pdf) — 최종 발표용 슬라이드
* 📄 [**요구사항 명세서**](./Penglobe_Requirement.pdf) — 기능 및 시스템 상세 정의서

---

## 🧩 핵심 기능

| 기능 | 설명 |
|------|------|
| 🥾 **펭걸음** | GPS 기반 이동 추적 및 교통수단별 탄소 절감 계산 |
| 🍱 **빙하 식탁** | FoodLens SDK + AI로 식단 탄소 배출량 분석 |
| 📊 **빙하 리포트** | 설문 + AI 피드백 기반 1일 탄소 리포트 제공 |
| 🧊 **얼음 시스템** | 절감 포인트(얼음)으로 친환경 제품 구매/기부 |
| 🏅 **랭킹·퀴즈·미션** | 게임 요소로 지속적 참여 유도 |

---

## ⚙️ 기술 스택

| 영역 | 기술 |
|------|------|
| **Backend** | Java, Spring Boot, Spring Security, JPA, Swagger |
| **Frontend** | React Native, Expo, TailwindCSS |
| **Database** | MariaDB |
| **AI / SDK** | Groq LLM API, FoodLens SDK |
| **Infra / Deploy** | Ubuntu 22.04, Docker |
| **Collaboration** | GitHub, Figma, Notion, Slack |

---

<details>
<summary>🏗️ 전체 아키텍처 보기 </summary>

```mermaid
flowchart LR
    %% =========================
    %% CLIENT
    subgraph Client["프론트엔드 (React Native + Expo)"]
        RN["📱 React Native App"]
        FOODLENS["🍱 FoodLens SDK (AI 음식 인식)"]
        EXPO["📷 Expo SDK (Camera, Location 등)"]
    end

    %% =========================
    %% BACKEND
    subgraph Backend["백엔드 (Spring Boot)"]
        API["🧩 REST API"]
        SEC["🔐 Spring Security + JWT"]
        SWAGGER["📜 Swagger UI"]
        JPA["🗃️ Spring Data JPA + Hibernate"]
    end

    %% =========================
    %% DATABASE
    subgraph Database["데이터베이스 (MariaDB)"]
        DB[("💾 MariaDB")]
    end

    %% =========================
    %% EXTERNAL API
    subgraph External["외부 API & 서비스"]
        KAKAO["🗺️ 카카오 지도 API"]
        PORTONE["💳 PortOne (아임포트) 결제 API"]
        GROQ["🤖 Groq LLM API"]
    end

    %% =========================
    %% INFRA
    subgraph Infra["배포 환경 (Ubuntu + Docker)"]
        UBUNTU["🟠 Ubuntu 22.04 서버"]
        DOCKER["🐳 Docker 컨테이너"]
    end

    %% =========================
    %% CONNECTIONS
    RN --> API
    RN --> FOODLENS
    RN --> EXPO
    API --> SEC
    API --> SWAGGER
    API --> JPA
    API --> DB
    API --> KAKAO
    API --> PORTONE
    API --> GROQ
    UBUNTU --> DOCKER
    DOCKER --> API
    DOCKER --> DB

    %% =========================
    %% STYLE
    style RN fill:#61DAFB,stroke:#000,stroke-width:1px,color:#000
    style API fill:#6DB33F,stroke:#2c662d,stroke-width:1px,color:#fff
    style SEC fill:#6DB33F,stroke:#2c662d,stroke-width:1px,color:#fff
    style SWAGGER fill:#6DB33F,stroke:#2c662d,stroke-width:1px,color:#fff
    style JPA fill:#6DB33F,stroke:#2c662d,stroke-width:1px,color:#fff
    style DB fill:#003545,stroke:#001f2a,stroke-width:1px,color:#fff
    style FOODLENS fill:#FF6F61,stroke:#c94d44,stroke-width:1px,color:#fff
    style KAKAO fill:#FFCD00,stroke:#bba100,stroke-width:1px,color:#000
    style PORTONE fill:#0064FF,stroke:#003d99,stroke-width:1px,color:#fff
    style GROQ fill:#FF4A4A,stroke:#b92f2f,stroke-width:1px,color:#fff
    style UBUNTU fill:#E95420,stroke:#b23d16,stroke-width:1px,color:#fff
    style DOCKER fill:#2496ED,stroke:#1866a6,stroke-width:1px,color:#fff
    style EXPO fill:#000000,stroke:#333333,stroke-width:1px,color:#fff
````

</details>

---

## 📈 시범 운영 결과

| 항목            | 결과                        |
| ------------- | ------------------------- |
| 운영 기간         | 2025.09.20 ~ 2025.09.28   |
| 참여자 수         | 30명                       |
| 긍정 응답률        | 94.4%                     |
| 실제 친환경 행동 증가율 | 83.3%                     |
| 주요 피드백        | “쉽고 재미있다”, “습관처럼 사용하게 된다” |

> 실제 사용자 테스트에서 **친환경 실천 동기부여 효과 94%**,
> **행동 변화율 83%** 달성

---

## 👥 팀 Penglobe

| 이름      | 담당 기능     | 주요 역할                                 |
| ------- | --------- | ------------------------------------- |
| **최원정** | 🧊 미션     | 회원가입·로그인, 얼음 거래소, 결제                  |
| **최은진** | 🥾 펭걸음    | GPS 이동 추적, 서버/DB 배포, 백엔드 아키텍처         |
| **한진호** | 🏅 랭킹     | 지역/주간/전체 랭킹, 내 정보, 자동화 로직             |
| **김세연** | 🍱 빙하 식탁  | FoodLens SDK 연동, LLM 연결, 홈 구성, iOS 빌드 |
| **최희정** | 📊 빙하 리포트 | 설문 리포트, AI 피드백, 퀴즈/관리자 페이지, 운영관리      |

---

## 🔗 리포지토리

| 구분              | 링크                                                    |
| --------------- | ----------------------------------------------------- |
| 🖥️ **Backend** | [Penglobe/server](https://github.com/Penglobe/server) |
| 📱 **Frontend** | [Penglobe/front](https://github.com/Penglobe/front)   |


그림으로 첫인상 확실히 주고 싶으신가요? (예: 로고나 서비스 메인화면 캡처)
```
