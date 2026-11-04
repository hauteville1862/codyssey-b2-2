# Contributing Guide

팀 협업 규칙이다. 각 절은 담당자가 자기 PR 에서 채운다.

## 1. 브랜치 전략(GitHub Flow) — 담당 임유현
<!-- SEC1:START -->
(작성 예정)
<!-- SEC1:END -->

## 2. 브랜치 네이밍과 커밋 메시지 컨벤션 — 담당 임유현
<!-- SEC2:START -->
(작성 예정)
<!-- SEC2:END -->

## 3. PR 작성 규칙 — 담당 이나현
<!-- SEC3:START -->
(작성 예정)
<!-- SEC3:END -->

## 4. 코드 리뷰 규칙 — 담당 이나현
<!-- SEC4:START -->
(작성 예정)
<!-- SEC4:END -->

## 5. 충돌 발생 시 대응 흐름 — 담당 박경내
<!-- SEC5:START -->
1. **발견**: `git merge origin/main` 또는 PR 화면에서 충돌을 확인한 사람이 PR 코멘트로 알린다.
2. **최신화**: 자기 브랜치에서 `git fetch origin` → `git merge origin/main` (공유 브랜치는 rebase 하지 않는다).
3. **판단**: 충돌 구간의 양쪽 의도를 읽고 keep both / choose one / refactor 중 고른다. 판단이 어렵다면 상대 작성자와 코멘트로 합의한다.
4. **검증**: 충돌 표식(`<<<<<<<`, `=======`, `>>>>>>>`)이 남지 않았는지 확인하고 실행·doctest 를 다시 돌린다.
5. **기록**: 해결 커밋 뒤 `docs/conflict-resolution.md` 에 상황·표식·해결 과정·결과·배운 점을 남긴다.
6. **재요청**: 원래 리뷰어에게 리뷰를 다시 요청한다. 해결 커밋에서 무엇을 골랐는지 PR 코멘트로 요약한다.
<!-- SEC5:END -->

## 6. 병합 전 공통 체크리스트
<!-- CHECKLIST:START -->
- [ ] (초안)
<!-- CHECKLIST:END -->
