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
(작성 예정)
<!-- RESET:END -->

## 시나리오 3. `git revert` — 원격에 push 된 커밋 취소 (임유현)
<!-- REVERT:START -->
(작성 예정)
<!-- REVERT:END -->

## 시나리오 4. `git stash` / `git stash pop` — 작업 보관 후 전환 (박경내)
<!-- STASH:START -->
(작성 예정)
<!-- STASH:END -->
