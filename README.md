# Movies Data Analysis Project

## 📊 Project Overview
This project analyzes a comprehensive movies dataset containing information about films including ratings, genres, financial data, cast, and production details.

## 📁 Project Structure
```
CSV Files/
├── moviescsv.csv                 # Original movies dataset
├── movies_cleaned.csv            # Cleaned dataset with NULLs filled
├── moviescsvfile.numbers         # Original Apple Numbers file
├── analyze_movies.py             # Data analysis script
├── fill_movie_nulls_python.py    # NULL handling script
├── import_movies.py              # Data import script
├── fill_movie_nulls.sql          # SQL NULL handling (alternative)
└── README.md                     # This file
```

## 🎯 Dataset Information
- **Total Movies**: 7,668 films
- **Columns**: 15 features
- **Time Period**: Various years
- **Data Quality**: Cleaned and preprocessed

### Dataset Columns
| Column | Type | Description |
|--------|------|-------------|
| name | String | Movie title |
| rating | String | MPAA rating (R, PG, etc.) |
| genre | String | Movie genre |
| year | Integer | Release year |
| released | String | Release date and country |
| score | Float | IMDb rating (0-10) |
| votes | Float | Number of votes on IMDb |
| director | String | Film director |
| writer | String | Screenwriter |
| star | String | Lead actor/actress |
| country | String | Production country |
| budget | Float | Production budget |
| gross | Float | Box office revenue |
| company | String | Production company |
| runtime | Float | Movie length in minutes |

## 🚀 Getting Started

### Prerequisites
- Python 3.7+
- pandas
- numpy
- matplotlib
- seaborn

### Installation
```bash
pip install pandas numpy matplotlib seaborn
```

### Data Import
```python
import pandas as pd

# Import cleaned dataset
df = pd.read_csv('/Users/michaelidaewor/Downloads/CSV Files/movies_cleaned.csv', header=0)

# Basic info
print(f"Dataset shape: {df.shape}")
print(df.head())
```

## 📈 Data Cleaning Process

### NULL Value Handling
The dataset was cleaned to handle missing values appropriately:

**Text/String Columns** → Descriptive defaults:
- Missing titles → 'Unknown Title'
- Missing ratings → 'Not Rated'
- Missing genres → 'Unknown'
- Missing cast/crew → 'Unknown Director/Writer/Star'
- Missing countries/companies → 'Unknown Country/Company'

**Numeric Columns** → Zero values:
- Missing scores, votes, budget, gross, runtime → 0
- Missing years → 0

### Data Quality Summary
- **Original NULLs**: 2,317 total missing values
- **After Cleaning**: 0 NULLs remaining
- **Data Integrity**: 100% complete dataset

## 🔧 Available Scripts

### 1. Data Analysis (`analyze_movies.py`)
- Loads and analyzes the movies dataset
- Provides basic statistics and data overview
- Saves cleaned version to CSV

### 2. NULL Handling (`fill_movie_nulls_python.py`)
- Identifies and fills all missing values
- Handles different data types appropriately
- Creates cleaned dataset ready for analysis

### 3. Data Import (`import_movies.py`)
- Simple script to load the dataset
- Includes basic data exploration
- Ready-to-use import commands

## 📊 Potential Analysis Areas

### Financial Analysis
- Budget vs. Revenue correlation
- Most profitable genres
- Production company performance
- Return on investment trends

### Content Analysis
- Genre popularity over time
- Rating distribution
- Director/actor success patterns
- Runtime trends

### Temporal Analysis
- Year-over-year trends
- Seasonal release patterns
- Evolution of movie ratings
- Historical budget changes

## 🛠️ Usage Examples

### Basic Statistics
```python
# Load data
df = pd.read_csv('/Users/michaelidaewor/Downloads/CSV Files/movies_cleaned.csv')

# Basic stats
print(df.describe())
print(df['genre'].value_counts())
print(df['rating'].value_counts())
```

### Financial Analysis
```python
# Budget vs Revenue
import matplotlib.pyplot as plt
plt.scatter(df['budget'], df['gross'])
plt.xlabel('Budget')
plt.ylabel('Gross Revenue')
plt.title('Budget vs Revenue')
plt.show()
```

### Genre Analysis
```python
# Top genres by average score
genre_scores = df.groupby('genre')['score'].mean().sort_values(ascending=False)
print(genre_scores.head(10))
```

## 📝 Notes
- Dataset includes films from various years and countries
- Financial data may be in different currencies (not standardized)
- Some movies may have incomplete information
- Ratings and scores are from IMDb

## 🤝 Contributing
Feel free to extend this analysis with additional visualizations, statistical tests, or machine learning models.

## 📄 License
This project is for educational and analytical purposes.

---
*Last updated: August 2024*
