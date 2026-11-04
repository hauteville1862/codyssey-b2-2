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

## Review Evidence

### 1. 리뷰 반영 기록 (본인 PR 에서 리뷰 코멘트를 반영한 증거)

리뷰어가 인라인 코멘트로 변경을 요청하거나 제안하면, 작성자가 반영 커밋을 만들고 같은 스레드에 커밋 해시를 적어 답했다.

| 팀원 | 내 PR | 받은 리뷰 코멘트 | 반영 커밋 | 내 답글 |
|---|---|---|---|---|
| 임유현(@hauteville1862) | [#2](https://github.com/hauteville1862/codyssey-b2-2/pull/2) | [@Rara-rookie 코멘트](https://github.com/hauteville1862/codyssey-b2-2/pull/2#discussion_r4462890644) | [`0bb7716`](https://github.com/hauteville1862/codyssey-b2-2/commit/0bb7716) | [답글](https://github.com/hauteville1862/codyssey-b2-2/pull/2#discussion_r4462891616) |
| 임유현(@hauteville1862) | [#10](https://github.com/hauteville1862/codyssey-b2-2/pull/10) | [@Rara-rookie 코멘트](https://github.com/hauteville1862/codyssey-b2-2/pull/10#discussion_r4462896409) | [`14d4383`](https://github.com/hauteville1862/codyssey-b2-2/commit/14d4383) | [답글](https://github.com/hauteville1862/codyssey-b2-2/pull/10#discussion_r4462897550) |
| 임유현(@hauteville1862) | [#14](https://github.com/hauteville1862/codyssey-b2-2/pull/14) | [@Rara-rookie 코멘트](https://github.com/hauteville1862/codyssey-b2-2/pull/14#discussion_r4462936103) | [`38ecf50`](https://github.com/hauteville1862/codyssey-b2-2/commit/38ecf50) | [답글](https://github.com/hauteville1862/codyssey-b2-2/pull/14#discussion_r4462938170) |
| 이나현(@Rara-rookie) | [#6](https://github.com/hauteville1862/codyssey-b2-2/pull/6) | [@datecoco 코멘트](https://github.com/hauteville1862/codyssey-b2-2/pull/6#discussion_r4462889145) | [`bc2002a`](https://github.com/hauteville1862/codyssey-b2-2/commit/bc2002a) | [답글](https://github.com/hauteville1862/codyssey-b2-2/pull/6#discussion_r4462889871) |
| 이나현(@Rara-rookie) | [#12](https://github.com/hauteville1862/codyssey-b2-2/pull/12) | [@datecoco 코멘트](https://github.com/hauteville1862/codyssey-b2-2/pull/12#discussion_r4462896365) | [`d87aae8`](https://github.com/hauteville1862/codyssey-b2-2/commit/d87aae8) | [답글](https://github.com/hauteville1862/codyssey-b2-2/pull/12#discussion_r4462898409) |
| 박경내(@datecoco) | [#4](https://github.com/hauteville1862/codyssey-b2-2/pull/4) | [@hauteville1862 코멘트](https://github.com/hauteville1862/codyssey-b2-2/pull/4#discussion_r4462749816) | [`ff6bcda`](https://github.com/hauteville1862/codyssey-b2-2/commit/ff6bcda) | [답글](https://github.com/hauteville1862/codyssey-b2-2/pull/4#discussion_r4462751613) |
| 박경내(@datecoco) | [#11](https://github.com/hauteville1862/codyssey-b2-2/pull/11) | [@hauteville1862 코멘트](https://github.com/hauteville1862/codyssey-b2-2/pull/11#discussion_r4462898072) | [`f100be6`](https://github.com/hauteville1862/codyssey-b2-2/commit/f100be6) | [답글](https://github.com/hauteville1862/codyssey-b2-2/pull/11#discussion_r4462899619) |

### 2. 작성한 리뷰 (다른 사람 PR, 팀원별 2개 PR 이상)

| 리뷰어 | 리뷰한 PR | 인라인 코멘트 | 첫 리뷰 | 승인 리뷰 |
|---|---|---|---|---|
| 임유현(@hauteville1862) | [#4](https://github.com/hauteville1862/codyssey-b2-2/pull/4) | [코멘트](https://github.com/hauteville1862/codyssey-b2-2/pull/4#discussion_r4462749816) | [변경 요청](https://github.com/hauteville1862/codyssey-b2-2/pull/4#pullrequestreview-5762212652) | [승인](https://github.com/hauteville1862/codyssey-b2-2/pull/4#pullrequestreview-5762216895) |
| 임유현(@hauteville1862) | [#11](https://github.com/hauteville1862/codyssey-b2-2/pull/11) | [코멘트](https://github.com/hauteville1862/codyssey-b2-2/pull/11#discussion_r4462898072) | [코멘트 리뷰](https://github.com/hauteville1862/codyssey-b2-2/pull/11#pullrequestreview-5762390231) | [승인](https://github.com/hauteville1862/codyssey-b2-2/pull/11#pullrequestreview-5762434041) |
| 이나현(@Rara-rookie) | [#2](https://github.com/hauteville1862/codyssey-b2-2/pull/2) | [코멘트](https://github.com/hauteville1862/codyssey-b2-2/pull/2#discussion_r4462890644) | [변경 요청](https://github.com/hauteville1862/codyssey-b2-2/pull/2#pullrequestreview-5762380355) | [승인](https://github.com/hauteville1862/codyssey-b2-2/pull/2#pullrequestreview-5762383838) |
| 이나현(@Rara-rookie) | [#10](https://github.com/hauteville1862/codyssey-b2-2/pull/10) | [코멘트](https://github.com/hauteville1862/codyssey-b2-2/pull/10#discussion_r4462896409) | [코멘트 리뷰](https://github.com/hauteville1862/codyssey-b2-2/pull/10#pullrequestreview-5762387996) | [승인](https://github.com/hauteville1862/codyssey-b2-2/pull/10#pullrequestreview-5762391438) |
| 이나현(@Rara-rookie) | [#14](https://github.com/hauteville1862/codyssey-b2-2/pull/14) | [코멘트](https://github.com/hauteville1862/codyssey-b2-2/pull/14#discussion_r4462936103) | [코멘트 리뷰](https://github.com/hauteville1862/codyssey-b2-2/pull/14#pullrequestreview-5762437797) | [승인](https://github.com/hauteville1862/codyssey-b2-2/pull/14#pullrequestreview-5762441335) |
| 박경내(@datecoco) | [#6](https://github.com/hauteville1862/codyssey-b2-2/pull/6) | [코멘트](https://github.com/hauteville1862/codyssey-b2-2/pull/6#discussion_r4462889145) | [변경 요청](https://github.com/hauteville1862/codyssey-b2-2/pull/6#pullrequestreview-5762378600) | [승인](https://github.com/hauteville1862/codyssey-b2-2/pull/6#pullrequestreview-5762381676) |
| 박경내(@datecoco) | [#12](https://github.com/hauteville1862/codyssey-b2-2/pull/12) | [코멘트](https://github.com/hauteville1862/codyssey-b2-2/pull/12#discussion_r4462896365) | [코멘트 리뷰](https://github.com/hauteville1862/codyssey-b2-2/pull/12#pullrequestreview-5762387919) | [승인](https://github.com/hauteville1862/codyssey-b2-2/pull/12#pullrequestreview-5762394697) |

## Evidence
- git log --oneline --graph --all: [docs/git-log-graph.txt](docs/git-log-graph.txt)
