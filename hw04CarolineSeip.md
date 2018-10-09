hw04CarolineSeip
================
Caroline Seip
October 3, 2018

Table of Contents
=================

-   Data reshaping: Activity \#2
-   

Data reshaping: Activity \#2
============================

Make a tibble with one row per year and columns for life expectancy for two or more countries. - Use knitr::kable() to make this table look pretty in your rendered homework. - Take advantage of this new data shape to scatterplot life expectancy for one country against that of another.

First let's load the dataset, tidyverse and knitr:

``` r
#Load gapminder dataset
library(gapminder)
#Load tidyverse to use dplyr and ggplot
library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────────────────────── tidyverse 1.2.1 ──

    ## ✔ ggplot2 3.0.0     ✔ purrr   0.2.5
    ## ✔ tibble  1.4.2     ✔ dplyr   0.7.6
    ## ✔ tidyr   0.8.1     ✔ stringr 1.3.1
    ## ✔ readr   1.1.1     ✔ forcats 0.3.0

    ## ── Conflicts ────────────────────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
#Load knitr to use the kable function
library(knitr)
```

Now let's make a formatted table of life expectancy for each year in Australia and New Zealand:

``` r
#Use the gapminder dataset
gapminder %>%
  #Filter so that we are only using Oceania (Australia and New Zealand)
  filter(continent=="Oceania") %>% 
  #Select the columns country, year and life expectancy
  select(country, year, lifeExp) %>% 
  #Make a table, rename column headings
  kable(col.names = c("Country", "Year", "Life expectancy (years)"))
```

| Country     |  Year|  Life expectancy (years)|
|:------------|-----:|------------------------:|
| Australia   |  1952|                   69.120|
| Australia   |  1957|                   70.330|
| Australia   |  1962|                   70.930|
| Australia   |  1967|                   71.100|
| Australia   |  1972|                   71.930|
| Australia   |  1977|                   73.490|
| Australia   |  1982|                   74.740|
| Australia   |  1987|                   76.320|
| Australia   |  1992|                   77.560|
| Australia   |  1997|                   78.830|
| Australia   |  2002|                   80.370|
| Australia   |  2007|                   81.235|
| New Zealand |  1952|                   69.390|
| New Zealand |  1957|                   70.260|
| New Zealand |  1962|                   71.240|
| New Zealand |  1967|                   71.520|
| New Zealand |  1972|                   71.890|
| New Zealand |  1977|                   72.220|
| New Zealand |  1982|                   73.840|
| New Zealand |  1987|                   74.320|
| New Zealand |  1992|                   76.330|
| New Zealand |  1997|                   77.550|
| New Zealand |  2002|                   79.110|
| New Zealand |  2007|                   80.204|
