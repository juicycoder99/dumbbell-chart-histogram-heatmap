# Dumbbell Chart, Histograms, and Heatmap

Data visualisation project comparing US traffic-fatality trends with a dumbbell chart and analysing COVID-19 case distributions across Chinese provinces with histograms and Bhattacharyya-coefficient heatmaps.

The full implementation and analysis is in [`dumbbell_histogram_heatmap.ipynb`](dumbbell_histogram_heatmap.ipynb).

## Part I — Dumbbell Chart

Reproduces the dumbbell chart from the `Dumbbell 1` tab of `Dumbbell.xlsx`, showing the traffic
fatality rate per 100 million vehicle miles travelled for each US state in **2007 vs 2017**
(source: NHTSA). States are ordered by their 2017 rate. Built two ways:

- **Matplotlib** — static reproduction matching the original colours (2007 in blue `#5B9BD5`,
  2017 in orange `#ED7D31`).
- **Plotly** — an interactive version with hover values.

## Part II — Histograms and Heatmap

Using `covid_china_daily_70days_2.csv` (70 days of daily COVID cases per Chinese province):

1. Reproduce the Chongqing daily-case histograms for bin sizes **1, 5, 15, 50, 100**.
2. Compute the **Bhattacharyya coefficient** between every pair of provinces to build an
   *N × N* similarity matrix.
3. Visualise each similarity matrix as a **heatmap**.
4. Repeat for all five bin sizes and discuss how bin size affects the result.

The Bhattacharyya coefficient between two normalised histograms *P* and *Q* is:

```
BC(P, Q) = Σ sqrt( P(i) · Q(i) )
```

## Running it

```bash
pip install numpy pandas matplotlib plotly seaborn openpyxl
jupyter notebook dumbbell_histogram_heatmap.ipynb
```

## Files

| File | Description |
|------|-------------|
| `dumbbell_histogram_heatmap.ipynb` | Full implementation and analysis (Part I and Part II) |
| `PROJECT_BRIEF.pdf` | Project brief (goals, objectives, outcomes) |
| `Dumbbell.xlsx` | Part I dataset |
| `covid_china_daily_70days_2.csv` | Part II dataset |
