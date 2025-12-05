# Exploratory Data Analysis of the Texas Real Estate Market

This project performs an exploratory data analysis (EDA) of the Texas residential real estate market using **R** (including **dplyr**, **ggplot2**, and **moments** libraries). The goal is to apply descriptive statistics and data-visualization techniques to understand how sales activity and prices evolve across cities, months, and years. The full analysis is contained in the R Markdown document and the HTML output can be visulized in this [Github Page](https://lgucrl.github.io/exploratory-data-analysis-real-estate/).



## Dataset

The analysis is based on the `realestate_texas.csv` dataset, which contains monthly observations in the period 2010–2014 for four Texas cities (Beaumont, Bryan–College Station, Tyler, Wichita Falls).

The dataset variables include:

- `city` – city name
- `year`, `month` – reference year and month
- `sales` – number of property sales
- `volume` – total value of sales (in millions of dollars)
- `median_price` – median sale price (USD)
- `listings` – number of active listings
- `months_inventory` – months needed to sell all current listings

## Analytical workflow

1. **Univariate descriptive statistics**  
   The analysis begins with a detailed examination of each numeric variable on its own. For sales, volume, median prices, listings, and months of inventory, it computes classical measures of central tendency (such as minimum, maximum, mean, median, and quartiles) and dispersion (including range, interquartile range, variance, standard deviation, and coefficient of variation). The shape of the distributions is also investigated through skewness and kurtosis, providing an initial sense of whether markets tend to have symmetric or asymmetric price and sales distributions and whether extreme values play an important role.

2. **Frequency distributions**  
   Next, the project organizes both categorical and continuous variables into frequency structures. It produces frequency tables for qualitative and discrete variables like `city`, `year`, and `month`, allowing a quick view of how observations are distributed across locations and time. For continuous variables such as `median_price`, it constructs classes and builds full frequency tables with absolute, relative, and cumulative frequencies. This step helps to visualize how prices are spread across different ranges and to identify typical segments of the market.

3. **Inequality and heterogeneity measures**  
   To quantify how heterogeneous the housing market is in terms of prices, the project computes a normalized Gini index for the classed distributions of median prices. This index summarizes the degree of inequality in a single number, highlighting whether price levels are relatively homogeneous across the observed range or whether they are heavily concentrated in specific value intervals. The Gini index offers a compact way to compare heterogeneity between different segments or time periods.

4. **Probability calculations**  
   Building on the frequency tables, the project derives simple classical probabilities for events defined over the dataset. Examples include the probability that a randomly selected observation corresponds to a given city or month, or that median prices fall within a certain range. These calculations illustrate how descriptive statistics provide the foundation for basic probability reasoning and help to answer questions about how likely specific market configurations are.

5. **Feature engineering**  
   The analysis then introduces new, derived variables to enrich the interpretation of the original data. One such variable is an average sale price (`mean_price`), obtained by combining the total volume of sales with the number of transactions. Another is a measure of listing effectiveness, defined as the ratio of realized to expected sales based on the number of listings and the months of inventory. These engineered features are used to better understand pricing dynamics and market efficiency across cities and over time.

6. **Conditional descriptive analysis**  
   After computing global summaries, the project explores how key metrics behave when conditioned on city, year, and month. It produces tables of means, standard deviations, and other descriptive measures for each group, enabling comparisons such as differences in typical prices between cities, changes in sales volume across years, and seasonal patterns throughout the calendar year. This conditional perspective reveals whether certain markets or periods stand out in terms of activity or price levels.

7. **Visualization with ggplot2**  
   Throughout the analysis, the project uses **ggplot2** to visualize the structure and evolution of the data. It creates density plots, bar charts, boxplots, and violin plots to portray distributions and differences between cities and months. Time-series line charts and smoothed trend lines (with confidence bands) are used to track sales, sales volume, and median prices over the 2010–2014 period, both in aggregate and by city. These visualizations support the numerical findings and make it easier to detect trends, seasonal patterns, and structural differences in the Texas housing markets.

8. **Conclusions**  
   Finally, the project synthesizes the numerical and graphical evidence to draw substantive conclusions about the Texas real estate market. It comments on the degree of price heterogeneity across cities, highlights which locations tend to have higher or lower median prices and sales volumes, and identifies the presence of seasonality in sales (often with peaks in spring and summer). It also notes longer-term upward trends in both activity and prices for most of the cities studied, providing a concise narrative of how these markets behaved over the analyzed time span.

