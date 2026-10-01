# KPC 금융 데이터 분석 수업 자료

2026년 10월 6~8일 · 20시간 과정의 수강생 실습 자료입니다.

[수업 안내](https://www.slog.gg/p/14880) · [교시별 수업 자료](https://www.slog.gg/p/14891)

## 다운로드하고 시작하기

1. [수업 자료 ZIP 다운로드](https://github.com/jhs512/kpc-finance-course/releases/latest/download/kpc-finance.zip)를 누릅니다. GitHub 로그인은 필요하지 않습니다.
2. Windows 탐색기에서 ZIP의 **모두 압축 풀기**를 선택합니다. ZIP 안에서 직접 실행하지 않습니다.
3. 압축 안의 `kpc-finance` 폴더를 `C:\kpc-finance`에 둡니다. 이 폴더를 열었을 때 `pyproject.toml`, `uv.lock`, `.python-version`, `raw`, `practice`가 바로 있어야 합니다. 이미 같은 이름의 폴더가 있으면 덮어쓰지 말고 다른 영문 폴더 이름을 사용합니다.
4. PowerShell에서 실제 폴더로 이동한 뒤 아래 명령을 실행합니다. CMD를 사용할 때 폴더 이동 명령은 `cd /d C:\kpc-finance`입니다.

```powershell
cd C:\kpc-finance
uv sync --locked
uv run --locked jupyter notebook
```

uv가 없으면 [uv 공식 설치 안내](https://docs.astral.sh/uv/getting-started/installation/)를 먼저 따릅니다. 이 배포 자료에서는 `uv init`이나 `uv add`를 다시 실행하지 않습니다. Python과 패키지를 최초로 내려받으므로 인터넷이 필요합니다. `.venv`는 각 PC에서 새로 만들어집니다.

5. 브라우저가 열리면 `practice` → `periods` → `d1-p01.ipynb`를 엽니다. 새 Notebook을 직접 만들려면 최상위에서 **New → Python 3 (ipykernel)**을 선택하고 `01-python-basics.ipynb`로 저장합니다.
6. Python Kernel에서 `import sys; print(sys.executable)`를 실행해 선택한 폴더의 `.venv`인지 확인합니다. `from pathlib import Path; print(Path.cwd())`로 자료 위치도 확인합니다. 교시별 Notebook은 첫 셀이 수업 자료의 최상위 폴더를 찾습니다.
7. 셀은 위에서 아래로 실행합니다. 끝나면 저장하고 Kernel을 재시작해 전체 재실행합니다.

## 포함된 자료

- 교시별 Notebook 12개(실행 출력 초기화)
- 검증된 환경 설정 및 잠금 파일 3개
- Titanic, 익명 신용카드 부도 데이터, 삼성전자 과거 주가 CSV

기존 원자료의 경로와 값은 수업 설명에 맞춰 유지합니다. 교안은 데이터 분석 연습용이며 금융 예측의 정확도를 보장하지 않습니다. 라이브 웹 수집은 외부 응답에 따라 실패할 수 있어 제공 파일로 기본 실습을 진행합니다.
