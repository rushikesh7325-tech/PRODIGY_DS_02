# PRODIGY_DS_02: Titanic Dataset - Exploratory Data Analysis

## 🚢 Project Overview
Comprehensive exploratory data analysis of the historic Titanic dataset to uncover patterns and factors affecting passenger survival during the tragic 1912 disaster.

## 📊 Dataset Information
- **Source**: Prodigy InfoTech / Kaggle Titanic Dataset
- **Records**: 891 passengers
- **Original Features**: `PassengerId`, `Survived`, `Pclass`, `Name`, `Sex`, `Age`, `SibSp`, `Parch`, `Ticket`, `Fare`, `Cabin`, `Embarked`
- **Engineered Features**: `Has_Cabin`, `Title`, `Family_Size`, `Age_Group`, `Fare_Category`, `Is_Alone`

## 🛠️ Tools & Technologies

 Python 3.9+, Pandas, NumPy
 Matplotlib, Seaborn, Jupyter Notebook


## 📋 Methodology

### 1. Data Loading & Initial Exploration
- Loaded dataset and examined structure (891 passengers, 12 features)
- Analyzed data types, distributions, and statistical summaries
- Identified missing value patterns

### 2. Data Cleaning
- **Age**: Filled 177 missing values (19.9%) with median (28.0 years)
- **Embarked**: Filled 2 missing values (0.2%) with mode ('S' - Southampton)
- **Cabin**: Created binary `Has_Cabin` indicator (77.1% missing), dropped original column
- **Result**: Zero remaining missing values

### 3. Feature Engineering
Created 6 new predictive features:

| Feature | Description | Purpose |
|---------|-------------|---------|
| `Title` | Extracted from Name (Mr, Mrs, Miss, Master, Rare) | Social status indicator |
| `Family_Size` | SibSp + Parch + 1 | Family grouping effect |
| `Age_Group` | Child(0-12), Teen(13-18), Adult(19-35), Middle Age(36-60), Senior(60+) | Age categorization |
| `Fare_Category` | Low, Medium, High, Very High (quartiles) | Wealth proxy |
| `Is_Alone` | 1 if Family_Size == 1 | Solo traveler indicator |
| `Has_Cabin` | 1 if cabin data exists | Deck location proxy |

### 4. Exploratory Analysis Dimensions
- Univariate analysis (survival distribution)
- Bivariate analysis (gender, class, age effects)
- Multivariate interactions (gender+class, age+family)
- Correlation analysis across all features

### 5. Visualization Suite (12+ Charts)

 Bar charts - Histograms - Box plots - Pie charts
 Heatmaps - Multi-panel grids - Statistical overlays


## 🔍 Key Findings

### 📈 Overall Statistics
  
 Total Passengers: 891
 Survived: 342 (38.38%)
 Died: 549 (61.62%)

### 🎯 Critical Survival Factors (Ranked by Impact)

| Rank | Factor | Survival Rate | Impact |
|------|--------|---------------|---------|
| 1 | **Female** | **74.20%** | 3.9x vs males |
| 2 | **1st Class** | **62.96%** | 2.6x vs 3rd class |
| 3 | **Has Cabin** | **66.67%** | 2.2x vs no cabin |
| 4 | **Child (<18)** | **54.02%** | Priority evacuation |
| 5 | **Family Size 2-4** | **53-58%** | Coordination advantage |

### Detailed Breakdown

#### Gender (Correlation: +0.543)
    
    Female: 74.20% (233/314)
    Male: 18.89% (109/577)



#### Passenger Class (Correlation: -0.338)
    
   1st Class: 62.96% (136/216)
   2nd Class: 47.28% (87/184)
   3rd Class: 24.24% (119/491)



#### Age Groups
 
  Child (0-12): 58.67%
  Teen (13-18): 38.46%
  Adult (19-35): 36.25%
  Middle Age: 42.11%
  Senior (60+): 23.81%

#### Family Size Sweet Spot
   Size 1 (Alone): 30.35%
   Size 2: 58.71%
   Size 3: 57.84%
   Size 4: 53.33%
   Size 7+: 11.11%


## 📈 Visualizations Catalog

| File | Analysis Type | Key Insight |
|------|---------------|-------------|
| `survival_distribution.png` | Overall breakdown | 38% survival baseline |
| `survival_by_gender.png` | Gender disparity | 74%F vs 19%M |
| `survival_by_class.png` | Class gradient | 63%→47%→24% |
| `age_analysis.png` | Age histograms | Bimodal survivor pattern |
| `fare_analysis.png` | Fare by class | 1st class fare premium |
| `family_size_survival.png` | Family dynamics | 2-4 member peak |
| `correlation_heatmap.png` | Feature matrix | Top correlations |
| `survival_by_port.png` | Port effects | C=## 📈 7 Visualizations Showcase (All Generated ✅)

### 🎯 TOP INSIGHTS - Priority Display

| **Gender + Class Interaction** | **Correlation Heatmap** | **Survival by Gender** |
|--------------------------------|-------------------------|------------------------|
| ![F1st=97% vs M3rd=13%](visualizations/gender_class_analysis.png "97% Female 1st vs 13% Male 3rd") | ![Has_Cabin +0.317](visualizations/correlation_heatmap.png "Top correlations") | ![74%F vs 19%M](visualizations/survival_by_gender.png "3.9x female advantage") |

| **Family Size Impact** | **Cabin Location Effect** | **Class Survival Gradient** |
|------------------------|---------------------------|-----------------------------|
| ![2-4 optimal](visualizations/family_size_survival.png "Optimal family coordination") | ![67% vs 30%](visualizations/cabin_impact.png "2.2x cabin advantage") | ![63%→47%→24%](visualizations/survival_by_class.png "Class disparity") |

### 📊 Overall Survival Baseline
<div style="text-align: center;">
    ![38% Survival](visualizations/survival_distribution.png "342/891 survived")
</div>


```markdown
## 📈 7 Key Visualizations Generated

| **Gender + Class** | **Correlation Matrix** | **Gender Disparity** |
|--------------------|----------------------|---------------------|
|  |  |  |

| **Family Dynamics** | **Cabin Impact** | **Class Gradient** |
|-------------------|-----------------|-------------------|
|  |  |  |

<div style="text-align: center;">

</div>
55%, Q=39%, S=34% |
| `cabin_impact.png` | Location proxy | Cabin=67% vs 30% |
| `gender_class_analysis.png` | Interaction effects | F1st=97%, M3rd=13% |
| `advanced_analysis.png` | 4-panel summary | Multi-factor patterns |

## 💡 Actionable Insights for Maritime Safety

1. **Evacuation Priority**: "Women & children first" saved ~55% vs 19% male baseline
2. **Class Access**: 1st class proximity to lifeboats = 2.6x survival advantage
3. **Deck Location**: Cabin assignment (upper decks) = lifeboat proximity
4. **Group Coordination**: Small families (2-4) navigated chaos 1.7x better
5. **Resource Equity**: Eliminate socioeconomic barriers in emergencies


## 🚀 How to Replicate

### Prerequisites
```bash
pip install pandas==2.0.3 numpy==1.24.3 matplotlib==3.7.2 seaborn==0.12.2 jupyter==1.0.0


# 1. Clone repository
git clone https://github.com/YOUR_USERNAME/PRODIGY_DS_02.git
cd PRODIGY_DS_02

# 2. Launch Jupyter
jupyter notebook

# 3. Open notebook
task02_titanic_eda.ipynb

# 4. Run all cells (Ctrl+F9) - ~5 minutes execution

