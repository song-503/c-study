# C Study

C 언어 공부 기록

## 진도표

| # | 주제 | 상태 |
|---|---|---|
| 01 | [기초 / 개발환경](01-basics/) | ✅ |

> ⬜ 시작 전 · 🔄 진행 중 · ✅ 완료

## 개발 환경
- Windows + WSL (Ubuntu)
- gcc 15.2 / gdb
- VS Code (WSL 확장 + C/C++ 확장)

## 실행 방법
| 키 | 동작 |
|---|---|
| `Ctrl+Shift+B` | 현재 파일 컴파일 + 실행 |
| `F5` | 현재 파일 컴파일 + 디버깅 (중단점 사용) |

실행 파일은 `build/` 폴더에 생성되며 레포에는 올리지 않는다.

터미널에서 직접 컴파일할 때:
```bash
gcc -Wall -Wextra -g 01-basics/hello.c -o build/hello
./build/hello
```

## 폴더 구성
주제별로 폴더를 나누고, 각 폴더에 소스 파일을 둔다.
```
c-study/
├── .vscode/       # 빌드·디버깅 설정
├── 01-basics/
│   └── hello.c
└── build/         # 컴파일 결과 (git 제외)
```
