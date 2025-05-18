Lamrot Kassahun 
GitHub Repo URL: https://github.com/lamli65/solar-challenge-week-1.git   
Interim report Submission Date: 18 May 2025   
  

 

1.  Task 1: Git & Environment Setup 

a. Repository Setup 

Repo Name: solar-challenge-week1 

- Created repository: `solar-challenge-week1` 
- Cloned locally and created virtual environment using `venv` 
- Structured project as follows: 
 
  

solar-challenge-week1/ 

 ├── data/ # Raw and cleaned data (in .gitignore) 

 ├── notebooks/ # EDA and analysis notebooks 

 ├── scripts/ # Reusable Python scripts 

 ├── src/ # Main source code 

 ├── tests/ # Unit tests 

 ├── .github/workflows/ # GitHub CI workflows 

 ├── requirements.txt 

 └── README.md 

 
b. Git Branching 
- Mention branches you created (e.g., `setup-task`, `eda-benin`) 
- Mention pull requests and merges 
 
c. CI/CD Setup 
- setting up GitHub Actions CI: 
- `.github/workflows/ci.yml` 
- Configured to run `pip install -r requirements.txt` on push 
 
d. README.md 
- About environment setup instructions 
  ```markdown 
  To replicate the environment: 
  ```bash 
  git clone https://github.com/lamli65/solar-challenge-week1.git 
  cd solar-challenge-week1 
  python -m venv .venv 
  source venv/bin/activate 
  pip install -r requirements.txt 
  

 

2.Task 2: Data Profiling, Cleaning & EDA (Plan/Progress) 

This section details my strategy and progress toward analyzing the datasets for Benin, Togo, and Sierra Leone. 

Use subsections per country, and for each i will be using the following methods: 

a. Data Loading 

Loaded raw data from provided source 

Used pandas to inspect structure 

Columns include: GHI, DNI, DHI, ModA, Tamb, RH, WS, etc. 

b. Summary Statistics & Missing Values 

Plan to use: 

df.describe() 

df.isna().sum() 

Flag any column with >5% missing 

Mention if you already did this and what you found 

c. Outlier Detection 

Z-score strategy: 

|Z| > 3 for GHI, DNI, ModA, WS, etc. 

Plan to visualize or drop/impute 

Cleaning approach: 

Drop rows with critical nulls 

Impute with median for selected columns 

d. Time Series Patterns 

Plan to visualize: 

GHI, DNI, Tamb over time using line plots 

Look for diurnal/seasonal patterns 

e. Cleaning Impact 

Will analyze how cleaning events affected ModA/ModB values 

Group by Cleaning flag and compare 

f. Correlation Analysis 

Will generate: 

Correlation heatmaps 

Scatter plots (e.g., WS vs GHI, RH vs Tamb) 

g. Wind & Temperature Analysis 

Plan for: 

Wind rose charts (WS, WD) 

Bubble plots (GHI vs Tamb, bubble size = RH) 

h. Progress Summary 
- Completed initial profiling and outlier detection for Benin 
- Exported cleaned dataset to `data/benin_clean.csv` (ignored in Git) 
- EDA notebook saved as `notebooks/benin_eda.ipynb` 
  

 

3. Dataset Integration 

 All raw and cleaned datasets are stored locally under `/data/` directory, excluded via `.gitignore` to follow Git hygiene best practices. 
  

 

4. Next Steps 

- Complete EDA for Togo and Sierra Leone 
- Begin cross-country comparisons (Task 3) 
- Prepare visual summaries (boxplots, summary tables) 
- Begin Streamlit dashboard setup 
  