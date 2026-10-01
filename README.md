# KPC 금융 데이터 분석 수업 자료

2026년 10월 6~8일 · 20시간 과정의 수강생 실습 자료입니다.

[수업 안내](https://www.slog.gg/p/14880) · [교시별 수업 자료](https://www.slog.gg/p/14891)

## 데이터 실습 시점에 다운로드하기

1교시 환경 준비는 [첫 교시 안내](https://www.slog.gg/p/14892)에 따라 빈 실습 폴더에서 시작합니다. 이 ZIP은 환경 준비의 선행 조건이 아닙니다. 1일차 7교시 Titanic 실습에서 제공 데이터를 처음 읽을 때 내려받습니다. 파일 저장·읽기 기초 예제는 직접 만든 데이터로 진행합니다.

1. [수업 자료 ZIP 다운로드](https://github.com/jhs512/kpc-finance-course/releases/latest/download/kpc-finance.zip)를 누릅니다. GitHub 로그인은 필요하지 않습니다.
2. Windows 탐색기에서는 ZIP의 **모두 압축 풀기**를 선택합니다. macOS Finder에서는 ZIP을 더블 클릭하면 같은 위치에 압축이 풀립니다. ZIP 안에서 직접 실행하지 않습니다.
3. Windows는 압축 안의 `kpc-finance` 폴더를 `C:\kpc-finance-data`, macOS는 사용자 홈의 `~/kpc-finance-data`에 이름을 바꿔 둡니다. 1교시의 빈 환경 폴더와 분리합니다. 이 폴더를 열었을 때 `pyproject.toml`, `uv.lock`, `.python-version`, `raw`, `practice`가 바로 있어야 합니다. 1교시 폴더와 이름이 같으면 덮어쓰지 말고 다른 영문 폴더 이름을 사용하고 아래 경로도 맞춥니다.
4. Windows PowerShell에서 실제 폴더로 이동한 뒤 아래 명령을 실행합니다. CMD를 사용할 때 폴더 이동 명령은 `cd /d C:\kpc-finance-data`입니다.

```powershell
cd C:\kpc-finance-data
uv sync --locked
uv run --locked python -m ipykernel install --user --name kpc-finance-data --display-name "Python (kpc-finance-data)"
uv run --locked jupyter notebook
```

macOS는 **터미널**(zsh 또는 bash)에서 실행합니다. `~`는 사용자 홈이며 `C:` 드라이브 경로를 사용하지 않습니다.

```bash
cd ~/kpc-finance-data
uv sync --locked
uv run --locked python -m ipykernel install --user --name kpc-finance-data --display-name "Python (kpc-finance-data)"
uv run --locked jupyter notebook
```

uv가 없으면 [uv 공식 설치 안내](https://docs.astral.sh/uv/getting-started/installation/)를 먼저 따릅니다. 이 배포 자료에서는 `uv init`이나 `uv add`를 다시 실행하지 않습니다. Python과 패키지를 최초로 내려받으므로 인터넷이 필요합니다. `.venv`는 각 PC에서 새로 만들어집니다.

5. 브라우저가 열리면 `practice` → `periods`에서 현재 교시 Notebook을 엽니다. Titanic 첫 실습은 `d1-p07-08.ipynb`입니다. Kernel 선택/변경 메뉴에서 **Python (kpc-finance-data)**를 선택합니다. 새 Notebook을 직접 만들 때도 자료 폴더의 최상위에서 같은 Kernel을 선택합니다. 1교시의 **Python (kpc-finance-uv)**, Anaconda의 **Python (kpc-finance-conda)**와 구분합니다. 배포 Notebook의 기본 표시가 Python 3이면 그대로 믿지 말고 아래 실행 파일을 확인합니다.
6. Python Kernel에서 `import sys; print(sys.executable)`를 실행해 Windows는 `.venv\Scripts\python.exe`, macOS는 `.venv/bin/python`을 가리키는지 확인합니다. `from pathlib import Path; print(Path.cwd())`로 자료 위치도 확인합니다. 제공 데이터를 쓰는 교시는 첫 셀에서 `raw`가 있는 자료 폴더를 찾습니다. 환경 준비와 직접 데이터 생성 교시는 `raw`를 요구하지 않습니다. `uv run`에서는 수동 환경 활성화가 필요 없습니다.
7. Windows와 macOS 모두 **Shift+Enter**로 위에서 아래로 실행합니다. 저장은 Windows **Ctrl+S**, macOS **Cmd+S** 또는 저장 버튼을 사용합니다. Kernel 메뉴에서 재시작하고 **Run All**로 전체 재실행합니다. 실행 중인 셀 중단은 Kernel의 **Interrupt**를 사용합니다. 서버 종료는 PowerShell/터미널에서 두 OS 모두 **Ctrl+C** 후 종료 확인에 응답합니다.

Python 경로는 `Path("raw/기존강사 수업자료/titanic.xlsx")`처럼 `/`로 쓰면 두 OS에서 사용할 수 있습니다. 폴더·파일·컬럼의 대소문자와 공백을 그대로 유지합니다. 한글 CSV는 저장 인코딩과 읽기 인코딩을 맞춥니다. 현재 예제의 UTF-8 CSV는 macOS에서도 UTF-8로 읽습니다.

## 포함된 자료

- 교시별 Notebook 12개(실행 출력 초기화)
- 검증된 환경 설정 및 잠금 파일 3개
- Titanic, 익명 신용카드 부도 데이터, 삼성전자 과거 주가 CSV

기존 원자료의 경로와 값은 수업 설명에 맞춰 유지합니다. 교안은 데이터 분석 연습용이며 금융 예측의 정확도를 보장하지 않습니다. 라이브 웹 수집은 외부 응답에 따라 실패할 수 있어 제공 파일로 기본 실습을 진행합니다.

## 공식 사용 안내

- [uv 설치](https://docs.astral.sh/uv/getting-started/installation/)
- [uv 프로젝트 환경 및 명령 실행](https://docs.astral.sh/uv/guides/projects/)
- [macOS에서 ZIP 압축 풀기](https://support.apple.com/guide/mac-help/zip-and-unzip-files-and-folders-on-mac-mchlp2528/mac)
- [Jupyter Notebook 사용](https://jupyter-notebook.readthedocs.io/en/stable/notebook.html)
