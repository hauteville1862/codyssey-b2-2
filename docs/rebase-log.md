# 히스토리 정리 기록 (보너스)

- 작성: 이나현(@Rara-rookie), 브랜치 `feature/b-contributing-review`
- push 전에 "PR 규칙"과 "리뷰 규칙" 두 커밋을 하나로 합쳤다. 원격에 올리기 전이라 히스토리 재작성이 다른 사람에게 영향을 주지 않는다.

## 정리 전
```text
$ git log --oneline -4
661854f docs: add review checklist and refine PR definition
b00ed7c docs: add code review rules to CONTRIBUTING
7d8d822 docs: add PR rules to CONTRIBUTING
1a81dfe Merge pull request #2 from hauteville1862/feature/a-text-utils
```

## 정리(`git rebase -i HEAD~3`, 두 번째 줄 pick → fixup)
```text
$ env GIT_SEQUENCE_EDITOR=perl -i -pe 's/^pick/fixup/ if $. == 2' git rebase -i HEAD~3
Rebasing (2/3)Rebasing (3/3)Successfully rebased and updated refs/heads/feature/b-contributing-review.
$ git log --oneline -3
0f16c3d docs: add review checklist and refine PR definition
8d458be docs: add PR rules to CONTRIBUTING
1a81dfe Merge pull request #2 from hauteville1862/feature/a-text-utils
```

## 비교
- 같은 문서의 인접한 두 절을 쓴 커밋이라 리뷰어 입장에서는 한 단위로 읽는 편이 쉽다.
- `fixup` 은 앞 커밋 메시지를 유지하고 뒤 커밋 메시지는 버린다. 메시지를 합치려면 `squash` 를 쓴다.
- 이미 push 한 브랜치를 rebase 하면 강제 push 가 필요하므로 팀 합의 없이 하지 않는다.
