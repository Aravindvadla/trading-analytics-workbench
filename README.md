\# Trading Analytics Workbench



A small Python project with:



\- \*\*FastAPI\*\* service exposing `/forecast` and `/backtest`

\- \*\*Dash\*\* dashboard to visualize price vs. moving-average forecast and signal counts



\## Repo layout

.

├─ src/

│ └─ workbench/

│ ├─ init.py

│ ├─ backtest.py # moving\_average\_backtest()

│ ├─ data\_gen.py # mock price data

│ ├─ forecast.py # forecast helpers

│ └─ repo.py # simple in-memory repo

├─ app.py # FastAPI app

├─ dashboard.py # Dash dashboard

├─ requirements.txt

├─ pyproject.toml

└─ data/prices\_OIL.csv # sample data





\## Quick start



\### 1) Create \& activate venv



python -m venv .venv

.\\.venv\\Scripts\\Activate.ps1

pip install -r requirements.txt



2\) Run the API



$env:PYTHONPATH = (Resolve-Path .\\src).Path

python -m uvicorn app:app --reload

Open: http://127.0.0.1:8000/forecast and http://127.0.0.1:8000/backtest



3\) Run the dashboard (new terminal)



$env:PYTHONPATH = (Resolve-Path .\\src).Path

python .\\dashboard.py

Open: http://127.0.0.1:8050





Notes



If you see ModuleNotFoundError: workbench..., make sure PYTHONPATH is set as shown above.







