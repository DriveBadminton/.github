# 브랜치 전략 (Branching Strategy)

## 1. 문서 목적 (Purpose)
- 우리 조직의 Android 앱 개발 워크플로우에 일관성을 주고, 충돌을 최소화하기 위한 GitHub Flow 기반 브랜치 전략을 정의한다.

## 2. 주요 브랜치 (Primary Branches)
- main

## 3. 기능 브랜치 (Feature Branches)
- 네이밍 규칙
- feature/<ISSUE번호>-<간단한설명>
  - 예) feature/123-add-user-login

- 브랜치 생성
  ```bash
  git checkout main
  git pull origin main
  git checkout -b feature/123-add-user-login
  ```


## 4. 버그·핫픽스 브랜치 (Bugfix & Hotfix)
-	버그 수정 브랜치
-	네이밍: bugfix/<ISSUE번호>-<간단한설명>
-	긴급 수정 브랜치
-	네이밍: hotfix/<버전>-<간단한설명>
-	Workflow
  1.	main에서 분기
  2.	수정 → PR → 머지 → 태그/릴리스

## 5. Pull Request 가이드라인 (PR Guidelines)
-	PR 제목 포맷
  ``` text
  [ISSUE-123] 로그인 화면 구현
  ```
-	PR 내용
-	구현 배경 및 목적
-	변경 사항 요약
-	리뷰 조건
-	최소 1명 리뷰 승인(개인 프로젝트이므로 사용하지 않음)
-	CI (Build/Test) 모두 통과

## 6. 머지 전략 (Merge Strategy)
-	Rebase & Merge
