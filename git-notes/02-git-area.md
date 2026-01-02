# Git Area (영역) 정리

## Area란?

파일이 위치할 수 있는 **작업 공간/영역**

## Git의 3가지 주요 영역

### 1. Working Directory (작업 디렉토리)

- 실제로 파일을 수정하는 공간
- 내 컴퓨터의 프로젝트 폴더

### 2. Staging Area (스테이징 영역)

- `git add` 명령으로 파일을 올리는 **대기실**
- commit 하기 전에 "이 파일일들을 commit에 포함시킬거야" 하고 준비하는 곳

### 3. Repository (저장소)

- `git commit`으로 최종 저장되는 곳
- **.git** 폴더 안에 저장됨
- 프로젝트의 전체 히스토리가 보관되는 영역

## 흐름도

```
Working Directory
    ↓ (git add)
Staging Area
    ↓ (git commit)
Local Repository (.git 폴더) ← push 전까지 여기 있음!
    ↓ (git push)
Remote Repository (GitHub 등)
```

## 비유로 이해하기

- **Working Directory**: 책상 위 (작업 중인 서류들)
- **Staging Area**: 서류 정리함 (제출할 서류만 골라놓음)
- **Repository**: 서류 보관함 (최종 제출/보관된 서류들)
