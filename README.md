#Education Project

> A brief description of what the project does and its purpose.
This project aims to address the educational inequality in US high schools based on ACT and SAT scores.
---

## Project Overview

This project is designed to answer how ACT score get influenced by socioeconmoic factors by usin Edgap and National Center for Education Statistics data(NCES). 

- **Objective:** To determine how average school ACT scores are influenced by community socioeconomic facotrs and to invesitigate if schools contribute any factors toward it.
- **Domain:** Education, Public Policy
- **Key Techniques:** Data cleaning, Data merging, Exploratory Data Analysis, Multiple linear regression, Feature engineering. 

---

## Project Structure

```
├── data/                 # Raw and processed data
├── code/                 # Jupyter notebooks and Python scripts
├── reports/              # Generated reports and visualizations
├── requirements.txt      # Dependencies
└── README.md             # Project documentation
```

---

## Data

- **Source:** : https://github.com/devlinhoang-cyber/Education/tree/e77fae2f9622268b64f8acecc65c9f7e110e50b4/Data
- **Description:**
  1. Edgap_data.xlsx: Provided school level average ACT score and community socioeconmic indicators, such as median income, unemployment, parental education, free/reduced lunch meal.
  2. ccd_sch_029_1617_w_1o_11212017.csv: The 2016-2017 Common Core of Data (CCD) from NCES contains metadata from all public schools. 
- **License:** (if applicable)
    Data is from public sources (EdGap.org, NCES) and is in the public domain.

---

## Analysis

1. Data loading with Edgap and CCD files into the Dataframe by using Pandas.
2. Data cleaning and filtering with snake_case to make column names standardized. The CCD is filtered to includ only High School, perecentage was converted into numeric variables.
3.  Preprocessing with duplicating School_ID and dropped any data with 0 or NaN.
4.  Data merging to clean up Edgap and CCD_high_school;, then merge into a single dataset.
5.  Categorized school_type to creat binary dummy variable for regression model.
6.  Histogram and heat map are used as exploratory data analysis tools, to show relationship between socioeconomic and ACT scores.
7.  Moedling by using statmodels: Model 1 is predicting ACT scores with only socioeconomic facotrs. Model 2 predicts with both socioeconomic factors and school_type dummy variable.
9.  Export final cleaned data set as edgap_ccd_merged_cleaned_final.csv
---

## Results

The results of the analysis supported both of our theories.A strong predictor of average ACT scores is socioeconomic status.  Adj.R square = 0.692 indicates that 69.2% of the variance in ACT scores was explained by Model 1 (socioeconomic variables alone).The two best predictors are pct_adults_college (a high positive connection, R = 0.65) and pct_free_reduced_lunch (a significant negative association, R = -0.74).Model 2's inclusion of school type as a predictor greatly enhanced the model, raising the explained variance to 70.9% (Adj. R square = 0.709).The average ACT scores of Charter schools (-0.87 points) and Vocational/Technical schools (-1.35 points) were considerably lower than those of "Regular" schools in this sample, even after adjusting for all socioeconomic characteristics. 
---

## Authors

- Devlin Hoang - [@devlinhoang-cyber(https://github.com/devlinhoang-cyber/Education)

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Acknowledgements

- Tools/libraries used
- Tutorials or papers referenced
- Inspiration or collaborators
