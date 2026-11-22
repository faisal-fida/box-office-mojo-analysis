# box-office-mojo-analysis

A Jupyter notebook that scores movies by worldwide box office and release year and plots the results.

## Features

- Loads a Box Office Mojo export (`boxofficemojo.xlsx`) with pandas.
- Keeps the `name`, `worldwide` and `year` columns and min-max normalises them.
- Builds a combined score: inverted normalised worldwide gross plus normalised year.
- Interactive Plotly charts: scatter of worldwide gross against year coloured by score, top 10 films by worldwide gross, bottom 10 films by combined score.

## Tech stack

Python 3, pandas, Plotly, openpyxl, Jupyter.

## Project structure

```
boxofficemojo.ipynb   analysis notebook
boxofficemojo.xlsx    input data
requirements.txt
```

## Setup and run

```bash
python3 -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook boxofficemojo.ipynb
```

Run the cells in order. No environment variables or network access are needed.

## Usage

Replace `boxofficemojo.xlsx` with another export that has `Name`, `Worldwide` and `Year` columns (header case is ignored) and rerun the notebook.

## Limitations

- The combined score is an ad hoc formula. Because worldwide gross is inverted, low-grossing recent films score highest, so read the "bottom 10" chart with that in mind.
- No tests. Results are only shown as charts inside the notebook.
