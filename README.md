# Exploratory Data Analysis of the Texas Real Estate Market

This project carries out an exploratory data analysis (EDA) of the Texas residential real estate market using **R** (including **dplyr**, **ggplot2**, and **moments** libraries). The goal is to apply descriptive statistics and data-visualization techniques to understand how sales activity and prices evolve across cities, months, and years. The full analysis is contained in the R Markdown document and the HTML output can be visulized in this [Github Page](https://lgucrl.github.io/exploratory-data-analysis-real-estate/).



## Dataset

The analysis is based on the `realestate_texas.csv` dataset, which contains monthly observations in the period 2010–2014 for four Texas cities (Beaumont, Bryan–College Station, Tyler, Wichita Falls).

The dataset variables include:

- `city`: city name
- `year`, `month`: reference year and month
- `sales`: number of property sales
- `volume`: total value of sales (in millions of dollars)
- `median_price`: median sale price (USD)
- `listings`: number of active listings
- `months_inventory`: months needed to sell all current listings

## Analytical workflow

1. **Univariate descriptive statistics**  
   The analysis starts with a detailed inspection of each single numeric variable. For sales, volume, median prices, listings, and months of inventory, it computes classical measures of central tendency (such as minimum, maximum, mean, median, and quartiles) and dispersion (including range, interquartile range, variance, standard deviation, and coefficient of variation). The shape of the distributions is also investigated through skewness and kurtosis, providing an initial insight of the importance of asymmetric distributions and extreme values.

2. **Frequency distributions and heterogeneity measures**  
   Next, the analysis organizes both categorical and continuous variables into frequency structures. It produces frequency tables for qualitative and discrete variables like `city`, `year`, and `month`, allowing a quick view of how observations are distributed across locations and time. For continuous variables such as `median_price`, it constructs classes and builds full frequency tables with absolute, relative, and cumulative frequencies. The analysis also computes a normalized Gini index for the distributions of median prices, highlighting whether price levels are relatively homogeneous across the observed range or whether they are heavily concentrated in specific value intervals.

3. **Probability calculations**  
   Building on the frequency tables, the analysis derives simple classical probabilities for events defined over the dataset, such as the probability that a randomly selected observation corresponds to a given city or month. These calculations help to answer questions about how likely specific market configurations are.

4. **Feature engineering**  
   The analysis then introduces new, derived variables to enrich the interpretation of the original data, such as an average sale price (`mean_price`), obtained from the total volume of sales and the number of transactions, and a measure of listing effectiveness, defined as the ratio of realized to expected sales based on the number of listings and the months of inventory.

5. **Conditional descriptive analysis**  
   Next, the analysis explores how key metrics behave when conditioned on city, year, and month, by producing tables of means, standard deviations, and other descriptive measures for each group. This conditional analysis enables comparisons such as differences in typical prices between cities, changes in sales volume across years, and seasonal patterns throughout the year.

6. **Visualization with ggplot2**  
   Throughout the analysis, **ggplot2** is used to visualize the structure and evolution of the data. Density plots, bar charts, boxplots and violin plots are created to show distributions and differences between cities and months. Time-series line charts and smoothed trend lines (with confidence bands) are used to track sales, sales volume, and median prices over the 2010–2014 period, both aggregated and by city.

7. **Conclusions**  
   Lastly, the numerical and graphical evidence are synthesized to derive significative conclusions about the Texas real estate market. The final section contains comments on the degree of price heterogeneity across cities, highlights which locations tend to have higher or lower median prices and sales volumes, and identifies the presence of seasonality in sales. It also notes longer-term trends in both activity and prices for the cities analyzed.

