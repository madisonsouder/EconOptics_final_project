# EconOptics
## Source
The data was published by two different sources. The Regional Cost of Living Analysis data was published on the data-sharing website Kaggle. It was collected from 2000 to 2023 and downloaded as a CSV file on March 20, 2025. <br>
Sadati, H. M. (2024, November 30). Regional cost of living analysis. Kaggle. https://www.kaggle.com/datasets/heidarmirhajisadati/regional-cost-of-living-analysis <br>

The Wellbeing Research Centre at the University of Oxford and Gallup, the UN Sustainable Development Solutions Network, published the World Happiness Report data. The dataset includes data from 2011 to 2024. It was accessed and downloaded as an Excel file on March 20, 2025. <br>
Gallup World Poll. (2024). World Happiness Report [Data set]. https://worldhappiness.report/data-sharing/
### Collection
**Regional Cost of Living Analysis** <br>
There was no metadata published with this dataset. It is not possible to determine how this data was collected. <br>

**World Happiness Rank** <br>
The data is collected through a survey, either conducted over the phone or face-to-face. Approximately 1,000 people are surveyed from each participating country and territory per year. Countries with larger populations have high survey numbers per year; China averages 4,000 people surveyed per year. 
### Extraction
**Regional Cost of Living Analysis** <br>
The data was downloaded from Kaggle as a CSV file. This was a one-time download with no updates. <br>

**World Happiness Rank** <br>
The data was downloaded from the World Happiness Report website as an Excel file. This was a one-time extraction with no updates. <br>
## Data Cleaning
### Program
Both datasets were cleaned and examined using Python through Jupyter Notebook.
### Cleaning
1. The column names of both datasets were changed to lowercase, and spaces were replaced with underscores
2. NaN values and outliers were found and examined, but left as is. They would be re-examined after the two datasets were combined into one dataframe.
3. The World Happiness Report was saved as a new dataframe with only the desired columns kept.
   - year
   - happiness_rank
   - country
   - happiness_score
   - upperwhisker
   - lowerwhisker
   - explained_by_log_gdp_per_capita
4. The two datasets were left-joined on the year and country. All rows from the Regional Cost of Living Analysis were kept, and only rows from the World Happiness Report with a match were kept.
5. The columns were re-ordered as:
   - country
   - region
   - year
   - happiness_rank
   - average_monthly_income
   - cost_of_living
   - tax_rate
   - housing_cost_percentage
   - healthcare_cost_percentage
   - education_cost_percentage
   - transportation_cost_percentage
   - savings_percentage
   - happiness_score
   - upperwhisker
   - lowerwhisker
   - explained_by_log_gdp_per_capita
6. Three rows were removed because each row had 404 NaN values out of a total of 500 entries. The rows removed were:
   - upperwhisker
   - lowerwhisker
   - explained_by_log_gdp_per_capita
7. Rows from 2011 to 2024 where the happiness score or happiness rank was NaN were removed. All rows containing data from the Regional Cost of Living Analysis Data were kept. <br>
All cleaning and the reasoning were included as comments in Python.
## Data Nuances
### Numerical Data
There are ten numerical data columns. The following is their unit:
   - happiness_rank - Number
   - average_monthly_income - USD
   - cost_of_living - USD per month
   - tax_rate - Average monthly percent
   - housing_cost_percentage - Percent
   - healthcare_cost_percentage - Percent
   - education_cost_percentage - Percent
   - transportation_cost_percentage - Percent
   - savings_percentage - Percent
   - happiness_score - Number
### Formulas
No additional columns were created, and thus no formulas were used.
### Column Names
   - country - Name of the country
   - region - Continent the country is located on
   - year - Year the data was collected and reflects
   - happiness_rank - Where the highest score ranks compared to the other countries
   - average_monthly_income - Average monthly income converted to USD
   - cost_of_living - Average monthly income converted to USD
   - tax_rate - Percentage rate at which the income is taxed
   - housing_cost_percentage - Percent of monthly income spent on housing
   - healthcare_cost_percentage - Percent of monthly income spent on healthcare
   - education_cost_percentage - Percent of monthly income spent on education
   - transportation_cost_percentage - Percent of monthly income spent on transportation
   - savings_percentage - Percent of monthly income saved 
   - happiness_score - average score from 0 to 10
