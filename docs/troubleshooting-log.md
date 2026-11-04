# Troubleshooting Log

팀 전체가 네 가지 시나리오를 실제로 수행하고 명령과 출력을 그대로 기록한다.

## 시나리오 1. `git commit --amend` — 최근 커밋 메시지 수정 (임유현)
<!-- AMEND:START -->
(작성 예정)
<!-- AMEND:END -->

## 시나리오 2. `git reset --soft HEAD~1` — 로컬 커밋 취소, 변경 유지 (이나현)
<!-- RESET:START -->
(작성 예정)
<!-- RESET:END -->

## 시나리오 3. `git revert` — 원격에 push 된 커밋 취소 (임유현)
<!-- REVERT:START -->
(작성 예정)
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
