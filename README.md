# 🏏 IPL 2025 — Batting & Bowling Performance Analysis

An end-to-end Exploratory Data Analysis (EDA) of IPL 2025 player statistics, covering 156 batters and 108 bowlers across all 10 franchises. The project uncovers top performers, team-level trends, and the statistical profiles that separate elite players from the rest.

---

## 📁 Repository Structure

```
ipl2025-eda/
│
├── ipl2025.ipynb     # Main analysis notebook 
├── IPL2025Batters.csv         # Batting dataset — 156 players, 14 columns
├── IPL2025Bowlers.csv         # Bowling dataset — 108 players, 13 columns
└── README.md                  # Project overview (this file)
```

---

## 🗂️ Dataset Source

| Field | Details |
|-------|---------|
| **Platform** | [Kaggle](https://www.kaggle.com/datasets/vinayaks0n1/ipl-2025) |
| **Dataset Name** | IPL 2025 |
| **Author** | [vinayaks0n1](https://www.kaggle.com/vinayaks0n1) |
| **URL** | https://www.kaggle.com/datasets/vinayaks0n1/ipl-2025 |
| **Files Used** | `IPL2025Batters.csv`, `IPL2025Bowlers.csv` |
| **Tags** | data analytics · sports · data visualization · cricket · optimization |

> 💡 *"Make the best IPL fantasy teams!"* — original dataset description on Kaggle.

To download the dataset directly:
```bash
# Using Kaggle CLI (requires kaggle.json API token)
kaggle datasets download -d vinayaks0n1/ipl-2025
unzip ipl-2025.zip
```
Or download manually from the [Kaggle dataset page](https://www.kaggle.com/datasets/vinayaks0n1/ipl-2025).

---

## 📊 Datasets

### `IPL2025Batters.csv`
| Column | Description |
|--------|-------------|
| `Player Name` | Full player name |
| `Team` | IPL franchise |
| `Runs` | Total runs scored |
| `Matches` | Matches played |
| `Inn` | Innings batted |
| `No` | Not-outs |
| `HS` | Highest score |
| `AVG` | Batting average |
| `BF` | Balls faced |
| `SR` | Strike rate |
| `100s` | Centuries |
| `50s` | Half-centuries |
| `4s` | Total fours |
| `6s` | Total sixes |

### `IPL2025Bowlers.csv`
| Column | Description |
|--------|-------------|
| `Player Name` | Full player name |
| `Team` | IPL franchise |
| `WKT` | Total wickets |
| `MAT` | Matches played |
| `INN` | Innings bowled |
| `OVR` | Overs bowled |
| `RUNS` | Runs conceded |
| `BBI` | Best bowling in an innings |
| `AVG` | Bowling average |
| `ECO` | Economy rate |
| `SR` | Bowling strike rate |
| `4W` | Four-wicket hauls |
| `5W` | Five-wicket hauls |

---

## ⚙️ Feature Engineering

New columns created during analysis:

| Feature | Formula | Purpose |
|---------|---------|---------|
| `Runs_per_Match` | `Runs / Matches` | Normalises scoring across different squad sizes |
| `Boundary_Runs` | `(4s × 4) + (6s × 6)` | Measures pure boundary contribution |
| `Boundary_Percentage` | `Boundary_Runs / Runs × 100` | How much of a batter's scoring comes off the rope |
| `Wickets_per_Match` | `WKT / MAT` | Fairer wicket comparison than raw totals |
| `Bowling_Impact` | `WKT / ECO` | Balances wickets against cost — rewards efficient wicket-takers |

---

## 📈 Analysis Overview (13 Charts)

| # | Chart | Key Finding |
|---|-------|-------------|
| 1 | Top 10 Run Scorers | Sai Sudharsan (GT, 759) leads Orange Cap; SKY and Kohli close behind |
| 2 | Top 10 Wicket Takers | Prasidh Krishna (GT, 25) leads Purple Cap; Bumrah best economy at 6.67 |
| 3 | Team-wise Total Runs | PBKS (3000) top, KKR (1886) bottom — a sharp contrast to 2024 |
| 4 | Team-wise Total Wickets | MI (109) most potent bowling unit, RR (65) least |
| 5 | Strike Rate Distribution | Most batters 120–160; Pooran (196.25) and Abhishek Sharma (193.39) are outliers |
| 6 | Batting Avg vs Strike Rate | SKY and Kohli dominate the elite top-right quadrant |
| 7 | Top Boundary Hitters | Pooran highest boundary% (80.15%); SKY leads boundary runs (504) |
| 8 | Economy Rate Distribution | Most bowlers 7–10 eco; Bumrah (6.67) is a clear left-tail outlier |
| 9 | Economy vs Wickets | Bumrah is the only player combining low economy and high wickets |
| 10 | Team Avg Strike Rate | PBKS (~145) most aggressive, DC (~119) most conservative |
| 11 | Team Avg Economy | RCB (9.22) most disciplined bowling unit, LSG (10.39) most expensive |
| 12 | Batting Correlation Heatmap | SR and Boundary% strongly correlated; Runs and Boundary_Runs tightly linked |
| 13 | Bowling Correlation Heatmap | WKT and Bowling_Impact strongly linked; experience (MAT) correlates with wickets |

---

## 🏆 Key Findings

### Batting
- **Orange Cap:** Sai Sudharsan (GT) — 759 runs at AVG 54.21
- **Most Destructive:** Nicholas Pooran (LSG) — SR 196.25, 80% boundary rate
- **Most Complete:** Surya Kumar Yadav (MI) — 717 runs at SR 167.91
- **Best Team Batting:** PBKS — 3000 team runs; Iyer, Prabhsimran, and Priyansh all struck above 160

### Bowling
- **Purple Cap:** Prasidh Krishna (GT) — 25 wickets
- **Most Economical:** Jasprit Bumrah (MI) — 18 wickets at eco 6.67
- **Best Spinner:** Varun Chakravarthy (KKR) — 17 wickets at eco 7.66
- **Best Team Bowling:** MI — 109 team wickets; RCB — best avg economy (9.22)

---

## 🛠️ Setup & Usage

### Requirements
```bash
pip install pandas numpy matplotlib seaborn
```

### Run the Notebook
```bash
jupyter notebook ipl2025_enriched.ipynb
```

Make sure `IPL2025Batters.csv` and `IPL2025Bowlers.csv` are in the **same directory** as the notebook before running.

---

## 🚀 Potential Extensions

- 🤖 **Predictive Modelling** — predict Orange/Purple Cap winners using mid-season regression
- 🏆 **Match Winner Prediction** — combine batting SR, team economy, and wicket rate into a win-probability model
- 📊 **Interactive Dashboard** — Power BI or Tableau for franchise-level drill-down
- 🔢 **Player Clustering** — K-Means to group players (anchor vs. aggressor vs. finisher profiles)
- 📈 **Playoff Probability Forecasting** — points table trend analysis

---

## 👤 Author

**IPL 2025 Data Analysis Project**  
Built with Python · pandas · matplotlib · seaborn

---

*Data covers the IPL 2025 season across all 10 franchises and 74 matches.*
