# P5. C 가 리뷰할 PR 남기기 — A — `docs: add contributing guide`

C 도 다른 팀원의 PR 을 리뷰해 봐야 합니다. 그런데 [P2](P2_first_pr.md) ~ [P4](P4_issue.md) 의 PR 은 이미 A·B 가 서로 승인하고 머지했습니다. 그래서 A 가 PR 을 하나 더 열어 두고, **머지하지 않고 C 에게 남깁니다.** C 가 이 PR 을 리뷰하고 승인한 뒤 머지합니다([C3](C3_review.md)).

이 PR 은 README 팀원 표에 C 의 자리도 한 줄 미리 넣습니다. C 도 자기 PR 에서 같은 자리에 자기 줄을 넣기 때문에, C 가 이 PR 을 머지하는 순간 C 의 PR 에 충돌이 납니다. C 가 혼자서도 [P3](P3_conflict.md) 의 충돌 해결을 겪게 하려는 장치입니다([C4](C4_conflict.md)).

이 문제에서 하는 것:
- A: 팀 작업 방법을 적은 `CONTRIBUTING.md` 와 표의 C 자리 한 줄을 PR 로 올리고 C 에게 리뷰 요청
- A·B: 이 PR 은 승인하지도 머지하지도 않고 그대로 둠

## A: PR 올리기 (터미널, VS Code, 브라우저)

1. main 을 받고 브랜치를 만듭니다.
   ```
   git checkout main
   git pull
   git checkout -b contributing
   ```
2. VS Code 에서 저장소 맨 위에 `CONTRIBUTING.md` 를 새로 만들고 저장합니다. 이 저장소에 처음 들어온 사람이 읽을 작업 순서입니다.
   ```
   # 작업 방법

   1. `git checkout main` 과 `git pull` 로 main 을 최신으로 받는다.
   2. `git checkout -b <브랜치>` 로 브랜치를 만든다. 한 브랜치에는 한 가지 일만.
   3. 커밋하고 `git push -u origin <브랜치>`.
   4. GitHub 에서 PR 을 열고 Reviewers 에 팀원 한 명을 지정한다.
   5. 승인을 받으면 작성자가 머지하고 브랜치를 지운다.
   6. 충돌이 나면 내 브랜치에서 `git fetch`, `git merge origin/main` 으로 푼다.
   ```
3. `README.md` 를 열고 팀원 표의 **마지막 줄(B 의 줄) 바로 아래**에 C 의 자리를 한 줄 넣고 저장합니다. 맡은 일은 비워 두는 뜻으로 `(C 가 정함)` 이라고 적습니다.
   ```
   | GitHub | 맡은 일 |
   |---|---|
   | @<A의 ID> | 화면 구성 |
   | @<B의 ID> | 서버 |
   | @<C의 ID> | (C 가 정함) |
   ```
4. 두 파일을 커밋하고 올립니다.
   ```
   git add CONTRIBUTING.md README.md
   git commit -m "docs: add contributing guide"
   git push -u origin contributing
   ```
5. 브라우저에서 PR 을 엽니다. 설명에 C 를 부르는 줄을 넣습니다.
   ```
   팀 작업 순서를 CONTRIBUTING.md 로 정리하고, 팀원 표에 C 자리를 넣었습니다.

   @<C의 ID> 리뷰 부탁합니다. 승인한 뒤 머지까지 해 주세요.
   ```
6. 오른쪽 **Reviewers** 에서 C 를 지정합니다. C 가 아직 초대를 수락하지 않았으면 목록에 나오지 않습니다. 그때는 5번의 `@<C의 ID>` 만으로 충분합니다. C 에게 알림이 갑니다.
7. **Create pull request**.

## 그대로 두기

8. **이 PR 은 A·B 가 승인하지 않습니다.** B 가 승인하면 A 가 머지할 수 있게 되고, C 가 리뷰할 PR 이 사라집니다.
9. **확인**: **Pull requests** 탭의 Open 목록에 이 PR 하나가 남아 있고, 머지 상자에 **Review required** 가 보이면 됩니다. 세 명이 다 온 팀은 C 가 [C2](C2_my_pr.md) 를 끝낸 뒤 [C3](C3_review.md) 을 합니다. C 가 오지 않은 팀은 C 가 나중에 합니다.

[P0](P0_setup.md) ~ P5 가 끝나면 팀 저장소에 필요한 것은 다 갖춰졌습니다. [끝날 때 갖춰져 있어야 하는 상태](../README.md#끝날-때-갖춰져-있어야-하는-상태)의 "팀 저장소" 항목을 GitHub 화면에서 하나씩 확인합니다.

---

[← 문제 목록](../README.md#문제) · [이전: P4](P4_issue.md) · [다음: C1](C1_join.md) · [부록: 흔한 오류](../README.md#부록-흔한-오류)
