<div align="center">

# 🏸 Badminton Web Application

**코트 매니저 기능을 중심으로 하는 배드민턴 웹 서비스**
<br>
경기/대회 운영과 관리 흐름을 효율적으로 지원합니다.
<br>
</div>

## 👋 소개 (About)

이 프로젝트는 배드민턴 동호인과 대회 운영진을 위한 웹 어플리케이션입니다.
**핵심 기능**인 `코트 매니저`를 통해 복잡한 경기 진행을 직관적으로 관리할 수 있습니다.

## 🧑‍💻 팀원 소개 (Our Team)

| <a href="https://github.com/changyeopbaek"><img src="https://github.com/changyeopbaek.png" width="100px" alt="changyeopbaek"/></a> | <a href="https://github.com/Gumraze-git"><img src="https://github.com/Gumraze-git.png" width="100px" alt="Gumraze-git"/></a> |
| :---: | :---: |
| **[changyeopbaek](https://github.com/changyeopbaek)** | **[Gumraze-git](https://github.com/Gumraze-git)** |
| Frontend Developer | Backend Developer |

## 🚀 주요 기능 및 로드맵 (Roadmap)

### ✅ 현재 기능 (Current Features)

#### 🏸 1. 자유게임 생성 및 매치 구성
- **목적**: 운영자가 비공개 자유게임의 기본 정보 생성/수정 및 라운드/코트/매치 구성.
- **주요 기능**:
    - 게임 제목, 참가자 목록, 코트/라운드 수, 운영자 추가, 급수 형식, 기록 방식 설정.
    - 게임 생성 후 별도 화면에서 라운드, 코트별 매치, 팀(복식) 구성.
    - 초기 매치 구성 후에도 운영자는 기본 정보 및 매치 정보 수정 가능.
    - 참가자는 회원/비회원 모두 가능하며, 게임 생성 후에도 추가/수정/삭제 가능 (매칭 포함 시 삭제 불가).
- **사용자**: 로그인 인증된 운영자.
- **인증 방식**: `Authorization: Bearer <accessToken>` HTTP Header 기반 인증.
- **관련 API**:
    - `PATCH /games/{gameId}`: 기본 정보 수정, 참가자 목록 수정.
    - `PATCH /games/{gameId}/matches`: 매치 팀 구성 저장, 코트/라운드 수 변경, 참여자 설정.

#### 🔗 2. 자유게임 공유 링크 기능
- **목적**: 운영자가 생성한 비공개 자유게임 정보를 링크로 공유하여, 참여자가 게임 현황을 조회.
- **주요 기능**:
    - 운영자는 게임 내용 입력 완료 후 고유 URL 형태의 공유 링크 생성.
    - 링크로 접근 시 로그인 없이 게임 기본 정보 및 라운드/코트 경기표 조회 가능.
- **사용자**: 운영자 (링크 생성), 참여자 (링크 조회).
- **인증 방식**: 링크 생성 (`accessToken` 기반), 링크 조회 (링크 토큰 기반, 로그인 불필요).
- **관련 API**:
    - `POST /games/{gameId}/link`: 링크 생성 (운영자).
    - `GET /games/link/{token}`: 링크 기반 게임 조회 (참여자/운영자).

#### 📋 3. 자유게임 목록/상세 조회
- **목적**: 운영자가 자신이 운영하는 자유게임 목록/상세를 조회하고 관리 화면에 진입. 참여자는 공유 링크로 게임 현황 조회.
- **주요 기능**:
    - 운영자는 자신이 운영자로 등록된 게임만 조회 가능 (목록 및 상세).
    - 목록은 관리 화면 필터/정렬에 활용.
    - 링크 조회 시 게임 기본 정보, 참가자 목록, 라운드/코트 매칭 정보 제공.
- **사용자**: 로그인 인증된 운영자, 링크로 접근한 참여자.
- **인증 방식**: 운영자 조회 (`accessToken` 기반), 링크 조회 (링크 토큰 기반).
- **관련 API**:
    - `GET /games`: 자유게임 목록 조회.
    - `GET /games/{gameId}`: 자유게임 상세 조회.
    - `GET /games/link/{linkToken}`: 링크 기반 게임 조회 (참여자/운영자).

### 🔜 추후 계획

## 📂 리포지토리 (Repositories)

| Repository | Description |
| :--- | :--- |
| **drive-frontend** | 프론트엔드 애플리케이션 |
| **drive-backend** | 백엔드 서버 |

## 🛠️ 기술 스택 (Tech Stack)

| 구분 | 스택 (Stack) |
| :---: | :--- |
| **Frontend** | <img src="https://img.shields.io/badge/Next.js_16-000000?style=for-the-badge&logo=next.js&logoColor=white"> <img src="https://img.shields.io/badge/React_19-61DAFB?style=for-the-badge&logo=react&logoColor=black"> <img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white"> <img src="https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white"> <img src="https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white"> |
| **Backend** | <img src="https://img.shields.io/badge/Java_21-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white"> <img src="https://img.shields.io/badge/Spring_Boot_3.5-6DB33F?style=for-the-badge&logo=springboot&logoColor=white"> <img src="https://img.shields.io/badge/Spring_Security-6DB33F?style=for-the-badge&logo=springsecurity&logoColor=white"> <img src="https://img.shields.io/badge/Spring_Data_JPA-6DB33F?style=for-the-badge&logo=spring&logoColor=white"> <br> <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white"> <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white"> <img src="https://img.shields.io/badge/AWS_EC2-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white"> <img src="https://img.shields.io/badge/Gradle-02303A?style=for-the-badge&logo=gradle&logoColor=white"> |

---
<div align="center">
  <sub>Powered by Drive Team</sub>
</div>
