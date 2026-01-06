# Git 명령어 정리

## 1. 기본 설정 (최초 1회)

```bash
# 사용자 이름 설정
git config --global user.name "Your Name"

# 이메일 설정
git config --global user.email "your.email@example.com"
```

---

## 2. 저장소 시작하기

```bash
# 현재 폴더를 Git 저장소로 만들기
git init

# 원격 저장소 복제
git clone <저장소URL>
```

---

## 3. 기본 작업 흐름

```bash
# 1. 상태 확인
git status

# 2. 파일 추가 (Staging Area에)
git add .                    # 모든 파일
git add 파일명.txt           # 특정 파일

# 3. 커밋 (저장)
git commit -m "커밋 메시지"

# 4. 원격 저장소에 업로드
git push origin main
```

### 커밋 메시지 컨벤션

#### 타입 종류
```
feat: 새로운 기능 추가
fix: 버그 수정
docs: 문서 수정
style: 코드 포맷팅 (기능 변경 없음)
refactor: 코드 리팩토링
test: 테스트 코드
chore: 빌드, 패키지 설정 등
```

#### 좋은 예시
```bash
git commit -m "feat: 로그인 기능 추가"
git commit -m "fix: 회원가입 버튼 오류 수정"
git commit -m "docs: README에 설치 방법 추가"
```

#### 나쁜 예시
```bash
git commit -m "수정"
git commit -m "aaa"
git commit -m "버그 고침"
```

---

## 4. 브랜치 관리

```bash
# 브랜치 목록 보기
git branch

# 새 브랜치 생성 + 이동 (한 번에)
git checkout -b feature/login

# 브랜치 이동
git checkout main
git switch main

# 브랜치 병합 (현재 브랜치에 다른 브랜치 합치기)
git merge feature/login

# 브랜치 삭제
git branch -d feature/login
```

---

## 5. 원격 저장소 관리

### 기본 명령어

```bash
# 원격 저장소 확인
git remote -v

# 원격 저장소 연결
git remote add origin <저장소URL>

# 원격 저장소 추가 (upstream)
git remote add upstream [URL]

# 원격 저장소 제거
git remote remove upstream
```

### Push / Pull / Fetch

```bash
# Push (업로드)
git push origin main

# Fetch (다운로드만)
git fetch origin main
git fetch upstream

# Pull (다운로드 + 병합)
git pull origin main
git pull upstream main

# Merge (병합)
git merge origin/main
```

---

## 6. 히스토리 확인

```bash
# 커밋 히스토리 보기
git log

# 간단하게 한 줄로
git log --oneline

# 그래프로 보기
git log --oneline --graph --all

# HEAD의 이동 기록 보기
git reflog
```

> **참고**: `git log`는 "무엇을 만들었나", `git reflog`는 "무엇을 했나"를 보여줍니다.

---

## 7. 변경사항 확인

```bash
# 작업 디렉토리의 변경사항 확인
git diff

# Staging Area의 변경사항 확인
git diff --staged
```

---

## 8. 변경사항 되돌리기

```bash
# add 취소 (staging → working directory)
git restore --staged 파일명

# 파일 변경사항 취소 (staging 전)
git restore 파일명

# 직전 커밋 취소 (변경사항은 유지)
git reset HEAD~1

# 병합 취소
git merge --abort
```

---

## 9. 충돌 해결 과정

```bash
# 1. merge 시도
git merge feature/login
# → CONFLICT 발생!

# 2. 충돌 파일 확인
git status

# 3. 충돌 파일 열어서 수동 수정
# (<<<<<<<, =======, >>>>>>> 표시 해결)

# 4. 해결된 파일 추가
git add .

# 5. 커밋으로 병합 완료
git commit
```

---

## 10. 작업 임시 저장 (Stash)

```bash
# 현재 작업 임시 저장
git stash

# 저장 목록 보기
git stash list

# 가장 최근 저장 불러오기
git stash pop

# 특정 stash 불러오기
git stash apply stash@{0}

# stash 삭제
git stash drop stash@{0}

# 모든 stash 삭제
git stash clear
```

---

## 용어 정리

| 용어 | 설명 |
|------|------|
| **Fork** | 다른 사람의 저장소를 내 계정으로 복사 |
| **Clone** | 원격 저장소를 로컬로 다운로드 |
| **Origin** | 내가 fork한 저장소 (기본 remote 이름) |
| **Upstream** | 원본 저장소 (직접 추가하는 remote) |
| **Pull Request (PR)** | 변경사항 병합 요청 |
| **Merge** | 브랜치 병합 |
| **Fetch** | 원격 저장소의 변경사항 가져오기 (병합 X) |
| **Pull** | Fetch + Merge |
| **Push** | 로컬 변경사항을 원격에 업로드 |
| **Stash** | 작업 중인 변경사항을 임시로 저장 |
