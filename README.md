# 6주차 실습 — 팀 저장소에서 Pull Request 와 코드 리뷰

오늘부터 팀 저장소 하나를 세 사람이 같이 씁니다. 규칙은 하나입니다. **main 에 직접 커밋하지 않고, 모든 변경은 pull request(PR)로 들어갑니다.** 팀원이 리뷰하고 승인해야 머지할 수 있도록 GitHub 에 규칙(ruleset)도 겁니다.
막히면 맨 아래 **부록: 흔한 오류**를 먼저 보고, 그래도 안 되면 손을 드세요.

- **팀 저장소**: 팀원 한 명(A)의 계정에 `oss2026-teamNN` 하나. `NN` 은 두 자리 조 번호입니다(3조 → `oss2026-team03`).
- **확인 방법**: 팀 저장소의 PR·리뷰·이슈·커밋을 봅니다. 따로 제출하는 파일은 없습니다.
- **본인 노트북, 본인 GitHub 계정으로** 합니다. PR 과 리뷰는 GitHub 계정으로 누가 했는지가 기록됩니다. 한 노트북에 모여서 한 사람 계정으로 하면 그 사람 기록만 남습니다.
- 저장소 어디에도 이름·학번을 적지 않습니다. 팀원은 GitHub 아이디로만 적습니다.

---

## 역할 정하기: A · B · C

문제마다 누가 하는지가 정해져 있습니다. 시작하기 전에 팀에서 A · B · C 를 정합니다.

| 역할 | 누구 | 하는 문제 |
|---|---|---|
| **A** | 저장소 주인(owner). 수업에 온 사람 | [P0](problems/P0_setup.md) ~ [P5](problems/P5_for_c.md) (B 와 같이) |
| **B** | 수업에 온 두 번째 사람 | [P0](problems/P0_setup.md) ~ [P5](problems/P5_for_c.md) (A 와 같이) |
| **C** | 세 번째 사람 | [C1](problems/C1_join.md) ~ [C4](problems/C4_conflict.md) (혼자) |

- **세 명이 모두 왔으면**: A·B 가 [P0](problems/P0_setup.md) ~ [P5](problems/P5_for_c.md) 를 하는 동안 C 는 [C1](problems/C1_join.md) ~ [C4](problems/C4_conflict.md) 를 합니다. [C1](problems/C1_join.md) 은 [P0](problems/P0_setup.md) 의 초대가 끝나면, [C2](problems/C2_my_pr.md) 는 [P3](problems/P3_conflict.md) 이 끝나면, [C3](problems/C3_review.md) 은 [P5](problems/P5_for_c.md) 와 [C2](problems/C2_my_pr.md) 가 둘 다 끝나면, [C4](problems/C4_conflict.md) 는 [C3](problems/C3_review.md) 이 끝나면 시작합니다. **[C2](problems/C2_my_pr.md) 를 [C3](problems/C3_review.md) 보다 먼저** 해야 [C4](problems/C4_conflict.md) 의 충돌이 생깁니다.
- **두 명만 왔으면**: 온 두 사람이 A·B, 오지 못한 사람이 C 입니다. C 는 나중에 혼자 [C1](problems/C1_join.md) ~ [C4](problems/C4_conflict.md) 를 합니다. C 의 PR([C2](problems/C2_my_pr.md))은 A 나 B 가 승인해 줘야 머지되므로, A·B 는 C 의 리뷰 요청 알림을 기다렸다가 승인합니다. 승인은 [C4](problems/C4_conflict.md) 의 충돌 해결 전이든 후든 상관없습니다.
- **아무도 오지 못했으면**: 세 사람이 시간을 맞춰(만나거나 온라인으로) 같은 순서로 합니다.

[P0](problems/P0_setup.md) ~ [P5](problems/P5_for_c.md) 가 끝나면 팀 저장소에 필요한 것은 전부 갖춰집니다. [C1](problems/C1_join.md) ~ [C4](problems/C4_conflict.md) 는 A·B 가 [P2](problems/P2_first_pr.md) ~ [P4](problems/P4_issue.md) 에서 나눠 한 이슈 → PR → 리뷰 → 충돌 해결을 C 가 혼자 한 바퀴 도는 문제입니다.

---

## 문제

| # | 누가 | 문제 | 남는 것 |
|---|---|---|---|
| [P0](problems/P0_setup.md) | A, B | [팀 저장소 만들기](problems/P0_setup.md) | 저장소 `oss2026-teamNN`, 커밋 `docs: team table` |
| [P1](problems/P1_ruleset.md) | A, B | [main 보호하기 (ruleset)](problems/P1_ruleset.md) | ruleset `protect-main` |
| [P2](problems/P2_first_pr.md) | A, B | [첫 PR 과 리뷰](problems/P2_first_pr.md) | PR 2개: `.gitignore`(A), `.editorconfig`(B) |
| [P3](problems/P3_conflict.md) | A, B | [PR 충돌 풀기](problems/P3_conflict.md) | PR 2개: README 팀원 표에 각자 한 줄, 충돌 해결 머지 커밋 |
| [P4](problems/P4_issue.md) | A, B | [이슈를 PR 로 닫기](problems/P4_issue.md) | 이슈 1개, 그 이슈를 닫은 PR 1개 |
| [P5](problems/P5_for_c.md) | A | [C 가 리뷰할 PR 남기기](problems/P5_for_c.md) | 열려 있는 PR 1개: `CONTRIBUTING.md` + 표에 C 자리 (리뷰어 C) |
| [C1](problems/C1_join.md) | C | [초대 수락하고 이슈 만들기](problems/C1_join.md) | 이슈 1개: `팀원 표에 <C의 ID> 추가` |
| [C2](problems/C2_my_pr.md) | C | [내 PR 올리기](problems/C2_my_pr.md) | 열린 PR 1개: 팀원 표에 C 의 줄, `Closes #이슈` |
| [C3](problems/C3_review.md) | C | [팀원 PR 리뷰하고 머지](problems/C3_review.md) | P5 의 PR 에 C 의 줄 댓글·승인, 머지 |
| [C4](problems/C4_conflict.md) | C | [내 PR 의 충돌 풀고 머지](problems/C4_conflict.md) | C2 의 PR 에 충돌 해결 머지 커밋, 머지, C1 의 이슈 닫힘 |

쓰는 Git 명령은 지난주까지 나온 것뿐입니다: `clone`, `status`, `add`, `commit`, `checkout`(`-b`), `branch`(`-d`), `merge`, `log`, `reset`, `fetch`, `push`(`-u`), `pull`. 나머지는 전부 GitHub 화면(브라우저)에서 합니다.

## 끝날 때 갖춰져 있어야 하는 상태

팀 저장소 ([P0](problems/P0_setup.md) ~ [P5](problems/P5_for_c.md))
- `oss2026-teamNN` 이 A 계정에 Public 으로 있고, B·C 가 collaborator
- main 에 ruleset: PR 필수, 승인 1명, 머지 방식 Merge 만, bypass 목록 비어 있음
- main 에 `.gitignore`(`node_modules/` 포함), `.editorconfig`
- 머지된 PR 은 전부 작성자가 아닌 팀원의 승인을 받은 뒤 머지됨
- 첫 PR 이 머지된 뒤로 main 에 PR 없이 들어간 커밋이 없음
- [P3](problems/P3_conflict.md) 에서 main 을 내 브랜치에 머지해 충돌을 푼 커밋이 있음
- 이슈 하나가 PR 의 `Closes #번호` 로 닫힘
- main 의 어떤 파일에도 `<<<<<<<`, `=======`, `>>>>>>>` 줄이 없음

사람마다 (A, B, C 모두)
- 내가 만든 PR 하나 이상이 main 에 머지됨
- 다른 팀원의 PR 하나 이상에 내 리뷰(승인)가 있음
- C 는 추가로: [C1](problems/C1_join.md) 의 이슈가 C 의 PR 로 닫힘, C 의 PR 에 충돌을 푼 머지 커밋이 있음

---

## 부록: 흔한 오류

| 증상 | 원인 → 해결 |
|---|---|
| 초대 메일이 안 옴 / 저장소에 push 하면 `Permission ... denied` 또는 `403` | 초대를 아직 수락하지 않음 → `https://github.com/<A의 ID>/oss2026-teamNN/invitations` 를 열어 **Accept invitation** ([C1](problems/C1_join.md) 1번) |
| push 가 `GH013: Repository rule violations found for refs/heads/main` 으로 거부됨 | main 에 직접 push 함. ruleset 이 제대로 걸렸다는 뜻 → 커밋을 브랜치로 옮기기: `git branch <새 브랜치>` → `git reset --hard origin/main` → `git checkout <새 브랜치>` → `git push -u origin <새 브랜치>` 로 PR |
| 리뷰 화면에 **Approve** 가 회색 / `Pull request authors can't approve their own pull request` | 내 PR 은 내가 승인할 수 없음 → 팀원에게 리뷰 요청 (Reviewers) |
| **Merge pull request** 버튼이 회색, 위에 `Review required` | 아직 승인이 없음 → 팀원 승인을 기다림 |
| PR 에 `This branch has conflicts that must be resolved` | 다른 PR 이 같은 줄을 먼저 바꿈 → [P3](problems/P3_conflict.md) 의 9 ~ 15번 |
| `does not provide an export named '…'` | `courses.js` 에 함수를 안 넣었거나 이름 오타, 또는 `courses.js` 가 문법 오류로 안 읽힘 → `node check.js` 로 먼저 확인 |
| 머지 상자가 계속 `Checking for the ability to merge automatically…` | GitHub 이 아직 계산 중 → 1 ~ 2분 뒤 F5 |
| 체크박스가 `- [ ] - [ ]` 처럼 두 번 들어감 | Enter 뒤에 GitHub 이 `- [ ] ` 를 자동으로 넣어 줌 → 앞의 중복 부분을 지움 ([P2](problems/P2_first_pr.md) 8번) |
| 머지 뒤 파일에 `<<<<<<<` 가 남아 있음 | 마커를 안 지우고 커밋함 → 브랜치에서 고쳐 다시 커밋·push. 이미 머지됐으면 고치는 PR 을 새로 만듦 |
| 브랜치에서 `git push` 가 `has no upstream branch` | 그 브랜치를 처음 올림 → `git push -u origin <브랜치>` |
| Reviewers 목록에 팀원이 안 보임 | 팀원이 초대를 아직 수락하지 않음 → 수락 후 다시 |
| PR 오른쪽 Development 칸에 이슈가 안 보임 | `Closes #번호` 를 댓글에 썼거나 번호가 틀림 → 머지 **전에** PR 설명 오른쪽 위 `...` → **Edit** 로 설명을 고쳐 저장. 이슈는 손으로 닫지 않음 ([P4](problems/P4_issue.md) 10번) |
| GitHub 화면이 갑자기 VS Code 처럼 바뀜(주소가 `github.dev` 또는 `vscode.dev`) | 글 칸을 클릭하지 않은 채 `.` 키를 누름(GitHub 의 단축키) → 브라우저 뒤로 가기. 로그인 허용 창이 뜨면 **취소** |
| 커밋했더니 편집기가 열림 | `-m` 없는 commit, 머지는 원래 열립니다. VS Code 면 `Ctrl+S` 뒤 탭 닫기. Vim 이면 `Esc` → `:wq` Enter |


erwriuwroweueurio
