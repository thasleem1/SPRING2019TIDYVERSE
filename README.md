# CUNY DATA 607 Spring 2019 Tidyverse recipes

You have two tasks:

**Create an Example**  Using one or more TidyVerse packages, and any dataset from fivethirtyeight.com or Kaggle, create a programming sample “vignette” that demonstrates how to use one or more of the capabilities of the selected TidyVerse package with your selected dataset. (25 points)

**Extend an Existing Example**  Using one of your classmate’s examples (as created above), extend his or her example with additional annotated code. (15 points)

You should clone the provided repository.  Once you have code to submit, you should make a pull request on the shared repository.  Minimally, you should be submitted .Rmd files; ideally, you should also submit an .md file and update the README.md file with your example.

*After you’ve completed both parts of the assignment, please submit your GitHub handle name in the submission link provided in the week 1 folder!* This will let your instructor know that your work is ready to be graded.

You should complete both parts of the assignment and make your submission no later than end of day on Sunday, May 12th.

In this assignment, you’ll practice collaborating around a code project with GitHub.  You could consider our collective work as building out a book of examples on how to use TidyVerse functions.

* GitHub repository:  https://github.com/acatlin/SPRING2019TIDYVERSE
* FiveThirtyEight.com datasets:  https://data.fivethirtyeight.com/
* Kaggle datasets:  https://www.kaggle.com/datasets

## dplyr

### Ryan Gordon - mutate_all(), mutate_if(), mutate_at(), http://rpubs.com/rg563/TidyVerse_mutate
### Jimmy Ng - case_when, https://github.com/acatlin/SPRING2019TIDYVERSE/blob/master/tidyverse_recipe_case_when_JN.Rmd
### David Apolinar: Part 1 group_by, arrange, summarise, https://github.com/dapolloxp/SPRING2019TIDYVERSE-1/blob/master/tidyverseDavidA.Rmd
### Part 2: https://github.com/dapolloxp/SPRING2019TIDYVERSE-1/blob/master/perez_tidyverse_lubridate.Rmd
## ggplot2

### Samantha Deokinanan

My aim is to demonstrate how tidyverse's `ggplot2` can create basic and advanced visualizations that can capture valuable information, and provide a clear, analytical representation of the data in an easily understandable way. For the second part, I expanded on [Jimmy Ng's](https://github.com/myvioletrose/SPRING2019TIDYVERSE/blob/master/tidyverse_recipe_case_when_JN.Rmd) tidyverse recipe as I have never used `dplyr::case_when`, and thought `dplyr::if_else` and `dplyr::recode` could produced the same outputs. 

RPUB:

Part 1: http://rpubs.com/greeneyefirefly/data607-tidyverse-p1

Part 2: http://rpubs.com/greeneyefirefly/data607-tidyverse-p2

***

### Magrittr Piping Example

Provides a comparison of performing data wrangling on a heart disease dataset with and without using the %>% and %<>% Magrittr pipe operators.

David Apolinar: https://github.com/dapolloxp/SPRING2019TIDYVERSE-1/blob/master/tidyverseDavidA.Rmd
Extensions in John Perez's: https://github.com/dapolloxp/SPRING2019TIDYVERSE-1/blob/master/perez_tidyverse_lubridate.Rmd

## purrr


### Javern Wilson
The packages chosen for this assignment are Purrr and Stringr
https://github.com/acatlin/SPRING2019TIDYVERSE/blob/master/DATA607%20Tidyverse%20Assignment.Rmd

## base R vs. tidyverse

### Jadgish Chhabria

I have created a brief vignette showing the different approaches to some common data wrangling tasks using base R versus tidyverse.

The associated data set has been posted on github: https://raw.githubusercontent.com/Jagdish16/jagdish_r_repo/master/DATA607/camera_dataset.csv
 and the html file can be found here: bs.com/Jagdish/ds607_tidyverse_vignette

## tibbles
 
### Austin Chan
I decided to do my tidyverse assignment on the tibbles package. The rmarkdown code has been posted to this repository and the html file can be found here: http://rpubs.com/ilawl/490256

## Nest and Unnest

### Isabel R.
I will focus on how to use the `Nest` and `Unnest` functions utilizing data from *FiveThirtyEight*,"How Popular Is Donald Trump?" from the trump-approval-ratings data set. The rmarkdown code has been posted to this repository and the html file can be found here: http://rpubs.com/IsabelR/TidyVerseAssignment


## ggplot2 - usmap

### Mohamed
Task1 - Have used the ggplot2 capabilities to extend us-map (heat waves) graphs
Task2 - Extension of Javern Wilson Code

rpubs links:
tidyverse task1: http://rpubs.com/thasleem/d607_tva_t1
tidyverse task2: http://rpubs.com/thasleem/d607_tva_t2
