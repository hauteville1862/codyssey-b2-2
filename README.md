# 코디세이 깃플로우 3조 — Git 협업 연습 저장소

3인 팀이 GitHub Flow 로 이슈 → 브랜치 → PR → 리뷰 → 병합 흐름과 충돌 해결, Git 트러블슈팅을 연습한 저장소다.

## 팀원

| 이름 | GitHub | 맡은 일 |
|---|---|---|
| 임유현 | @hauteville1862 | 저장소·보호 규칙, 문자열 유틸, 브랜치·커밋 규칙, 제출물 인덱스 |
| 이나현 | @Rara-rookie | 수학 유틸, PR·리뷰 규칙, 충돌 #1 해결 |
| 박경내 | @datecoco | 날짜 유틸, 충돌 대응 흐름, 충돌 #2 해결 |

## 왜 GitHub Flow 인가

1. main 하나만 항상 동작하는 상태로 두고 모든 작업을 짧은 feature 브랜치에서 하므로 3인 팀이 지키기 쉽다.
2. 모든 변경이 PR 과 리뷰를 거쳐 main 에 들어가 누가 무엇을 왜 바꿨는지 기록이 남는다.
3. 정해진 릴리스 주기가 없어 develop·release 브랜치를 따로 두는 Git Flow 는 이 규모에 과하다.

## 결과물: 팀원별 유틸 함수 모음

| 모듈 | 작성자 | 함수 | 사용 예시 |
|---|---|---|---|
| `src/text_utils.py` | 임유현 | slugify, truncate | `slugify("Hello Git Flow")` → `'hello-git-flow'` |
| `src/math_utils.py` | 이나현 | clamp, mean | `clamp(15, 0, 10)` → `10` |
| `src/date_utils.py` | 박경내 | days_between, is_weekend | `days_between("2026-09-01", "2026-09-15")` → `14` |

함수별 예시는 docstring 에 있고 `python -m doctest -v src/<모듈>.py` 로 확인한다.

## 문서

- [협업 규칙](docs/CONTRIBUTING.md)
- [충돌 해결 기록](docs/conflict-resolution.md)
- [Git 트러블슈팅 기록](docs/troubleshooting-log.md)
- [용어집](docs/reference/glossary.md)
- [제출물 인덱스](SUBMISSION.md)
