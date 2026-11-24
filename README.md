# C Study

WSL(Ubuntu) + gcc 환경에서 C 언어를 공부하며 정리한 기록

## 진도표

| # | 주제 | 상태 |
|---|---|---|
| 00 | [개발환경 구축](00-setup/) | ✅ |

> ⬜ 시작 전 · 🔄 진행 중 · ✅ 완료

## 개발 환경

| 항목 | 내용 |
|---|---|
| OS | Windows + WSL2 (Ubuntu) |
| 컴파일러 | gcc 15.2 (`build-essential`) |
| 디버거 | gdb |
| 에디터 | VS Code + WSL 확장 + C/C++ 확장 |

## 실행 방법

VS Code에서 `.c` 파일을 열어 둔 상태로 단축키를 누른다.

| 단축키 | 동작 |
|---|---|
| `Ctrl+Shift+B` | 컴파일 + 실행 (결과만 출력) |
| `F5` | 컴파일 + 디버깅 (중단점에서 정지) |

터미널에서 직접 컴파일할 때:

```bash
mkdir -p build
gcc -Wall -Wextra -g 00-setup/hello.c -o build/hello
./build/hello
```

| 옵션 | 의미 |
|---|---|
| `-Wall -Wextra` | 경고를 최대한 표시 (초기화 안 된 변수 등 실수 방지) |
| `-g` | 디버깅 정보 포함 (gdb·중단점 사용에 필요) |
| `-o` | 출력 실행 파일 이름 지정 |

## 폴더 구성

```
c-study/
├── .vscode/
│   ├── tasks.json    # 컴파일·실행 설정
│   └── launch.json   # 디버깅 설정
├── 00-setup/         # 주제별 폴더 (01-..., 02-... 로 추가)
│   ├── README.md
│   └── hello.c
└── build/            # 컴파일 결과물 (git 제외)
```

- 실행 파일은 `build/` 아래에 소스 폴더 구조 그대로 생성되므로 폴더마다 `main.c`가 있어도 겹치지 않는다.
- 커밋 메시지 형식: `폴더명: 한 내용` (예: `02-pointer: 포인터 산술 예제`)
