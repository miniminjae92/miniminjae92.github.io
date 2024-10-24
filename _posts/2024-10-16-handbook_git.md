---
type: post
title: "Git Usage"
---

1. git init: Git 저장소 초기화
새로운 Git 저장소를 만들 때 사용.

```
git init
```

2. git clone: 저장소 복제
원격 저장소를 로컬로 복제할 때 사용. 클론 시 브랜치 체크아웃 신경 쓰기!
```
git clone <repository-url>
```
3. git add: 파일 스테이징
변경된 파일을 스테이징 영역에 추가할 때 사용.
```
git add <file-name>  # 또는 전체 파일 추가: git add .
```
4. git commit -m: 변경 사항 커밋
스테이징된 파일을 커밋할 때 사용.
```
git commit -m "Commit message"
```
5. git status: 현재 상태 확인
변경 사항, 스테이징 상태 등을 확인할 때 사용.
```
git status
```
6. git log: 커밋 히스토리 보기
프로젝트의 커밋 히스토리를 확인할 때 사용.
```
git log
git log --oneline
```
7. git branch: 브랜치 관련 작업
브랜치 목록 보기, 브랜치 생성 및 삭제할 때 사용.
```
git branch       # 브랜치 목록 보기
git branch <branch-name>    # 브랜치 생성
git branch -d <branch-name> # 브랜치 삭제
git branch -f <branch-name> <commit-hash>
git branch -f main HEAD~3
git branch -f feature-branch 123abc
```
8. git checkout: 브랜치나 커밋으로 이동
특정 브랜치나 커밋으로 체크아웃할 때 사용.
```
git checkout <branch-name>     # 브랜치 체크아웃
git checkout <commit-hash>     # 특정 커밋 체크아웃
git checkout HEAD^ 
git checkout HEAD~3 
git checkout main~2
```
10. git merge: 브랜치 병합
현재 체크아웃된 브랜치에 다른 브랜치를 병합할 때 사용.
```
git merge <branch-name>
```
11. git pull: 원격 저장소에서 최신 변경 사항 가져오기
원격 저장소의 최신 변경 사항을 가져와 병합.
```
git pull origin <branch-name>
```
12. git push: 로컬 커밋을 원격 저장소에 푸시
로컬의 커밋을 원격 저장소에 업로드할 때 사용.
```
git push origin <branch-name>
```
13. git rebase: 브랜치 재배치
현재 브랜치의 커밋을 다른 브랜치 위로 재배치할 때 사용.
```
git rebase <branch-name>
```
14. git reset: 커밋을 취소하고 되돌림
특정 커밋으로 브랜치를 되돌릴 때 사용. --soft, --hard 옵션을 조정해 파일 상태를 유지할지 결정.
```
git reset --hard <commit-hash>
git reset <commit-hash>
```
15. git revert: 특정 커밋을 되돌림
과거 커밋을 되돌리고, 되돌린 결과를 새로운 커밋으로 저장할 때 사용.
```
git revert <commit-hash>
```
16. Git 체리-픽 (Cherry-pick): 특정 커밋을 선택해서 다른 브랜치에 복사하는 명령어, 필요한 커밋만 선택적으로 적용 가능.
```
git cherry-pick <Commit1> <Commit2> <...>
```
16. git stash: 임시로 변경 사항 저장
현재 작업 중인 변경 사항을 임시로 저장하고, 나중에 다시 적용할 때 사용.
```
git stash      # 변경 사항 임시 저장
git stash pop  # 임시 저장한 변경 사항 복원
```

Rebase: 체크아웃된 브랜치의 커밋을 다른 브랜치 위로 옮기는 것. 결과적으로 히스토리가 깔끔해지고, 마치 다른 브랜치 위에서 작업한 것처럼 보입니다.

Merge: 체크아웃된 브랜치로 다른 브랜치의 변경 사항을 병합하는 것. 두 브랜치의 히스토리가 병합되고, 체크아웃된 브랜치에 병합 커밋이 추가됩니다.

정리 (Local vs Pushed):
git revert:

Local: 새로운 커밋을 생성하면서 안전하게 되돌림.
Pushed: 원격 저장소에 푸시된 커밋을 안전하게 되돌리면서 히스토리 보존. 협업에 적합.
git reset:

Local: 로컬에서 히스토리를 삭제하거나 수정할 때 안전하게 사용 가능.
Pushed: 푸시된 후에 사용하면 협업자와의 충돌을 일으킬 수 있으며, force push가 필요. 신중하게 사용해야 함.
결론:
로컬에서 작업할 때는 reset을 자유롭게 사용할 수 있지만, 원격에 푸시된 커밋에 대해선 revert를 사용하는 것이 더 안전하고 협업에 유리합니다.

git add -p: 변경된 파일의 부분(패치)을 선택적으로 스테이징할 수 있는 명령어.
