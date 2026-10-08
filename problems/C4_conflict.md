# C4. 내 PR 의 충돌 풀고 머지 — C

[C3](C3_review.md) 에서 머지한 PR 이 README 팀원 표의 같은 자리를 바꿨습니다. 그래서 [C2](C2_my_pr.md) 에서 연 내 PR 에 충돌이 나 있습니다. [P3](P3_conflict.md) 에서 B 가 한 것과 같은 방법으로, 내 브랜치에서 풉니다. 풀고 나서 팀원 승인을 받아 머지하면 [C1](C1_join.md) 의 이슈가 저절로 닫힙니다.

이 문제에서 하는 것:
- 충돌 확인 (브라우저)
- 내 브랜치에서 `fetch` → `merge origin/main` → 해결 → 커밋 → push (터미널, VS Code)
- 승인 받고 머지 → 이슈가 닫혔는지 확인 (브라우저)

## 충돌 확인 (브라우저)

1. 내 PR([C2](C2_my_pr.md)) 페이지를 열고 새로 고칩니다. 머지 상자에 **This branch has conflicts that must be resolved**, 그 아래 충돌 파일 `README.md` 가 보입니다. Merge 버튼은 회색입니다.

   ![This branch has conflicts that must be resolved](../images/pr_conflict.png)

## 내 브랜치에서 충돌 풀기 (터미널, VS Code)

2. 내 브랜치로 옮깁니다. [C3](C3_review.md) 에서 main 으로 옮겨 왔기 때문입니다.
   ```
   git checkout row-<내 ID>
   ```
3. GitHub 의 최신 상태를 받아옵니다. 받아오기만 하고 합치지는 않습니다.
   ```
   git fetch
   ```
4. **main 을 내 브랜치에 합칩니다.** 내 브랜치에 main 의 새 커밋을 가져오는 방향입니다.
   ```
   git merge origin/main
   ```
   `CONFLICT (content): Merge conflict in README.md` 가 나면 맞게 된 것입니다.
5. VS Code 에서 `README.md` 를 엽니다. 표 아래가 이렇게 되어 있습니다.
   ```
   | @<B의 ID> | 서버 |
   <<<<<<< HEAD
   | @<내 ID> | 테스트 |
   =======
   | @<내 ID> | (C 가 정함) |
   >>>>>>> origin/main
   ```
   위쪽(`HEAD`)이 내 브랜치, 아래쪽이 main([C3](C3_review.md) 에서 머지한 A 의 PR)입니다. 같은 자리를 두 사람이 다르게 적었으니 하나를 고릅니다. 이번에는 **내 줄을 남깁니다.** 마커 세 줄(`<<<<<<<`, `=======`, `>>>>>>>`)과 `(C 가 정함)` 줄을 지우고 저장합니다.
   ```
   | @<B의 ID> | 서버 |
   | @<내 ID> | 테스트 |
   ```
6. 마커가 남지 않았는지 확인합니다. 아무것도 안 나와야 합니다.
   ```
   git grep -n -e "<<<<<<<" -e ">>>>>>>"
   ```
7. 해결을 알리고 머지 커밋을 만듭니다. 편집기가 `Merge remote-tracking branch 'origin/main' into row-<내 ID>` 메시지와 함께 열리면 그대로 저장하고 닫습니다.
   ```
   git add README.md
   git commit
   ```
8. 브랜치를 다시 올립니다. 이미 `-u` 로 연결된 브랜치라 그냥 `push` 면 됩니다.
   ```
   git push
   ```

## 승인 받고 머지 (브라우저 → 터미널)

9. PR 페이지를 새로 고칩니다. **Commits** 탭에 방금 만든 머지 커밋이 추가되어 있고, 충돌 표시가 사라졌습니다. 한동안 `Checking for the ability to merge automatically…` 만 보이면 1 ~ 2분 뒤 F5 를 누릅니다.
10. 팀원이 아직 승인하지 않았으면 머지 상자에 **Review required** 가 보입니다. 팀원에게 "충돌 풀었으니 승인 부탁" 이라고 알리고 기다립니다. 이미 승인했으면 그 승인은 그대로 남아 있습니다.
11. 머지 상자가 초록 **Changes approved** 가 되면 **Merge pull request** → **Confirm merge** → **Delete branch**.
12. 터미널에서 main 을 갱신하고 브랜치를 지웁니다.
    ```
    git checkout main
    git pull
    git branch -d row-<내 ID>
    ```
13. **확인**
    - GitHub 저장소 첫 화면 README 의 팀원 표에 세 줄이 있고, 내 줄의 맡은 일이 `(C 가 정함)` 이 아니라 내가 적은 것입니다. 마커는 없습니다.
    - **Issues** 탭 → **Closed** 에 [C1](C1_join.md) 의 이슈가 있고, 기록에 `closed this as completed in #…` 으로 내 PR 번호가 남아 있습니다.
    - `git log --oneline --graph -6` 에 `Merge remote-tracking branch 'origin/main' into row-<내 ID>` 가 보입니다.

[C1](C1_join.md) ~ C4 가 끝나면 C 의 몫은 끝입니다. [끝날 때 갖춰져 있어야 하는 상태](../README.md#끝날-때-갖춰져-있어야-하는-상태)의 "사람마다" 항목을 GitHub 화면에서 확인합니다.

---

[← 문제 목록](../README.md#문제) · [이전: C3](C3_review.md) · [부록: 흔한 오류](../README.md#부록-흔한-오류)
