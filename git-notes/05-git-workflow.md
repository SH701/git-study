# Git 협업 워크플로우

## 1. 기본 개념

### Repository (저장소)

-**Original Repository**: 원본 프로젝트 저장소 -**Forked Repository**: 내가 복사해온 저장소 -**Local Repository**: 내 컴퓨터에 있는 저장소

### Remote 이름

-**origin**: 내 fork된 저장소를 가리키는 이름 (기본 값) -**upstream**: 원본 저장소를 가리키는 이름 (직접 추가 해야 함)

---

### Fork (포크)

- GitHub 웹사이트에서 원본 저장소를 내 계정으로 복사

### Clone (클론)

- Fork한 저장소를 내 컴퓨터로 다운로드

### Issue (이슈)

- 프로젝트가 해야 하는데 아직 하지 않은 일이나, 사람들이 발견한 문제나 버그 같은 것을 기록하는 것

### Milestone (마일스톤)

- 버전을 올릴 때 필요한 것들을 따로 리스트로 모아두는 것

### Pull Request (PR)

- 내가 작업한 변경사항을 원본 저장소에 병합해달라고 요청하는 것
- 코드 리뷰와 토론을 거쳐 승인되면 병합됨

### PR 상태

-**Open**: 검토 중 -**Merged**: 병함됨 -**Closed**: 거절되거나 취소됨

## Pull Request 과정

### 1. Fork

Upstream Repository(원본 리포지토리)를 자신의 저장소로 fork

### 2. Clone, Remote설정 (git clone 깃URL)

fork해온 리포지토리를 로컬 저장소로 Clone

### 3. Branch 생성 (git checkout -b 브랜치명)

클론해온 프로젝트의 코드를 추가, 수정할 때 브랜치를 생성해서 작업할 수 있음.

### 4. 수정 작업 후 add, commit, push

작업 완료 후 add, commit, push를 통해 해당 코드를 원격 저장소로 푸시

### 5. Pull Request 생성

원본 리포지토리에서 New pull request를 통해 Pull Request 생성

### 6. Merge Pull Request

해당 리포지토리의 관리자는 코드의 변경 사항을 확인 후, Merge여부를 결정

### 7. Merge 이후 동기화 및 Fork 및 Branch 삭제

Merge가 완료되면 로컬에 작성한 코드와 원본의 코드를 병합하고 최신의 상태를 유지하게 위해 동기화

## 추가 학습 자료

- [GitHub Fork 공식 문서](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks)
- [오픈 소스 프로젝트에서 협업하는 방법](https://www.tomasbeuzen.com/post/git-fork-branch-pull)
