# Conflict Resolution Log

충돌은 숨기지 않고 해결 과정을 남긴다. 충돌을 해결한 사람이 해결 커밋과 같은 PR 에서 기록한다.

<!-- CONFLICT1:START -->
## 충돌 기록 #1 — 두 사람이 같은 곳(같은 hunk)을 다르게 고친 충돌

### 참여자
- 해결한 사람: 이나현(@Rara-rookie) — `feature/b-contributing-review` (PR #12)
- 상대: 임유현(@hauteville1862) — PR #10 (`feature/a-contributing-flow`, 먼저 병합됨)
- 기록 작성: 박경내(@datecoco), 저장소 기록(커밋)을 보고 나중에 정리함

### 상황(What happened)
- PR #10 이 먼저 main 에 병합된 뒤, 최신 main 을 `feature/b-contributing-review` 로 병합하자 충돌이 났다.
- 충돌 파일: docs/CONTRIBUTING.md 의 `## 6. 병합 전 공통 체크리스트` 구간

### 충돌 내용(Conflict markers)
```txt
# docs/CONTRIBUTING.md
<!-- CHECKLIST:START -->
<<<<<<< d87aae8 (docs: add review response time rule)
- [ ] 리뷰어 1명 이상의 승인을 받았다
- [ ] 리뷰 코멘트에 모두 답하거나 반영했다
=======
- [ ] PR 본문에 What / Why / How 와 Closes #이슈 가 있다
- [ ] 로컬에서 실행·doctest 를 확인했다
>>>>>>> 8aa3ea8 (Merge pull request #10 from hauteville1862/feature/a-contributing-flow)
<!-- CHECKLIST:END -->
```
(위 표식은 `git show --remerge-diff 82b1c4c` 로 다시 만들어 확인한 것이다.)

### 해결 과정(How)
- 전략: **choose one(내 쪽 선택)**. 해결 커밋에는 이나현 브랜치 쪽 두 줄(리뷰 승인, 리뷰 코멘트 반영)만 남았고, main 쪽 두 줄은 들어가지 않았다.
- 해결 커밋: `82b1c4c` (Merge branch 'main' into feature/b-contributing-review, 2026-11-04 11:36 KST)
- 당시 터미널 명령과 출력은 남아 있지 않아 적지 않는다.

### 결과(Outcome)
- 해결 후 PR #12 가 main 에 병합됐다(병합 커밋 `1640ad2`).

### 배운 점(Learnings)
- 같은 체크리스트 구간을 여러 사람이 동시에 고치면 같은 hunk 충돌이 난다. 담당 구간을 나누거나 먼저 병합된 내용을 받은 뒤 이어 쓰면 줄일 수 있다.
- choose one 으로 해결하면 상대 쪽 내용이 빠질 수 있으니, 버린 줄이 정말 필요 없는지 상대 작성자와 확인하는 게 좋다.
<!-- CONFLICT1:END -->

<!-- CONFLICT2:START -->
## 충돌 기록 #2 — 한쪽은 파일 이동+수정, 다른 쪽은 옛 경로에서 같은 줄 수정한 충돌

### 참여자
- 작성자: 박경내(@datecoco) — `feature/c-contributing-conflict`
- 상대: 이나현(@Rara-rookie) — PR #12 (`feature/b-contributing-review`, 먼저 병합됨)

### 상황(What happened)
- 상대 PR 이 먼저 main 에 병합된 뒤, 내 PR 을 병합하기 전에 최신 main 을 내 브랜치로 병합하자 충돌이 났다.
- 충돌 파일: docs/reference/glossary.md

### 충돌 내용(Conflict markers)
```txt
# docs/reference/glossary.md
<<<<<<< HEAD:docs/reference/glossary.md
- **PR(Pull Request)**: 브랜치의 변경을 main 에 합쳐 달라는 요청. 본문의 Closes #번호로 이슈와 연결한다
=======
- **PR(Pull Request)**: 브랜치의 변경을 main 에 합쳐 달라는 요청. 코드 리뷰와 토론이 이루어지는 단위
>>>>>>> origin/main:docs/glossary.md
```

### 해결 과정(How)
- 전략: **keep both**. 두 쪽 변경이 서로 다른 내용을 더하는 것이라 한쪽을 버릴 이유가 없어, 우리 쪽 줄을 두고 상대 쪽에만 있는 줄을 이어 붙였다.
- 실제 명령과 출력:
```txt
$ git fetch origin
$ git merge --no-edit origin/main
Auto-merging docs/CONTRIBUTING.md
Auto-merging docs/reference/glossary.md
CONFLICT (content): Merge conflict in docs/reference/glossary.md
Automatic merge failed; fix conflicts and then commit the result.
(편집) 충돌 구간을 두 쪽 줄의 합집합으로 정리하고 표식 제거
$ git add docs/reference/glossary.md
$ git commit --no-edit
```

### 결과(Outcome)
- 해결 커밋 `607e88f`, PR #11 에 push 후 원래 리뷰어에게 재요청했다.

### 배운 점(Learnings)
- 여러 사람이 함께 쓰는 절(체크리스트·용어집)은 담당자를 정하거나 먼저 병합된 내용을 받은 뒤 이어 쓰면 충돌을 줄일 수 있다.
- 파일을 옮길 때는 옮기는 PR 을 먼저 병합하고 공지하면 다른 사람이 옛 경로를 고치는 일을 막을 수 있다.
<!-- CONFLICT2:END -->
