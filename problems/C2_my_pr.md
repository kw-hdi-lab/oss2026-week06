# C2. 내 PR 올리기 — C — `docs: add <ID> to team table`

README 팀원 표에 C 의 줄을 PR 로 넣습니다. main 에는 직접 push 할 수 없으니(ruleset) 브랜치 → PR 순서로 갑니다. PR 설명에 [C1](C1_join.md) 에서 만든 이슈 번호를 `Closes #번호` 로 적어, 이 PR 이 머지되면 이슈가 저절로 닫히게 합니다.

**이 문제에서는 PR 을 열기만 하고 머지하지 않습니다.** 승인은 팀원이 해야 하고(내 PR 은 내가 승인할 수 없음), 머지는 [C4](C4_conflict.md) 에서 합니다. PR 을 연 다음 바로 [C3](C3_review.md) 으로 갑니다.

이 문제에서 하는 것:
- 브랜치에서 표에 내 줄 추가 → push (터미널, VS Code)
- PR 열기, `Closes #번호`, 리뷰 요청 (브라우저)

## 브랜치에서 커밋하고 push (터미널, VS Code)

1. main 을 최신으로 받고 브랜치를 만듭니다.
   ```
   git checkout main
   git pull
   git checkout -b row-<내 ID>
   ```
2. VS Code 에서 `README.md` 를 열고, 팀원 표의 **마지막 줄(B 의 줄) 바로 아래**에 내 줄을 넣고 저장합니다. 표 아래에 `## 규칙` 절이 있으면 그 위, 표 안에 넣습니다.
   ```
   | GitHub | 맡은 일 |
   |---|---|
   | @<A의 ID> | 화면 구성 |
   | @<B의 ID> | 서버 |
   | @<내 ID> | 테스트 |
   ```
   **Ctrl+Shift+V** 로 미리보기를 열어 표가 세 줄로 보이는지 확인합니다. 내 줄과 B 의 줄 사이에 빈 줄이 있으면 표가 거기서 끊겨 내 줄이 글자 그대로 보입니다.
3. 커밋하고 브랜치를 올립니다. 처음 올리는 브랜치라 `-u origin <브랜치>` 를 붙입니다.
   ```
   git commit -am "docs: add <내 ID> to team table"
   git push -u origin row-<내 ID>
   ```
   main 으로 push 하면 `GH013 ... Changes must be made through a pull request` 로 거부됩니다. 브랜치로 올렸는지 확인합니다.

## PR 열고 리뷰 요청 (브라우저)

4. 저장소 페이지의 노란 띠 **Compare & pull request** 를 누릅니다. 맨 위가 **base: main ← compare: row-<내 ID>** 인지 확인합니다.
5. 설명에 한 줄, 이슈 번호, 리뷰어 호출을 적습니다. `#5` 자리에는 [C1](C1_join.md) 10번의 번호를 씁니다.
   ```
   팀원 표에 제 줄을 추가합니다.

   Closes #5

   @<A의 ID> 리뷰 부탁합니다.
   ```
   **Preview** 에서 `#5` 와 `@아이디` 가 링크로 보이는지 확인합니다.
6. 오른쪽 **Reviewers** 에서 A 나 B 를 지정하고 **Create pull request**. 머지 상자에 **Review required** 가 보이면 정상입니다. F5 를 누르면 오른쪽 **Development** 칸에 [C1](C1_join.md) 의 이슈가 연결되어 보입니다.
7. 팀원에게 PR 주소를 보내 승인을 부탁합니다. GitHub 알림은 놓치기 쉬우니 팀 단톡방에도 한 줄 남깁니다.
8. **확인**: **Pull requests** 탭의 Open 목록에 내 PR 과 A 의 `docs: add contributing guide` PR 이 둘 다 있으면 됩니다. 승인을 기다리지 말고 [C3](C3_review.md) 으로 갑니다.

---

[← 문제 목록](../README.md#문제) · [이전: C1](C1_join.md) · [다음: C3](C3_review.md) · [부록: 흔한 오류](../README.md#부록-흔한-오류)
