# data_analytics_himalayan_mountaineering

# Einreichung Projektvorschlag
für
**Data Analytics
(17.11.25 – 12.12.25)**


## Projektersteller/Gruppe: 

- **Group** E: East/Lynam-Smth
- **Name:** Lynam-Smith, Miles ; East, James
- **Datum:** Presentation 11.12.25


## Projektidee, Beschreibung:The Himalayan database is rich in historical value, detailing the peaks, expeditions, climbing statuses, and geographic information of numerous Himalayan summits. We will explore this data dating back to the start of the last century. Our approach will be clean and tidy the data - using Numpy, Pandas in Jupyter notebook, before the data analysis takes place. We will record both the steps taken and the results plus any lesson learnt. The data analysis will focus on the inspiration taken from Tidy Tuesday in Github which is detailed in the following section; using MatPlotLib, Seaborn, Plotly (including Dash), and SpaCy.

Our purpose is to continuation of the work of Elizabeth Hawley, a longtime journalist based in Kathmandu, who dedicated most of her life to archiving expeditions in the Nepal Himalaya, whilst demonstrating our newly acquired data science skills. 

**Data Source** https://github.com/rfordatascience/tidytuesday/tree/main/data/2025/2025-01-21

and 

https://www.himalayandatabase.com/downloads/Himalayan%20Database.zip

## Projektschritte, Aufgaben zum Projekt (falls schon vorhanden):

### 1. Data Import & Understanding:Load all relevant Himalayan Database tables into Pandas DataFrames and explore their structure (data dictionary, columns/fields, first rows, data types). 


### 2. Exploratory Data Analysis (EDA): 

- Use descriptive statistics and visualizations to explore the data, detect outliers, missing values
- understand important variables (e.g., peak heights, climbing status, routes used).

### 3. Data Cleaning & Transformation: 
- Remove or impute missing values, standardize naming conventions/categories (e.g., names of peaks and countries)
- convert data types for dates/times, numbers, etc, engineer new features, e.g., create an “expedition success” variable based on all route outcomes.

### 4. Documentation & Version Control:
- Record every step in Jupyter Notebook using comments and markdown.
- Document issues and solutions and version key milestones using GitHub.

### 4. External Data Consistency Check:
- Check data reliability by cross-referencing some expeditions/peaks with Github and  Himalayan Database website.

### 5. Reflection & Lessons Learned:

- At the end reflect on what worked well in the cleaning and analysis process,
- where trouble arose
- what insights you gained.

### 6. Presentation/Reporting:
- Prepare key visualizations, analysis results, and main messages for a presentation

-----

## Potential Business Questions

- What is the distribution of climbing status (PSTATUS) across different mountain ranges (HIMAL_FACTOR)?
- Which mountain range (HIMAL_FACTOR) has the highest average peak height (HEIGHTM)?
- What is the distribution of peak heights (HEIGHTM) for peaks that are open (OPEN) versus those that are not?
- Which climbing routes (ROUTE1, ROUTE2, ROUTE3, ROUTE4) have the highest success rates (SUCCESS1, SUCCESS2, SUCCESS3, SUCCESS4) across all expeditions?
- How does the use of supplemental oxygen (O2USED, O2NONE) affect summit success rates?- -
- How often does bad weather (TERMREASON = 4) play a role in termination compared to technical difficulty (TERMREASON = 10)?
- Are expeditions with no hired personnel (NOHIRED) associated with higher or lower death rates?

