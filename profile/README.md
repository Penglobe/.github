
# 🐧 Penglobe - 생활 속 실천을 가치로 전환하는 환경 금융 플랫폼
## 🏆 신한금융 SW 아카데미 5기 — 최우수상 수상작

> “**걸을수록, 지구가 가벼워집니다.**”  
> Penglobe는 일상의 친환경 실천을 **데이터와 보상으로 연결하는 환경 금융 플랫폼**입니다.  
> 사용자가 걸을 때마다, 식사를 선택할 때마다, 탄소 절감 데이터가 쌓이고  
> 그 노력은 **빙하를 회복시키며 펭귄 ‘이파’와 ‘토리’를 다시 만나게 합니다.**  
> 친환경 행동이 시각적으로 보상되는 ‘감정 피드백형 홈화면’을 통해  
> 즐겁게 지속 가능한 변화를 만들어갑니다. 


<div align="center">
  <img src="https://github.com/user-attachments/assets/9f5fcc86-e5a3-4f66-a90a-922dc9b72468" width="23%" />
  <img src="https://github.com/user-attachments/assets/0a35894a-c5c7-4e17-9aa3-033045c503dc" width="23%" />
  <img src="https://github.com/user-attachments/assets/218b3d5a-957b-4d1c-8ac3-f0a5639cd477" width="23%" />
  <img src="https://github.com/user-attachments/assets/7aefd07c-65ff-4ad8-b7b8-83668eb2676f" width="23%" />
</div>

<br/>

<div align="center">

<table>
  <tr>
    <td align="center" width="33%"><b>🥾 펭걸음</b></td>
    <td align="center" width="33%"><b>🍱 빙하 식탁</b></td>
    <td align="center" width="33%"><b>📊 빙하 리포트</b></td>
  </tr>
  <tr>
    <td align="center"><img src="https://github.com/user-attachments/assets/738a94db-a323-4dae-9755-a1d21eb2ab3b" width="100%"/></td>
    <td align="center"><img src="https://github.com/user-attachments/assets/058bcddf-508a-4f88-ac37-b8620799df57" width="100%"/></td>
    <td align="center"><img src="https://github.com/user-attachments/assets/090dc4e7-1871-415a-a9fd-0883adae5fc6" width="100%"/></td>
  </tr>
</table>

</div>

---

## 📽️ 데모 & 자료

* 🎬 [**시연 영상**](https://drive.google.com/file/d/1e97pq4gYXMU9lzTcpQ6OluwVyoFs7QQT/view?usp=sharing) — 실제 앱 시연 장면
* 🎤 [**사용자 인터뷰 영상**](https://drive.google.com/file/d/19bxkwbrXZdF3JYh2HtyigsmyPSMhiUoA/view?usp=sharing) — 실제 사용자 반응 인터뷰
- 🧾 [**프로젝트 발표자료 (PPT)**](../Penglobe_PPT.pdf) — 최종 발표용 슬라이드  
- 📄 [**요구사항 명세서**](../Penglobe_Requirement.pdf) — 기능 및 시스템 상세 정의서  

---

## 🧩 핵심 기능

| 기능 | 설명 |
|------|------|
| 🥾 **펭걸음** | GPS 기반 이동 추적 및 교통수단별 탄소 절감 계산 |
| 🍱 **빙하 식탁** | FoodLens SDK + AI로 식단 탄소 배출량 분석 |
| 📊 **빙하 리포트** | 설문 + AI 피드백 기반 1일 탄소 리포트 제공 |
| 🧊 **얼음 거래소** | 절감 포인트(얼음)으로 친환경 제품 구매/기부 |
| 🏅 **랭킹·퀴즈·미션** | 소속감과 경쟁으로 지속적 참여 유도 |

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
<summary><h2>🏗️ 전체 아키텍처 보기</h2></summary>

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

## 📈 시범 운영

| 항목            | 결과                        |
| ------------- | ------------------------- |
| 운영 기간         | 2025.09.20 ~ 2025.09.28   |
| 참여자 수         | 30명                       |
| 긍정 응답률        | 94.4%                     |
| 주요 피드백        | “쉽고 재미있다”, “습관처럼 사용하게 된다” |

> 실제 사용자 테스트에서 **친환경 실천 동기부여 효과 94%**

---

## 👥 팀 Penglobe

| 이름      | 담당 기능     | 주요 역할                                  |
| ------- | --------- | -------------------------------------- |
| **최원정** | 🧊 미션     | 회원가입·로그인, 얼음 거래소, 결제 기능 구현             |
| **최은진** | 🥾 펭걸음    | 백엔드 아키텍처 설계 및 관리, 서버/DB 배포, 안드로이드 빌드   |
| **한진호** | 🏅 랭킹     | 내 정보 및 랭킹 서비스, 자동화 로직(스케줄링) 구현         |
| **김세연** | 🍱 빙하 식탁  | 프론트엔드 아키텍처 관리, LLM 연동, 홈 화면 구성, iOS 빌드 |
| **최희정** | 📊 빙하 리포트 | 퀴즈·관리자 페이지, 운영 관리, 문서 관리               |


---

## 🔗 리포지토리

| 구분              | 링크                                                    |
| --------------- | ----------------------------------------------------- |
| 🖥️ **Backend** | [Penglobe/server](https://github.com/Penglobe/server) |
| 📱 **Frontend** | [Penglobe/front](https://github.com/Penglobe/front)   |


