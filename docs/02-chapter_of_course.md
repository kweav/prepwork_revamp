
# A new chapter

*If you haven't yet read the getting started Wiki pages; [start there](https://github.com/jhudsl/OTTR_Template/wiki/Getting-started)

Every chapter needs to start out with this chunk of code:



## Learning Objectives

*Every chapter also needs Learning objectives that will look like this:  

This chapter will cover:  

- {You can use https://tips.uark.edu/using-blooms-taxonomy/ to define some learning objectives here}
- {Another learning objective}

## Libraries

For this chapter, we'll need the following packages attached:

*Remember to add [any additional packages you need to your course's own docker image](https://github.com/jhudsl/OTTR_Template/wiki/Using-Docker#starting-a-new-docker-image).


```r
library(magrittr)
```

# Topic of Section

You can write all your text in sections like this!

## Subtopic

Here's a subheading and some text in this subsection!

### Code examples

You can demonstrate code like this:


```r
output_dir <- file.path("resources", "code_output")
if (!dir.exists(output_dir)) {
  dir.create(output_dir)
}
```

And make plots too:


```r
hist_plot <- hist(iris$Sepal.Length)
```

<img src="resources/images/02-chapter_of_course_files/figure-html/unnamed-chunk-4-1.png" width="672" />

You can also save these plots to file:


```r
png(file.path(output_dir, "test_plot.png"))
hist_plot
```

```
## $breaks
## [1] 4.0 4.5 5.0 5.5 6.0 6.5 7.0 7.5 8.0
## 
## $counts
## [1]  5 27 27 30 31 18  6  6
## 
## $density
## [1] 0.06666667 0.36000000 0.36000000 0.40000000 0.41333333 0.24000000 0.08000000
## [8] 0.08000000
## 
## $mids
## [1] 4.25 4.75 5.25 5.75 6.25 6.75 7.25 7.75
## 
## $xname
## [1] "iris$Sepal.Length"
## 
## $equidist
## [1] TRUE
## 
## attr(,"class")
## [1] "histogram"
```

```r
dev.off()
```

```
## quartz_off_screen 
##                 2
```

### Image example

How to include a Google slide. It's simplest to use the `ottrpal` package:

<img src="resources/images/02-chapter_of_course_files/figure-html//1YmwKdIy9BeQ3EShgZhvtb3MgR8P6iDX4DfFD65W_gdQ_gcc4fbee202_0_141.png" title="Major point!! example image" alt="Major point!! example image" width="480" style="display: block; margin: auto;" />

But if you have the slide or some other image locally downloaded you can also use html like this:

<img src="resources/images/02-chapter_of_course_files/figure-html//1YmwKdIy9BeQ3EShgZhvtb3MgR8P6iDX4DfFD65W_gdQ_gcc4fbee202_0_141.png" title="Major point!! example image" alt="Major point!! example image" style="display: block; margin: auto;" />

### Video examples

To show videos in your course, you can use markdown syntax like this:

[A video we want to show](https://www.youtube.com/embed/VOCYL-FNbr0)

Alternatively, you can use `knitr::include_url()` like this:
Note that we are using `echo=FALSE` in the code chunk because we don't want the code part of this to show up.
If you are unfamiliar with [how R Markdown code chunks work, read this](https://rmarkdown.rstudio.com/lesson-3.html).

<iframe src="https://www.youtube.com/embed/VOCYL-FNbr0" width="672" height="400px" data-external="1"></iframe>

OR this works:

<iframe src="https://www.youtube.com/embed/VOCYL-FNbr0" width="672" height="400px"></iframe>

### Links to files

This works:

<iframe src="https://www.bgsu.edu/content/dam/BGSU/center-for-faculty-excellence/docs/TLGuides/TLGuide-Learning-Objectives.pdf" width="672" height="800px" data-external="1"></iframe>

Or this:

[This works](https://www.bgsu.edu/content/dam/BGSU/center-for-faculty-excellence/docs/TLGuides/TLGuide-Learning-Objectives.pdf).

Or this:

<iframe src="https://www.bgsu.edu/content/dam/BGSU/center-for-faculty-excellence/docs/TLGuides/TLGuide-Learning-Objectives.pdf" width="672" height="800px"></iframe>

### Links to websites

Examples of including a website link.

This works:

<iframe src="https://yihui.org" width="672" height="400px" data-external="1"></iframe>

OR this:

![Another link](https://yihui.org)

OR this:

<iframe src="https://yihui.org" width="672" height="400px"></iframe>

### Citation examples

We can put citations at the end of a sentence like this [@rmarkdown2021].
Or multiple citations [@rmarkdown2021, @Xie2018].

but they need a ; separator [@rmarkdown2021; @Xie2018].

In text, we can put citations like this @rmarkdown2021.

### FYI boxes

::: {.fyi}
Please click on the subsection headers in the left hand
navigation bar (e.g., 2.1, 4.3) a second time to expand the
table of contents and enable the `scroll_highlight` feature
([see more](introduction.html#scroll-highlight)).
:::

### Dropdown summaries

<details><summary> You can hide additional information in a dropdown menu </summary>
Here's more words that are hidden.
</details>

## Print out session info

You should print out session info when you have code for [reproducibility purposes](https://jhudatascience.org/Reproducibility_in_Cancer_Informatics/managing-package-versions.html).


```r
devtools::session_info()
```

```
## ─ Session info ───────────────────────────────────────────────────────────────
##  setting  value
##  version  R version 4.0.3 (2020-10-10)
##  os       macOS Big Sur 10.16
##  system   x86_64, darwin19.6.0
##  ui       unknown
##  language (EN)
##  collate  en_US.UTF-8
##  ctype    en_US.UTF-8
##  tz       America/New_York
##  date     2022-07-26
##  pandoc   2.18 @ /Applications/RStudio.app/Contents/MacOS/quarto/bin/tools/ (via rmarkdown)
## 
## ─ Packages ───────────────────────────────────────────────────────────────────
##  package     * version date (UTC) lib source
##  bookdown      0.26    2022-04-15 [1] CRAN (R 4.0.3)
##  brio          1.1.3   2021-11-30 [1] CRAN (R 4.0.3)
##  bslib         0.3.1   2021-10-06 [1] CRAN (R 4.0.3)
##  cachem        1.0.6   2021-08-19 [1] CRAN (R 4.0.3)
##  callr         3.7.0   2021-04-20 [1] CRAN (R 4.0.3)
##  cli           3.3.0   2022-04-25 [1] CRAN (R 4.0.3)
##  crayon        1.5.1   2022-03-26 [1] CRAN (R 4.0.3)
##  curl          4.3.2   2021-06-23 [1] CRAN (R 4.0.3)
##  desc          1.4.1   2022-03-06 [1] CRAN (R 4.0.3)
##  devtools      2.4.3   2021-11-30 [1] CRAN (R 4.0.3)
##  digest        0.6.29  2021-12-01 [1] CRAN (R 4.0.3)
##  ellipsis      0.3.2   2021-04-29 [1] CRAN (R 4.0.3)
##  evaluate      0.15    2022-02-18 [1] CRAN (R 4.0.3)
##  fansi         1.0.3   2022-03-24 [1] CRAN (R 4.0.3)
##  fastmap       1.1.0   2021-01-25 [1] CRAN (R 4.0.3)
##  fs            1.5.2   2021-12-08 [1] CRAN (R 4.0.3)
##  glue          1.6.2   2022-02-24 [1] CRAN (R 4.0.3)
##  highr         0.9     2021-04-16 [1] CRAN (R 4.0.3)
##  hms           1.1.1   2021-09-26 [1] CRAN (R 4.0.3)
##  htmltools     0.5.2   2021-08-25 [1] CRAN (R 4.0.3)
##  httr          1.4.3   2022-05-04 [1] CRAN (R 4.0.3)
##  jquerylib     0.1.4   2021-04-26 [1] CRAN (R 4.0.3)
##  jsonlite      1.8.0   2022-02-22 [1] CRAN (R 4.0.3)
##  knitr         1.39    2022-04-26 [1] CRAN (R 4.0.3)
##  lifecycle     1.0.1   2021-09-24 [1] CRAN (R 4.0.3)
##  magrittr    * 2.0.3   2022-03-30 [1] CRAN (R 4.0.3)
##  memoise       2.0.1   2021-11-26 [1] CRAN (R 4.0.3)
##  ottrpal       1.0.1   2022-03-03 [1] CRAN (R 4.0.3)
##  pillar        1.7.0   2022-02-01 [1] CRAN (R 4.0.3)
##  pkgbuild      1.3.1   2021-12-20 [1] CRAN (R 4.0.3)
##  pkgconfig     2.0.3   2019-09-22 [1] CRAN (R 4.0.3)
##  pkgload       1.2.4   2021-11-30 [1] CRAN (R 4.0.3)
##  png           0.1-7   2013-12-03 [1] CRAN (R 4.0.3)
##  prettyunits   1.1.1   2020-01-24 [1] CRAN (R 4.0.3)
##  processx      3.5.3   2022-03-25 [1] CRAN (R 4.0.3)
##  ps            1.7.0   2022-04-23 [1] CRAN (R 4.0.3)
##  purrr         0.3.4   2020-04-17 [1] CRAN (R 4.0.3)
##  R6            2.5.1   2021-08-19 [1] CRAN (R 4.0.3)
##  readr         2.1.2   2022-01-30 [1] CRAN (R 4.0.3)
##  remotes       2.4.2   2021-11-30 [1] CRAN (R 4.0.3)
##  rlang         1.0.2   2022-03-04 [1] CRAN (R 4.0.3)
##  rmarkdown     2.14    2022-04-25 [1] CRAN (R 4.0.3)
##  rprojroot     2.0.3   2022-04-02 [1] CRAN (R 4.0.3)
##  rstudioapi    0.13    2020-11-12 [1] CRAN (R 4.0.3)
##  sass          0.4.1   2022-03-23 [1] CRAN (R 4.0.3)
##  sessioninfo   1.2.2   2021-12-06 [1] CRAN (R 4.0.3)
##  stringi       1.7.6   2021-11-29 [1] CRAN (R 4.0.3)
##  stringr       1.4.0   2019-02-10 [1] CRAN (R 4.0.3)
##  testthat      3.1.4   2022-04-26 [1] CRAN (R 4.0.3)
##  tibble        3.1.7   2022-05-03 [1] CRAN (R 4.0.3)
##  tzdb          0.3.0   2022-03-28 [1] CRAN (R 4.0.3)
##  usethis       2.1.6   2022-05-25 [1] CRAN (R 4.0.3)
##  utf8          1.2.2   2021-07-24 [1] CRAN (R 4.0.3)
##  vctrs         0.4.1   2022-04-13 [1] CRAN (R 4.0.3)
##  withr         2.5.0   2022-03-03 [1] CRAN (R 4.0.3)
##  xfun          0.31    2022-05-10 [1] CRAN (R 4.0.3)
##  yaml          2.3.5   2022-02-21 [1] CRAN (R 4.0.3)
## 
##  [1] /usr/local/lib/R/4.0/site-library
##  [2] /usr/local/Cellar/r/4.0.3/lib/R/library
## 
## ──────────────────────────────────────────────────────────────────────────────
```
