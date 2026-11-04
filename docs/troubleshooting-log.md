# Troubleshooting Log

팀 전체가 네 가지 시나리오를 실제로 수행하고 명령과 출력을 그대로 기록한다.

## 시나리오 1. `git commit --amend` — 최근 커밋 메시지 수정 (임유현)
<!-- AMEND:START -->
### 참여자
- 임유현(@hauteville1862) — 실행·기록

### 상황
- `src/text_utils.py` 를 커밋한 직후 메시지에 오타(`utlis`, `slugfy`, `truncte`)가 있는 것을 발견했다. 아직 push 전이다.

### 시도한 명령/절차
```text
$ git add src/text_utils.py
$ git commit -q -m feat: add text utlis slugfy and truncte
$ git log --oneline -1
c7ac952 feat: add text utlis slugfy and truncte
# 오타가 있는 메시지를 push 전에 발견했다. 아직 원격에 없으므로 --amend 로 고친다.
$ git commit --amend -q -m feat: add text utils slugify and truncate
$ git log --oneline -1
db980ad feat: add text utils slugify and truncate
```

### 결과
- 커밋 해시가 바뀌고 메시지만 고쳐졌다. 변경 내용은 그대로다.
- 주의: `--amend` 는 커밋을 새로 만드는 히스토리 재작성이다. 이미 push 한 커밋에 쓰면 강제 push 가 필요해지므로 공유 브랜치에서는 쓰지 않는다.

### 왜 이 방법을 선택했는가
- 원격에 올라가기 전의 마지막 커밋이라 다른 사람 히스토리에 영향이 없다. 되돌리는 커밋(revert)을 추가하면 의미 없는 커밋만 늘어난다.
<!-- AMEND:END -->

## 시나리오 2. `git reset --soft HEAD~1` — 로컬 커밋 취소, 변경 유지 (이나현)
<!-- RESET:START -->
### 참여자
- 이나현(@Rara-rookie) — 실행·기록

### 상황
- `src/math_utils.py` 를 커밋하면서 실수로 디버그용 `src/debug_scratch.py` 까지 넣었다. 아직 push 전이다.

### 시도한 명령/절차
```text
$ git add src/math_utils.py src/debug_scratch.py
$ git commit -q -m feat: add math utils clamp and mean
$ git show --stat --oneline HEAD
9a8ad12 feat: add math utils clamp and mean
 src/debug_scratch.py |  1 +
 src/math_utils.py    | 19 +++++++++++++++++++
 2 files changed, 20 insertions(+)
# 디버그용 파일까지 함께 커밋했다. push 전이므로 커밋만 취소하고 변경은 스테이징에 남긴다.
$ git reset --soft HEAD~1
$ git status --short
A  src/debug_scratch.py
A  src/math_utils.py
$ git restore --staged src/debug_scratch.py
$ rm src/debug_scratch.py
$ git commit -q -m feat: add math utils clamp and mean
$ git show --stat --oneline HEAD
60c01b0 feat: add math utils clamp and mean
 src/math_utils.py | 19 +++++++++++++++++++
 1 file changed, 19 insertions(+)
```

### 결과
- 잘못된 커밋은 없어지고 변경은 스테이징에 그대로 남았다. 디버그 파일만 빼고 다시 커밋했다.
- 주의: `reset` 은 브랜치 포인터를 뒤로 옮기는 히스토리 재작성이다. push 한 커밋에는 쓰지 않는다.

### 왜 이 방법을 선택했는가
- `--soft` 는 작업 내용을 잃지 않는다(`--hard` 는 변경까지 버린다). 커밋 구성만 다시 하면 되는 상황에 맞다.
<!-- RESET:END -->

## 시나리오 3. `git revert` — 원격에 push 된 커밋 취소 (임유현)
<!-- REVERT:START -->
### 참여자
- 임유현(@hauteville1862) — 실행·기록

### 상황
- 과제 범위에 없는 `docs/release-note-draft.md` 를 커밋하고 원격 브랜치에 push 했다. 리뷰어가 이미 브랜치를 받아 갔을 수 있다.

### 시도한 명령/절차
```text
$ git log --oneline -2
ba3d6b8 docs: add release note draft
77792f9 docs: add branch strategy and commit convention to CONTRIBUTING
# 릴리스 노트는 이 과제 범위가 아니라서 되돌린다. 이미 원격 브랜치에 push 했으므로 reset 대신 revert 한다.
$ git revert --no-edit HEAD
[feature/a-contributing-flow ba2f1d4] Revert "docs: add release note draft"
 Date: Wed Nov 4 11:30:58 2026 +0900
 1 file changed, 3 deletions(-)
 delete mode 100644 docs/release-note-draft.md
$ git log --oneline -3
ba2f1d4 Revert "docs: add release note draft"
ba3d6b8 docs: add release note draft
77792f9 docs: add branch strategy and commit convention to CONTRIBUTING
$ git push origin feature/a-contributing-flow
To https://github.com/hauteville1862/codyssey-b2-2.git
   ba3d6b8..ba2f1d4  feature/a-contributing-flow -> feature/a-contributing-flow
```

### 결과
- 원래 커밋은 남고, 그 변경을 지우는 새 커밋이 추가됐다. 강제 push 없이 일반 push 로 끝났다.

### 왜 이 방법을 선택했는가
- `reset` 으로 커밋을 지우면 원격과 히스토리가 달라져 강제 push 가 필요하고, 이미 받아 간 팀원 히스토리와 어긋난다.
- `revert` 는 히스토리를 고치지 않고 되돌림을 기록으로 남기므로 공유 브랜치에서 안전하다.
<!-- REVERT:END -->

## 시나리오 4. `git stash` / `git stash pop` — 작업 보관 후 전환 (박경내)
<!-- STASH:START -->
### 참여자
- 박경내(@datecoco) — 실행·기록

### 상황
- 날짜 유틸을 절반쯤 작성한 상태에서 main 의 최신 변경을 확인해야 했다. 미완성 코드를 커밋하고 싶지 않았다.

### 시도한 명령/절차
```text
$ git status --short
?? src/date_utils.py
# days_between 까지 작성했는데 main 에 올라온 변경을 먼저 확인해야 한다. 미완성 작업을 커밋하지 않고 보관한다.
$ git stash push -u -m date utils in progress
Saved working directory and index state On feature/c-date-utils: date utils in progress
$ git stash list
stash@{0}: On feature/c-date-utils: date utils in progress
$ git switch main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
$ git pull --ff-only origin main
From https://github.com/hauteville1862/codyssey-b2-2
 * branch            main       -> FETCH_HEAD
Already up to date.
$ git log --oneline -3
fb8d588 chore: initialize repository structure and collaboration docs
$ git switch feature/c-date-utils
Switched to branch 'feature/c-date-utils'
Your branch is up to date with 'origin/main'.
$ git stash pop
Already up to date.
On branch feature/c-date-utils
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	src/date_utils.py

nothing added to commit but untracked files present (use "git add" to track)
Dropped refs/stash@{0} (fe8cdf7e67ca7e8188a0bbe9e45e762cbbfb5029)
$ git status --short
?? src/date_utils.py
```

### 결과
- 작업 중이던 파일이 stash 에 보관됐다가 브랜치로 돌아와 그대로 복원됐다. 이어서 `is_weekend` 를 작성해 커밋했다.
- 주의: `-u` 를 빼면 아직 추적하지 않는 새 파일은 보관되지 않는다. `pop` 에서 충돌하면 stash 가 지워지지 않고 남는다.

### 왜 이 방법을 선택했는가
- "wip" 같은 의미 없는 커밋을 남기지 않고 브랜치를 오갈 수 있다.
<!-- STASH:END -->
