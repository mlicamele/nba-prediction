# nba-prediction

Machine learning model to predict NBA games trained on scraped data.

## Features

- **Game Winner Prediction**: Predicts which team will win NBA games
- **Comprehensive Statistics**: Uses extensive team statistics including traditional and advanced metrics
- **Web Scraping Pipeline**: Automated data collection using Playwright and BeautifulSoup
- **Ridge Classifier Model**: Robust machine learning approach for binary classification
- **Historical Data**: Training on NBA game data with team performance metrics

## Technology Stack

- **Python**: Core programming language
- **scikit-learn**: Ridge Classifier implementation and model evaluation
- **pandas**: Data manipulation and analysis
- **numpy**: Numerical computing
- **BeautifulSoup (bs4)**: HTML parsing for web scraping
- **Playwright**: Web browser automation for data collection

## Model Performance

- **Accuracy**: 63% on test data
- **Algorithm**: Ridge Classifier
- **Prediction Type**: Binary classification (Win/Loss)

## Dataset Features

The model uses a comprehensive set of team statistics including:

**Traditional Stats**: Minutes played (mp), field goals (fg, fga, fg%), 3-pointers (3p, 3pa, 3p%), free throws (ft, fta, ft%), rebounds (orb, drb, trb), assists (ast), steals (stl), blocks (blk), turnovers (tov), personal fouls (pf), points (pts), plus/minus (+/-)

**Advanced Stats**: True shooting percentage (ts%), effective field goal percentage (efg%), 3-point attempt rate (3par), free throw rate (ftr), rebound percentages (orb%, drb%, trb%), assist percentage (ast%), steal percentage (stl%), block percentage (blk%), turnover percentage (tov%), usage percentage (usg%), offensive rating (ortg), defensive rating (drtg)

**Team Context**: Home/away status, season information, game dates

**Opponent Stats**: Complete mirror of all above statistics for opposing teams

## Installation

### Prerequisites
- Python 3.7 or higher
- scikit-learn
- pandas
- numpy
- bs4
- playwright

### Setup
1. Clone the repository:
```bash
git clone https://github.com/mlicamele/nba-prediction.git
cd nba-prediction
```

2. Install required packages:
```bash
pip install scikit-learn pandas numpy beautifulsoup4 playwright
```

3. Install Playwright browsers:
```bash
playwright install
```

## Project Structure

```
nba-prediction/
├── data/
│   ├── scores/           # Game score data
│   └── standings/        # Team standings data
├── get_data.ipynb        # Data collection notebook
├── parse_data.ipynb      # Data processing notebook
├── predict.ipynb         # Model training and prediction notebook
├── nba_games.csv         # Processed game data
├── .gitattributes        # Git LFS configuration
├── .gitignore           # Git ignore file
└── README.md
```

## Usage

The project is organized as Jupyter notebooks for easy exploration and execution:

### 1. Data Collection
Open and run `get_data.ipynb` to scrape the latest NBA data:
```bash
jupyter notebook get_data.ipynb
```

### 2. Data Processing
Process and clean the scraped data using `parse_data.ipynb`:
```bash
jupyter notebook parse_data.ipynb
```

### 3. Model Training and Prediction
Train the Ridge Classifier and make predictions with `predict.ipynb`:
```bash
jupyter notebook predict.ipynb
```

## Data Collection

The project uses web scraping to collect NBA statistics:
- **Playwright**: Handles dynamic web content and browser automation
- **BeautifulSoup**: Parses HTML content to extract statistical data
- **Data Sources**: NBA team statistics, game scores, and standings

## Model Details

### Ridge Classifier
- **Type**: Linear classifier with L2 regularization
- **Advantages**: Handles multicollinearity well, robust to overfitting
- **Input**: Team statistics for both teams in a matchup
- **Output**: Binary prediction (0 = away team wins, 1 = home team wins)

### Feature Engineering
The model incorporates:
- Team performance statistics
- Maximum player statistics per game
- Opponent statistics (complete statistical profile of opposing team)
- Home/away indicators
- Temporal features (season, date)

## File Descriptions

- **get_data.ipynb**: Web scraping implementation using Playwright and BeautifulSoup
- **parse_data.ipynb**: Data cleaning, processing, and feature engineering
- **predict.ipynb**: Model training, evaluation, and prediction generation
- **nba_games.csv**: Final processed dataset with all features
- **data/scores/**: Raw game score data from scraping
- **data/standings/**: Team standings and ranking data
