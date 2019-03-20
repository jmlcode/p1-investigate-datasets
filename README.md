# Investigate Environment and Economy across Countries with Energy Consumption Data
This project investigates datasets from [Gapminder World](https://www.gapminder.org/data/) and aims to gain insights into countries' environment and economy from their consumption of energy. The analysis covers steps ranging from wrangling data to exploratory data analysis and drawing conclusions.

## Requirements
* Software
  * conda 4.6.3 or similar versions
  * python 3.7.2 (or python 3)
  * Packages
    - pandas
    - numpy
    - copy
    - matplotlib.pyplot
    - seaborn
* Raw Data
  - All `.csv` files of the raw data were manually downloaded from [Gapminder World](https://www.gapminder.org/data/). The __Indicator Name__ of each dataset is listed below in _italics_. The names of the python objects that contain the data in each file are provided in a parenthesis next to the __Indicator Name__.
    - Energy
      1. Oil > _Oil consumption, total_ (`df_energy_oil`)
      2. Coal > _Coal consumption, total_ (`df_energy_coal`)
      3. Total > _Energy use, per person_ (`df_energy_cons`)
      4. Total > _Energy production /person_ (`df_energy_prod`)
    - Environment > Emissions > _CO2 emissions yearly_ (`df_env_co2`)
    - Economy > Incomes & growth > _GDP/capita (USD, inflation-adjusted)_ (`df_gdp`)
  - Although the sizes of the six datasets used in this project are not significantly large, the repository does not include the raw datasets and the cleaned datasets because
    1. the raw datasets can be manually downloaded from [Gapminder World](https://www.gapminder.org/data/) by searching for the __Indicator Name__.
    2. the cleaned datasets can be obtained by cleaning the raw datasets according to the step-by-step wrangling operations documented in the `.ipynb` file.

## Organization of the Investigation
1. Introduction
  * provides a motivation for investigating and analyzing the datasets covering data across _Energy_, _Environment_, and _Economy_.
  * categorizes the investigation and analysis into two separate sections.
    1. CO2 Emissions vs. Oil and Coal Consumption
    2. GDP vs. Energy Consumption
  * provides the __Indicator Name__ of all raw datasets used in each section.
  * introduces the main questions for each section which will be investigated through the following analyses.
2. Data Wrangling
  * identifies several general properties of the raw datasets in each section.
  * builds on these general properties to define and execute the operations for cleaning the raw datasets.
3. Exploratory Data Analysis
  * applies data visualization and descriptive statistics to analyze the cleaned datasets and derive insights.
  * answers the main questions posed in the introduction.
4. Conclusions
  * summarizes the findings from the exploratory data analysis, including trends, correlations, distributions, and possible explanations for the observations.
  * qualifies the findings with limitations of the analysis in terms of investigating causation.

## Version Update from v1.0 to v2.0
1. Data Wrangling Phase > Identify Outliers
    - __Data Cleaning__ section from v1.0 mentioned that visual inspection of the scatter plot was used to determine the lower bounds of `mean_gdp` and `mean_cons` for the outliers. To support this information, the initial scatter plot used to identify the outliers was newly added to the end of the __Data Cleaning__ section for __GDP vs. Energy Consumption__.
2. Code Functionality > Warnings
    - When cleaning the datasets `df_energy_cons_v2` and `df_gdp_v2` to create `df_energy_cons_v3` and `df_gdp_v3`, `copy.copy()` was used to create copies of `df_energy_cons_v2` and `df_gdp_v2` instead of making changes to the original datasets.
3. Code Functionality > Use of Functions
    - In the __Exploratory Data Analysis__ section right before the analysis for __CO2 Emissions vs. Oil and Coal Consumption__, a new sub-section __Custom Functions__ was added, introducing two new functions in order to streamline generation of basic plots such as bar plot and histogram.
      * plot_bar()
          - requires input parameters for the dataframe, the variables for x and y axes, a list containing the labels for the title and the two axes, and the width of each bar
          - generates a bar plot based on the provided input parameters
          - used in __CO2 Emissions vs. Oil and Coal Consumption__ for plotting the mean annual consumption of oil and coal for the top five countries and the mean annual emissions of CO2 for the top five contributors.
      * plot_hist()
          - requires input parameters for the variable, number of bins, and a list containing the labels for the title and the two axes
          - generates a histogram plot based on the provided input parameters
          - used in __GDP vs. Energy Consumption__ for plotting the distribution of each of the two variables, mean annual energy use per person and mean annual GDP/capita.
4. Exploration Phase > Single-variable Exploration
    - __CO2 Emissions vs. Oil and Coal Consumption__
      * Two new bar plots were added, each of which focuses on a single variable:
          - mean annual consumption of oil and coal for the top five countries and
          - the mean annual emissions of CO2 for the top five contributors
      * Findings from reviewing these plots were used to compare the quantities observed across the five countries.
    - __GDP vs. Energy Consumption__
      * Two new histograms were added, each of which focuses on a single variable:
          - mean annual energy use per person in each country and
          - mean annual GDP/capita in each country
      * Findings from reviewing these plots were used to elaborate on the analysis deduced from the scatter plot that the distribution of each variable must be right-skewed.

## Author
Jong Min (Jay) Lee [jmlee5629@gmail.com]

## Acknowledgement
* This project was completed as one of the mandatory requirements for the Data Analyst Nanodegree at Udacity.
* A variety of datasets in [Gapminder World](https://www.gapminder.org/data/), covering various topics across industries and sectors, provided the motivation for applying the knowledge and the technical skills relevant to data analysis to analyzing real datasets and drawing insights from data.
* Online resources including discussions in [Stack Overflow](https://stackoverflow.com/) and technical documentations for packages and methods were referenced throughout the data wrangling and analysis processes.
