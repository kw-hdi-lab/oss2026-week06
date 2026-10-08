# C3. 팀원 PR 리뷰하고 머지 — C

A 가 [P5](P5_for_c.md) 에서 C 를 위해 열어 둔 PR(`docs: add contributing guide`)이 있습니다. C 가 리뷰하고 승인한 뒤 머지합니다. 승인하는 사람과 머지하는 사람이 같아도 됩니다. 규칙이 요구하는 것은 "작성자가 아닌 사람의 승인 1개" 입니다.

이 PR 은 `CONTRIBUTING.md` 를 추가하고, README 팀원 표에 C 의 자리를 `(C 가 정함)` 으로 미리 넣습니다. [C2](C2_my_pr.md) 에서 내가 같은 자리에 내 줄을 넣었으니, 이 PR 을 머지하고 나면 내 PR 에 충돌이 납니다. 그 충돌은 [C4](C4_conflict.md) 에서 풉니다.

이 문제에서 하는 것:
- 변경 보기 → 줄 댓글 → 승인 (브라우저)
- 머지 → 내 main 갱신 (브라우저 → 터미널)

## 리뷰하기 (브라우저)

1. 알림(오른쪽 위 종 모양)이나 **Pull requests** 탭에서 `docs: add contributing guide` PR 을 엽니다. **Conversation** 탭에서 A 가 쓴 설명을 먼저 읽습니다.
2. **Files changed** 탭을 엽니다. 파일이 둘입니다. `CONTRIBUTING.md` 는 줄이 전부 초록색(새로 추가된 줄)이고, `README.md` 는 표에 `(C 가 정함)` 한 줄이 추가되어 있습니다.
3. 내용을 읽고 댓글을 하나 이상 남깁니다. 줄 위에 마우스를 올리면 줄 번호 옆에 파란 **+** 가 나옵니다. 누르고, 댓글 칸을 클릭한 뒤 적고, **Start a review**.

   댓글은 구체적으로 씁니다. 어느 줄의 무엇을, 왜.
   - 좋은 예: `3번: push 전에 git status 로 확인하는 단계도 넣으면 좋겠습니다. 엉뚱한 파일이 같이 올라간 적이 있어서요.`
   - 좋은 예: `6번이 [P3](P3_conflict.md) 에서 한 방법과 같아서 이해가 쉬웠습니다.`
   - 피할 것: `좋아요`, `이상해요` 처럼 어느 줄인지, 왜인지 없는 댓글.
4. 오른쪽 위 초록색 **Submit review**(또는 **Review changes**) → 요약 한 줄 → **Approve** → **Submit review**.

   이번에는 고칠 점을 적었어도 **Approve** 로 냅니다. 이 PR 은 작은 문서이고, 고칠 점은 다음 PR 에서 반영해도 됩니다. 머지 전에 반드시 고쳐야 하는 문제라면 **Request changes** 를 고르는데, 그러면 작성자가 고쳐서 다시 push 할 때까지 머지가 막힙니다.

## 머지하고 정리 (브라우저 → 터미널)

5. **Conversation** 탭 아래 머지 상자가 초록 **Changes approved** 입니다. **Merge pull request** → **Confirm merge** → **Delete branch**.
6. 터미널에서 main 을 받습니다.
   ```
   git checkout main
   git pull
   ```
7. **확인**: `ls` 에 `CONTRIBUTING.md` 가 보이고, `cat README.md` 의 표 마지막 줄이 `| @<내 ID> | (C 가 정함) |` 입니다. GitHub 의 그 PR 페이지 기록에 내 아이디로 `approved these changes` 와 `merged commit … into main` 이 남아 있습니다.

---

[← 문제 목록](../README.md#문제) · [이전: C2](C2_my_pr.md) · [다음: C4](C4_conflict.md) · [부록: 흔한 오류](../README.md#부록-흔한-오류)
