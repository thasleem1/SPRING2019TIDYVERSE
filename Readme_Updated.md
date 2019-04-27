Part 1 : https://rpubs.com/Priya_Shaji/tidyverse

Part 2: 

Github Link : 

For Part 2 request submitted with pull request : 

Tidyverse Assignment
================

"Dplyr", one of the tidyverse package, is used to explore a dataset "drug_use_by_age" and a programming sample “vignette” is executed that demonstrates how to use one or more of the capabilities of the selected TidyVerse package.

## Data Source 

[fivethirtyeight.com]("https://fivethirtyeight.com")

## Drug-use-by-age Dataset

## Using dplyr and ggplot packages of tidyverse to explore Drug-use-by-age Dataset


***
### Dataset Description
***


It covers 13 drugs across 17 age groups.

Header	            Definition


`alcohol-use`	      Percentage of those in an age group who used alcohol in the past 12 months

`alcohol-frequency`	Median number of times a user in an age group used alcohol in the past 12   
                    months
                    
`marijuana-use`	    Percentage of those in an age group who used marijuana in the past 12 months

`marijuana-frequency`	Median number of times a user in an age group used marijuana in the past 12                       months

`cocaine-use`	      Percentage of those in an age group who used cocaine in the past 12 months 

`cocaine-frequency`	Median number of times a user in an age group used cocaine in the past 12                         months

`crack-use`	        Percentage of those in an age group who used crack in the past 12 months

`rack-frequency`  	Median number of times a user in an age group used crack in the past 12 months

`heroin-use`	      Percentage of those in an age group who used heroin in the past 12 months

`heroin-frequency`	Median number of times a user in an age group used heroin in the past 12                          months

`hallucinogen-use`	   Percentage of those in an age group who used hallucinogens in the past 12                         months

`hallucinogen-frequency`	Median number of times a user in an age group used hallucinogens in the                           past 12 months

`inhalant-use`	      Percentage of those in an age group who used inhalants in the past 12 months

`inhalant-frequency`	Median number of times a user in an age group used inhalants in the past 12                       months

`pain-releiver-use`	  Percentage of those in an age group who used pain relievers in the past 12                          months

`pain-releiver-frequency`	Median number of times a user in an age group used pain relievers in the                           past 12 months

`oxycontin-use`	        Percentage of those in an age group who used oxycontin in the past 12                             months

`oxycontin-frequency`	Median number of times a user in an age group used oxycontin in the past 12                       months

`tranquilizer-use`	Percentage of those in an age group who used tranquilizer in the past 12 months

`tranquilizer-frequency`	Median number of times a user in an age group used tranquilizer in the                           past 12 months

`stimulant-use`	      Percentage of those in an age group who used stimulants in the past 12                            months

`stimulant-frequency`	Median number of times a user in an age group used stimulants in the past 12                       months

`meth-use`	          Percentage of those in an age group who used meth in the past 12 months

`meth-frequency`	   Median number of times a user in an age group used meth in the past 12 months

`sedative-use`	    Percentage of those in an age group who used sedatives in the past 12 months

`sedative-frequency`	Median number of times a user in an age group used sedatives in the past 12                       months


***
### Load the dataset
***


1) Install `tidyverse` package and load the dataset

```{r}

#install.packages("tidyverse")
library(tidyverse)

## Using readr to read csv
df_drug <- read_csv('https://raw.githubusercontent.com/fivethirtyeight/data/master/drug-use-by-age/drug-use-by-age.csv')


```

── Attaching packages ─────────────────────────────────────────────────────────────────────────── tidyverse 1.2.1 ──
✔ ggplot2 3.1.0       ✔ purrr   0.3.2  
✔ tibble  2.1.1       ✔ dplyr   0.8.0.1
✔ tidyr   0.8.3       ✔ stringr 1.4.0  
✔ readr   1.3.1       ✔ forcats 0.4.0  
── Conflicts ────────────────────────────────────────────────────────────────────────────── tidyverse_conflicts() ──
✖ dplyr::filter() masks stats::filter()
✖ dplyr::lag()    masks stats::lag()
Parsed with column specification:
cols(
  .default = col_double(),
  age = col_character(),
  `cocaine-frequency` = col_character(),
  `crack-frequency` = col_character(),
  `heroin-frequency` = col_character(),
  `inhalant-frequency` = col_character(),
  `oxycontin-frequency` = col_character(),
  `meth-frequency` = col_character()
)
See spec(...) for full column specifications.


***
### Data Transformations
***


2) Let's explore the data type of all the variables of the dataset using `dplyr::glimpse`

```{r}
#View(df_drug)
dplyr::glimpse(df_drug)
```



3) Using the functions provided by the `dplyr` package, select the columns which ends with `use`


```{r}
drug_use <- df_drug %>%
  select(age,n,ends_with("use"))
```


4) View the dataset `drug-use`

```{r}
head(drug_use)
```

5) Now gather the column names as values for a new column `drugUse_name`


```{r}
#drug_use
drug_use<-drug_use%>%
  gather(-age,-n,key = "drugUse_name",value = "drugUse",`alcohol-use`,
`marijuana-use`,
`cocaine-use`,
`crack-use`,
`heroin-use`,
`hallucinogen-use`,
`inhalant-use`,
`pain-releiver-use`,
`oxycontin-use`,
`tranquilizer-use`,
`stimulant-use`,
`meth-use`,
`sedative-use`
)
```


6) Using the functions provided by the `dplyr` package, select the columns which ends with `frequency`


```{r}
drug_freq <- df_drug %>%
  select(age,n,ends_with("frequency"))
head(drug_freq)
```


7) Now gather the column names as values for a new column `drugFreq_name`

```{r}
drug_freq<-drug_freq%>%
  gather(-age,-n,key = "drugFreq_name",value = "drugFreq",`alcohol-frequency`,
`marijuana-frequency`,
`cocaine-frequency`,
`crack-frequency`,
`heroin-frequency`,
`hallucinogen-frequency`,
`inhalant-frequency`,
`pain-releiver-frequency`,
`oxycontin-frequency`,
`tranquilizer-frequency`,
`stimulant-frequency`,
`meth-frequency`,
`sedative-frequency`
)
```


8) Merge the two datasets `drug_use` and `drug_freq` in a single dataframe as `tidy_drug_data` using `full_join()` as a function provided by the `dplyr` package


```{r}
tidy_drug_data <- full_join(drug_use,drug_freq,by=c("age","n"))

head(tidy_drug_data)
```


9) Use `ggplot()` along with `facet_wrap` to individually plot the variation of drugs with age.


```{r}

drugUse_plot <- ggplot(tidy_drug_data,aes(x = age, y = drugUse,color=drugUse_name)) +

  geom_point() +
  
  facet_wrap(~ drugUse_name, nrow = 5) + 
  geom_smooth(color = "black")

drugUse_plot 

```


By plotting the graphs individually for each drug, it gives us a clear picture of which drug usage is higher at particular ages compared to other drugs.


10) Here ggplot() is used to plot the drug use rate varying with age. As we see in the data description,`n` is the number of people survyed for a particular drug. 

```{r}
ggplot(data = tidy_drug_data, 
    mapping = aes(x = age, y = drugUse)) + 
    geom_point(aes(fill = drugUse_name, size = n), shape = 21, color = "white") + 
    geom_smooth(aes(x = age, y = drugUse)) +
    labs(
        x = "Age", 
        y = "Drug use rate", 
        title = "drug use Data",
        subtitle = "ages with drug use rate",
        caption = "Source: ggplot2 package") + 
    scale_color_brewer(palette = "Set1") + 
    scale_size(range = c(0, 12)) +
    guides(size = guide_legend(override.aes = list(col = "black")), 
           fill = guide_legend(override.aes = list(size = 5))) +
    theme_bw()
```



11)  Using `filter()` function of `dplyr` package of tidyverse to group drugs whose usage is greater than 60%


```{r}

head(tidy_drug_data %>% 
    filter(`drugUse` > 60 ))

```

***
### Conclusion
***

```{r}
ggplot(data = tidy_drug_data, 
    mapping = aes(x = age, y = drugUse)) + 
    geom_point(aes(fill = drugUse_name, size = n), shape = 21, color = "white") + 
    geom_smooth(aes(x = age, y = drugUse)) +
    labs(
        x = "Age", 
        y = "Drug use rate", 
        title = "drug use Data",
        subtitle = "ages with drug use rate",
        caption = "Source: ggplot2 package") + 
    scale_color_brewer(palette = "Set1") + 
    scale_size(range = c(0, 12)) +
    guides(size = guide_legend(override.aes = list(col = "black")), 
           fill = guide_legend(override.aes = list(size = 5))) +
    theme_bw()
```

As we can see, from the graphs and also from filtering data : 

Alcohol is the most abused drug among the age group of 22-23.

More than 80% Percentage of those in an age group of 22-23 who used alcohol in the past 12 months.
