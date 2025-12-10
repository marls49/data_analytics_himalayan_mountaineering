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

-------------------------------------------------
-------------------------------------------------

The EDA brief was then developed into a concrete workflow: first clean/tidy with NumPy/pandas, then analyze/visualize with Matplotlib/Seaborn/Plotly/Dash, and finally do some text analysis with spaCy.

## 1. Cleaning and tidying with NumPy/pandas

- Load all CSVs, check shapes/dtypes, and standardize column names (lowercase, no spaces, consistent prefixes like `exp_`, `peak_`).  
- Handle missing values: inspect `isna().sum()`, decide when to drop rows/columns vs. impute (e.g., median heights, mode for categorical status), and ensure numeric columns are numeric (`to_numeric`, `astype(float)`), using NumPy for replacements (`np.where`, `np.nan`).  
- Fix categories and codes: map numeric codes like `PSTATUS`, `HIMAL_FACTOR`, `TERMREASON` to readable labels via dictionaries; normalize country/route names, and create tidy tables (separate expeditions, peaks, routes) with one row per entity and meaningful keys.  

## 2. Feature engineering in pandas/NumPy

- Create analytic features: expedition success flag (any success columns true), derived metrics like success rate per peak or route, death rate, altitude bands, and boolean indicators for oxygen use and hired personnel.  
- Aggregate with `groupby` for the questions in your screenshot: distribution of PSTATUS by HIMAL_FACTOR, mean HEIGHTM by HIMAL_FACTOR, distributions of HEIGHTM for OPEN vs not, success rates by ROUTE1–4, oxygen vs non‑oxygen success, termination reasons (weather vs technical), and hired vs non‑hired death/success rates.  
- Store reusable aggregates in separate DataFrames (e.g., `status_by_range`, `route_success`, `reason_counts`) and cache intermediate results to CSV/Parquet for version control.  

## 3. EDA with Matplotlib and Seaborn

- Use Seaborn for quick statistics: countplots/histplots of PSTATUS, HEIGHTM distributions, box/violin plots of HEIGHTM by HIMAL, bar plots of success rate by route and oxygen use; use Matplotlib when you need more low‑level control or publication‑quality tweaks.  
- Build multi‑panel figures to compare ranges or time periods, annotate important peaks or outliers, and always link visuals directly to the project questions (e.g., “Which mountain range has the highest average peak height?”).  
- Save plots with clear filenames and resolutions, and document insights inline in notebook (e.g., observations about outliers, unusual termination reasons, or inconsistent codes).  

## 4. Interactive views with Plotly and Dash

- Replicate key Seaborn/Matplotlib plots in Plotly Express for interactivity (hover, zoom): bar charts of average success rate by route, scatter of HEIGHTM vs success with colour by HIMAL, histograms split by oxygen/hired flags.  
- Use Dash to wrap these into an app:  
  - Controls like dropdowns (select range/peak), radio buttons (metric: success rate vs death rate), and sliders (year range if available).  
  - Graphs that update based on selections, plus optional data tables showing filtered expeditions.  
- Deploy the Dash app locally and treat it as an interactive report for the findings.  

## 5. Text and documentation with spaCy

- Jamie wants to use Accidents as it contains free-text - are there others?

- When we have free‑text fields (route descriptions, incident narratives, notes), use spaCy to clean and analyze them: tokenize, lemmatize, remove stopwords, and extract named entities (places, dates, organizations).  
- Build simple text features like keyword flags (e.g., “avalanche”, “crevasse”, “storm”), route type descriptors, or difficulty hints, and join them back to the expedition DataFrame for correlation with outcomes.  
- Use this text analysis to enrich the EDA (e.g., compare success or death rates for expeditions mentioning “weather” terms vs those that don’t) and to provide qualitative examples in your reflection/lessons learned.  

Next step can be a concrete notebook outline with example pandas/Seaborn/Plotly/Dash/spaCy code snippets tailored to the actual Himalayan tables.


-----------------------------------------------
------------------------------------------------

Lessons learnt

### Documentations and Version control

The Team (Miles and James) decided that the best way to approach the project was as a professional team would.

To do this we had two main focused; structure and documentation. We started the day with a Stand up at 0830, showing what was done the day before and highlighting the plan for the day ahead. After this was completed code was shared and problem solving started on any bugs. 

Secondly we used both "belt and braces" (auf Nummer sicher gehen) and decided to put documentation within both the Notebooks and within the readme. 

Thirdly for version control we decided to set up a Github repo https://github.com/marls49/data_analytics_himalayan_mountaineering, using commits to track progress and resolve issues with merges or clashes with data sets to ensure that consistency was maintained. 

### Reflection & Lessons Learned

The biggest learning we experienced as a team was the importance of a teamwork (e.g that we were both using the same dataset) secondly working on different parts of the same project and how github, whilst incredibly helpful still needs to removed in terms of mark ups - merges need to be aligned and gone through within the team as part of the process. For example we have been through the merger clashes on Visual Studio Code together step by step to ensure alignment within our tiny team. 

The key point here is that this project has given us a taste of how it would be to work in a team. Teamwork is not solely about hardskills - in this case Numpy or Pandas, Seabourne or Spacy but also about ensuring a cohesive unit that can pull together, a very valueable skillset for the future. 


### Presentation/Reporting

The decision we made as a team was that the best method for presenting was on Jupyter or on VSC, refering to the documentation 
