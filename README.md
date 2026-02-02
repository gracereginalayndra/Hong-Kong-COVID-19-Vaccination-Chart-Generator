**README.md:**

```markdown
# Hong Kong COVID-19 Vaccination Chart Generator

This project replicates professional-style horizontal stacked bar charts showing Hong Kong's COVID-19 vaccination rates by age group, similar to those published by the HKSAR government. It processes raw vaccination and population data to calculate cumulative dose percentages and visualizes them using Pandas and Matplotlib.

## Features
- Downloads and processes vaccination data from official CSV sources
- Fetches population data via API from the Census and Statistics Department
- Merges, groups, and scales data to compute per-population vaccination rates
- Generates stacked horizontal bar charts with cumulative percentages
- Custom data labeling with conditional formatting (bold totals, segment labels)
- Professional styling: grid lines, legends, tight layout, and publication-ready formatting

## Requirements
- Python 3.8+
- pandas
- matplotlib
- requests (for API calls, if not already included in starter code)

## Installation
```bash
git clone https://github.com/yourusername/hk-covid-vaccination-charts.git
cd hk-covid-vaccination-charts
pip install pandas matplotlib requests
```

## Project Structure
```
.
├── vaccinestat.py                          # Main script with all required functions
├── data/                          # Optional: sample raw data files
├── outputs/                       # Generated charts
├── README.md
└── requirements.txt
```

## Functions Implemented
1. `get_population(start, end)` – Fetches population data via API
2. `get_vaccination(start, end)` – Loads and filters vaccination data
3. `preprocess_population(df_pop)` – Cleans population data
4. `preprocess_vaccination(df_vac, df_pop)` – Merges and calculates vaccination rates
5. `plot_vaccination(df, as_at, n)` – Generates the stacked bar chart

## Usage
Run the provided starter code or use:
```python
from q5 import get_vaccination, get_population, preprocess_vaccination, plot_vaccination

df_vac = get_vaccination(end="2024-04-07")
df_pop = get_population("202307", "202312")
df_rates = preprocess_vaccination(df_vac, df_pop)
fig = plot_vaccination(df_rates, as_at="2024-04-07", n=7)
fig.savefig("vaccination_chart.png")
```

## Sample Output
The script generates charts similar to the official HKSAR vaccination reports, with:
- Horizontal stacked bars for each age group
- Bold labels for total vaccination rate per age group
- Segment labels for each dose where space allows
- Clean grid, legend, and title formatting

## Data Sources
- Vaccination data: HKSAR daily vaccination CSV: https://data.gov.hk/en-data/dataset/hk-hhb-hhbcovid19-vaccination-rates-over-time-by-age
- Population data: Census and Statistics Department API (Table 110-01002): https://www.censtatd.gov.hk/en/web_table.html?id=110-01002

## Notes
- Uses a global constant `N` for number of vaccine doses (default 7)
- Implements cumulative percentage display for clearer interpretation

## Acknowledgments
- Data provided by HKSAR Government
- Inspired by official COVID-19 vaccination dashboards
```
