# 00. 개발환경 구축

## 목표
Windows에서 WSL(Ubuntu)을 설치하고, VS Code에서 C 파일을 단축키로 컴파일·실행·디버깅한다.

## 설치 과정
1. PowerShell(관리자)에서 `wsl --install` → 재부팅 → Ubuntu 사용자 생성
2. 컴파일러·디버거 설치
   ```bash
   sudo apt update && sudo apt install -y build-essential gdb
   ```
3. VS Code에 **WSL** 확장 설치 → `Connect to WSL`
4. WSL 쪽에 **C/C++** 확장 설치 (`Install in WSL: Ubuntu`)
5. `.vscode/tasks.json`, `launch.json` 작성 → `Ctrl+Shift+B` / `F5`로 실행 확인
6. GitHub CLI 설치 후 `gh auth login`으로 WSL에서 push 가능하게 설정

## 막힌 점

### 1. `stdio.h: No such file or directory`
- 원인: `apt install gcc`만 하면 컴파일러만 설치되고 C 표준 헤더(`libc6-dev`)가 빠질 수 있음
- 해결: `build-essential` 설치 (gcc + 표준 헤더 + make 포함)

### 2. F5를 누르면 디버거 목록에 Node.js만 나옴
- 원인: C/C++ 확장이 Windows 쪽에만 있고 WSL 쪽에 설치되지 않음
- 해결: 확장 탭에서 `Install in WSL: Ubuntu`로 설치

### 3. 실행 후 `[1] + Done "/usr/bin/gdb" ...` 메시지 출력
- 원인: F5는 gdb를 거쳐 실행하므로 셸이 작업 종료 메시지를 출력함
- 해결: 결과만 볼 때는 디버거 없이 컴파일+실행하는 task를 만들어 `Ctrl+Shift+B`로 실행

### 4. `apt install gh` 실패 (`Unable to locate package gh`)
- 원인: 사용 중인 Ubuntu 기본 저장소에서 gh 패키지를 찾지 못함
- 해결: GitHub 공식 apt 저장소를 등록한 뒤 설치

### 5. `gh auth login` 중 브라우저가 열리지 않음
- 원인: WSL Interop(리눅스에서 Windows 프로그램 실행 기능)이 비활성화 상태
- 해결: Windows 브라우저에서 `github.com/login/device`에 직접 접속해 코드 입력

## 확인 문제
<details>
<summary>Q1. 컴파일과 링크는 각각 무엇을 하는 단계인가?</summary>

(답 작성)
</details>

<details>
<summary>Q2. <code>-g</code> 옵션 없이 컴파일하면 디버깅할 때 어떤 차이가 있나?</summary>

(답 작성)
</details>
