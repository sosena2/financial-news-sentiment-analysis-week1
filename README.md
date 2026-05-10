# Financial News Sentiment Analysis

Predicting stock price movements using news sentiment analysis and technical indicators.

## Project Structure
- `notebooks/` - Jupyter notebooks for analysis
- `data/raw/` - Raw data files
- `src/` - Source code modules
- `tests/` - Unit tests
- `scripts/` - Utility scripts

## Setup
```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows
pip install -r requirements.txt
## Project Conventions

- Data files: keep raw, immutable CSVs in `data/raw/`. Processed artifacts go in `data/processed/` (create when needed).
- Notebooks: exploratory analyses live in `notebooks/`. Make summary cells self-contained and include a final "Executive Summary" cell.
- Code: reusable functions live in `src/`. Prefer small, testable functions and avoid side effects.
- Branching: use feature branches `task-1`, `task-2`, `task-3` and open PRs against `main`.
- Commits: use Conventional Commits style (e.g., `fix(task2): ...`, `feat(task3): ...`).

## Data

- Ensure `data/raw/` contains original CSVs (do not edit in-place). Example files: `AAPL.csv`, `AMZN.csv`, `GOOG.csv`, `META.csv`, `NVDA.csv`, `raw_analyst_ratings.csv`.
- If adding derived datasets, create `data/processed/` and add a README note explaining the derivation steps.

## Testing & Validation

- Unit tests: place small unit tests in `tests/` using `pytest`. Focus on data transformations and core functions in `src/`.
- Notebook validation: add lightweight validation cells that recompute critical variables before plotting (self-contained summary cells).
- Reproducible environment: use `venv` and `requirements.txt`. For CI, run `pip install -r requirements.txt` and `pytest`.
- Example test commands:

```bash
venv\\Scripts\\activate     # Windows
pip install -r requirements.txt
pytest -q
```

## CI Recommendation

- Add a simple GitHub Actions workflow that:
	- Sets up Python, installs `requirements.txt`
	- Runs `pytest`
	- (Optional) Executes key notebook cells using `nbconvert` or `papermill` for smoke tests

