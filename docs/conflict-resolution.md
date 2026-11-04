# Conflict Resolution Log

충돌은 숨기지 않고 해결 과정을 남긴다. 충돌을 해결한 사람이 해결 커밋과 같은 PR 에서 기록한다.

<!-- CONFLICT1:START -->
(충돌 기록 #1 작성 예정)
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
