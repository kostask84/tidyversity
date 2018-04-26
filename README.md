
<!-- README.md is generated from README.Rmd. Please edit that file -->
tidyacademic <img src="man/figures/logo.png" width="160px" align="right" />
===========================================================================

🏫 Tidy tools for academics

Description
-----------

Tidy tools designed for use in academic research. Use functions to wrangle (e.g., wide-to-long or long-to-wide) and statistically analyze (e.g., Cronbach's alpha) data using conventions/techniques commonly observed in academic research. This package uses tidy evaluation (a form of non-standard evaluation) for ease of use and helps researchers keep their data and analysis tidy.

Installation
------------

<!-- You can install the released version of tidyacademic from [CRAN](https://CRAN.R-project.org) with:

``` r
install.packages("tidyacademic")
```
-->
Install the development version from [Github](https://github.com/mkearney/tidyacademic) with:

``` r
## install devtools if not already
if (!requireNamespace("devtools", quietly = TRUE)) {
  install.packages("devtools")
}
## install tidyacademic from Github
devtools::install_github("mkearney/tidyacademic")
```

Data sets
---------

Comes with two data sets.

1.  `polcom_survey` consists of survey responses to demographic, background, and likert-type attitudinal items about political communication.

``` r
polcom_survey
```

1.  `twitter_data` consists of tweet-level observations.

``` r
twitter_data
```

Descriptive statistics
----------------------

Return summary statistics in the form of a data frame.

``` r
## summary stats for social media use (numeric) variables
summarize_numeric(polcom_survey, smuse1:smuse3)

## summary stats for respondent sex and race (categorical) variables
summarize_categorical(polcom_survey, sex, race)
```

Estimate Cronbach's alpha for a set of variables.

``` r
## reliability of social media use items
cronbachs_alpha(polcom_survey, smuse1:smuse3)
```