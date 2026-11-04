# Submission Index

## Team
- 팀명: 코디세이 깃플로우 3조
- 저장소: https://github.com/hauteville1862/codyssey-b2-2
- 팀원: 임유현(@hauteville1862), 이나현(@Rara-rookie), 박경내(@datecoco)

## Repository Setup
- 방식: 옵션 A (GitHub Organization `<org>` 의 저장소)   ← 개인 저장소면 옵션 B
- 저장소: https://github.com/<org>/<repo> (public)
- 팀 단위 저장소 1개, 팀원 3명 모두 push 권한
| 팀원 | GitHub | 권한 |
|---|---|---|
| 임유현 | @hauteville1862 | admin(저장소 생성·보호 규칙) |
| 이나현 | @Rara-rookie | write(Collaborator) |
| 박경내 | @datecoco | write(Collaborator) |

## Member Contributions

| 팀원 | 만든 이슈 | 만든 PR(병합) | 다른 사람 PR 리뷰 |
|---|---|---|---|
| 임유현(@hauteville1862) | [#13 제출물 인덱스 SUBMISSION.md 와 히스토리 증빙 정리](https://github.com/hauteville1862/codyssey-b2-2/issues/13)<br>[#7 CONTRIBUTING 브랜치 전략·네이밍·커밋 규칙 작성](https://github.com/hauteville1862/codyssey-b2-2/issues/7)<br>[#1 문자열 유틸 slugify, truncate 추가](https://github.com/hauteville1862/codyssey-b2-2/issues/1) | [#14 docs: 제출물 인덱스와 히스토리 증빙 추가](https://github.com/hauteville1862/codyssey-b2-2/pull/14) (진행 중)<br>[#10 docs: CONTRIBUTING 브랜치 전략·네이밍·커밋 규칙 작성](https://github.com/hauteville1862/codyssey-b2-2/pull/10) (진행 중)<br>[#2 feat: 문자열 유틸 slugify, truncate 추가](https://github.com/hauteville1862/codyssey-b2-2/pull/2) (진행 중) | 2건: #4, #11 |
| 이나현(@Rara-rookie) | [#8 CONTRIBUTING PR·코드 리뷰 규칙 작성](https://github.com/hauteville1862/codyssey-b2-2/issues/8)<br>[#5 수학 유틸 clamp, mean 추가](https://github.com/hauteville1862/codyssey-b2-2/issues/5) | [#12 docs: CONTRIBUTING PR·코드 리뷰 규칙 작성](https://github.com/hauteville1862/codyssey-b2-2/pull/12) (진행 중)<br>[#6 feat: 수학 유틸 clamp, mean 추가](https://github.com/hauteville1862/codyssey-b2-2/pull/6) (진행 중) | 3건: #2, #10, #14 |
| 박경내(@datecoco) | [#9 CONTRIBUTING 충돌 대응 흐름 작성, 용어집 위치 정리](https://github.com/hauteville1862/codyssey-b2-2/issues/9)<br>[#3 날짜 유틸 days_between, is_weekend 추가](https://github.com/hauteville1862/codyssey-b2-2/issues/3) | [#11 docs: CONTRIBUTING 충돌 대응 흐름 작성, 용어집 위치 정리](https://github.com/hauteville1862/codyssey-b2-2/pull/11) (진행 중)<br>[#4 feat: 날짜 유틸 days_between, is_weekend 추가](https://github.com/hauteville1862/codyssey-b2-2/pull/4) (진행 중) | 2건: #6, #12 |

## Key Docs
- Contributing: [docs/CONTRIBUTING.md](docs/CONTRIBUTING.md)
- Conflict log: [docs/conflict-resolution.md](docs/conflict-resolution.md) (충돌 2건: 같은 hunk, 이름 변경+수정)
- Troubleshooting: [docs/troubleshooting-log.md](docs/troubleshooting-log.md) (amend, reset --soft, revert, stash)
- 결과물: 팀원별 유틸 함수 [src/](src/), 팀 소개 [team/](team/)
- 보너스: [docs/rebase-log.md](docs/rebase-log.md), [.github/CODEOWNERS](.github/CODEOWNERS)

## Branch Protection (main)
- PR 필수, 승인 1명 이상, 관리자 포함 적용: True
- 직접 push 거절 증빙: [docs/git-log-graph.txt](docs/git-log-graph.txt) 하단

## Evidence
- git log --oneline --graph --all: [docs/git-log-graph.txt](docs/git-log-graph.txt)
