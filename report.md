HW 1 - Tool Setup, CS 625, Fall 2022
================
Brock Briggs
Sep 08, 2022

## Git, GitHub

1.  *What is your GitHub username?*

brockbriggs

2.  *What is the URL of your remote GitHub repo (created through
    Mr. Kennedy’s exercises)?*

<https://github.com/odu-cs625-datavis/fall22-hw1-brockbriggs>

## R

The command below will load the tidyverse package. If you have installed
R, RStudio, and the tidyverse package, it should display a list of
loaded packages and their versions.

``` r
library(tidyverse)
```

    ## Warning: package 'tidyverse' was built under R version 4.0.5

    ## -- Attaching packages --------------------------------------- tidyverse 1.3.1 --

    ## v ggplot2 3.3.5     v purrr   0.3.4
    ## v tibble  3.1.4     v dplyr   1.0.7
    ## v tidyr   1.1.3     v stringr 1.4.0
    ## v readr   2.0.1     v forcats 0.5.1

    ## Warning: package 'ggplot2' was built under R version 4.0.5

    ## Warning: package 'tibble' was built under R version 4.0.5

    ## Warning: package 'tidyr' was built under R version 4.0.5

    ## Warning: package 'readr' was built under R version 4.0.5

    ## Warning: package 'purrr' was built under R version 4.0.5

    ## Warning: package 'dplyr' was built under R version 4.0.5

    ## Warning: package 'stringr' was built under R version 4.0.5

    ## Warning: package 'forcats' was built under R version 4.0.5

    ## -- Conflicts ------------------------------------------ tidyverse_conflicts() --
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

Verified tidyverse upload. Packages: ggplot2, tibble, tidyr, readr,
purrr, dplyr, stringr, forcats

## R Markdown

``` r
library(rmarkdown)
```

    ## Warning: package 'rmarkdown' was built under R version 4.0.5

1.  *Create a bulleted list with at least 3 items*

-   Hello
-   I am a bulleted list
-   Thank you for reading my report!

2.  *Write a single paragraph that demonstrates the use of italics,
    bold, bold italics, code, and includes a link. The paragraph does
    not have to make sense.*

This paragraph will be all about how long it took me to complete
**problem number 1**. I was initiating ***r code using \`\`\`{r}*** and
then attempting to use the \* to create a bulleted list. This was
*incorrect* because by opening a markdown file, I don’t need to initiate
anything else - the document is ready to receive r markdown syntax
already. I recognized my mistake after watching this [Youtube
video](https://youtu.be/7bSSah2vBKo). Here is my code portion.

``` r
paste("Hello","World")
```

    ## [1] "Hello World"

3.  *Create a level 3 heading*

### This is a level 3 heading

## R

#### Data Visualization Exercises

1.  (Q2) *How many rows are in mpg? How many columns?*

234 rows 11 columns

``` r
mpg
```

    ## # A tibble: 234 x 11
    ##    manufacturer model      displ  year   cyl trans drv     cty   hwy fl    class
    ##    <chr>        <chr>      <dbl> <int> <int> <chr> <chr> <int> <int> <chr> <chr>
    ##  1 audi         a4           1.8  1999     4 auto~ f        18    29 p     comp~
    ##  2 audi         a4           1.8  1999     4 manu~ f        21    29 p     comp~
    ##  3 audi         a4           2    2008     4 manu~ f        20    31 p     comp~
    ##  4 audi         a4           2    2008     4 auto~ f        21    30 p     comp~
    ##  5 audi         a4           2.8  1999     6 auto~ f        16    26 p     comp~
    ##  6 audi         a4           2.8  1999     6 manu~ f        18    26 p     comp~
    ##  7 audi         a4           3.1  2008     6 auto~ f        18    27 p     comp~
    ##  8 audi         a4 quattro   1.8  1999     4 manu~ 4        18    26 p     comp~
    ##  9 audi         a4 quattro   1.8  1999     4 auto~ 4        16    25 p     comp~
    ## 10 audi         a4 quattro   2    2008     4 manu~ 4        20    28 p     comp~
    ## # ... with 224 more rows

2.  (Q4) *Make a scatterplot of hwy vs cyl.*

``` r
ggplot(data = mpg) +
  geom_point(mapping = aes(x = hwy, y = cyl))
```

![](report_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

#### Workflow: basics Exercises

1.  (Q2) *Tweak each of the following R commands so that they run
    correctly (`library(tidyverse)` is correct):*

``` r
library(tidyverse)
ggplot(dota = mpg) + 
  geom_point(mapping = aes(x = displ, y = hwy))

fliter(mpg, cyl = 8)

filter(diamond, carat > 3)
```

Problems with this code

-   r should be in brackets {r}, all of code is blue so it assumes r is
    part of another command
-   dota should be data
-   fliter should be ‘filter’
-   cyl = 8 should have two ==
-   diamond should have an s on the end

``` r
library(tidyverse)
ggplot(data = mpg) +
  geom_point(mapping = aes(x = displ, y = hwy))
```

![](report_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

``` r
filter(mpg, cyl == 8)
```

    ## # A tibble: 70 x 11
    ##    manufacturer model     displ  year   cyl trans  drv     cty   hwy fl    class
    ##    <chr>        <chr>     <dbl> <int> <int> <chr>  <chr> <int> <int> <chr> <chr>
    ##  1 audi         a6 quatt~   4.2  2008     8 auto(~ 4        16    23 p     mids~
    ##  2 chevrolet    c1500 su~   5.3  2008     8 auto(~ r        14    20 r     suv  
    ##  3 chevrolet    c1500 su~   5.3  2008     8 auto(~ r        11    15 e     suv  
    ##  4 chevrolet    c1500 su~   5.3  2008     8 auto(~ r        14    20 r     suv  
    ##  5 chevrolet    c1500 su~   5.7  1999     8 auto(~ r        13    17 r     suv  
    ##  6 chevrolet    c1500 su~   6    2008     8 auto(~ r        12    17 r     suv  
    ##  7 chevrolet    corvette    5.7  1999     8 manua~ r        16    26 p     2sea~
    ##  8 chevrolet    corvette    5.7  1999     8 auto(~ r        15    23 p     2sea~
    ##  9 chevrolet    corvette    6.2  2008     8 manua~ r        16    26 p     2sea~
    ## 10 chevrolet    corvette    6.2  2008     8 auto(~ r        15    25 p     2sea~
    ## # ... with 60 more rows

``` r
filter(diamonds, carat > 3)
```

    ## # A tibble: 32 x 10
    ##    carat cut     color clarity depth table price     x     y     z
    ##    <dbl> <ord>   <ord> <ord>   <dbl> <dbl> <int> <dbl> <dbl> <dbl>
    ##  1  3.01 Premium I     I1       62.7    58  8040  9.1   8.97  5.67
    ##  2  3.11 Fair    J     I1       65.9    57  9823  9.15  9.02  5.98
    ##  3  3.01 Premium F     I1       62.2    56  9925  9.24  9.13  5.73
    ##  4  3.05 Premium E     I1       60.9    58 10453  9.26  9.25  5.66
    ##  5  3.02 Fair    I     I1       65.2    56 10577  9.11  9.02  5.91
    ##  6  3.01 Fair    H     I1       56.1    62 10761  9.54  9.38  5.31
    ##  7  3.65 Fair    H     I1       67.1    53 11668  9.53  9.48  6.38
    ##  8  3.24 Premium H     I1       62.1    58 12300  9.44  9.4   5.85
    ##  9  3.22 Ideal   I     I1       62.6    55 12545  9.49  9.42  5.92
    ## 10  3.5  Ideal   H     I1       62.8    57 12587  9.65  9.59  6.03
    ## # ... with 22 more rows

## Google Colab

1.  *What are the URLs of your Google Colab notebooks (both Python and
    R)?*
    <https://colab.research.google.com/drive/14q6jmbHJz9RG1P5X57s4pfGtb0mf_OXH?usp=sharing>
    <https://colab.research.google.com/drive/1xPbho6fDlb7fhN8w117u4p4mhhIF7hEW?usp=sharing>

## Tableau

![westsales](https://user-images.githubusercontent.com/112510129/189193381-99b50ce5-2f94-4542-ac25-0085c8489c02.png)

1.  *What conclusions can you draw from the chart?*

Copiers is the fastest growing sub category within the Technology
category with over a 900% increase in profit since 2019.

## Observable and Vega-Lite

### A Taste of Observable

1.  *In the “New York City weather forecast” section, try replacing
    `Forecast: detailedForecast` with `Forecast: shortForecast`. Then
    press the blue play button or use Shift-Return to run your change.
    What happens?*

The forecast description changes from including weather, temperatures,
and wind to only 1-2 words on weather.

2.  *Under the scatterplot of temperature vs. name, try replacing
    `markCircle()` with `markSquare()`. Then press the blue play button
    or use Shift-Return to run your change. What happens? How about
    `markPoint()`?*

The icons in the scatterplot change from circles to squares when
replacing ‘markCircle()’ with ‘markSquare()’. ‘markPoint()’ change
alters the icons to empty outlined circles.

3.  *Under “Pick a location, see the weather forecast”, pick a location
    on the map. Where was the point you picked near?*

Mountain Home, ID

4.  *The last visualization on this page is a “fancy” weather chart
    embedded from another notebook. Click on the 3 dots next to that
    chart and choose ‘Download PNG’. Insert the PNG into your report.*

![weatherChart](https://user-images.githubusercontent.com/112510129/189009954-3af131f7-8b49-48ab-960a-1d04cff1f032.png)
\#also uploaded photo to the repo

### Charting with Vega-Lite

`markCircle()`

1.  *Pass an option of `{ size: 200 }` to `markCircle()`.*

Made the data points on the scatterplot balloon in size with lots of
overlap. Would be good for general ideas but hard to view any specific
data points.

2.  *Try `markSquare` instead of `markCircle`.*

Turns all the circles into squares.

3.  *Try `markPoint({ shape: 'diamond' })`.*

Turned all squares into diamonds.

`vl.x().fieldQ("Horsepower")`, …

1.  *Change `Horsepower` to `Acceleration`*

Shifted from a chart similar to exponential values to more spread out
values but generally centered around 16 mark on acceleration.

2.  *Swap what fields are displayed on the x- and y-axis*

Shifted from a verticle dispersion to horizontal.

`vl.tooltip().fieldN("Name")`

1.  *Change `Name` to `Origin`.*

This made no discernable difference to the acceleration/mpg chart.

Another example, `count()`

1.  *Remove the `vl.y().fieldN("Origin")` line.*

Changed the chart from 3 values to 1.

2.  *Replace `count()` with `average("Miles_per_Gallon")`.*

Adjust charted to show miles per gallon and provided new, applicable
values.

## References

*Every report must list the references that you consulted while
completing the assignment. If you consulted a webpage, you must include
the URL.*

-   Insert Reference 1, <https://youtu.be/7bSSah2vBKo>
-   Insert Reference 2, <https://r4ds.had.co.nz/index.html>
-   Insert Reference 3, <https://rogerdudler.github.io/git-guide/>
-   Insert Reference 4,
    <https://git.cs.odu.edu/tkennedy/git-workshop/-/wikis/Git-Workshop>
-   Insert Reference 5, <https://rmarkdown.rstudio.com/lesson-1.html>
-   Insert Reference 6,
    <https://help.tableau.com/current/guides/get-started-tutorial/en-us/get-started-tutorial-home.htm>
-   Insert Reference 7,
    <https://observablehq.com/@observablehq/introduction-to-data>
-   Insert Reference 8,
    <https://gist.github.com/vinkla/dca76249ba6b73c5dd66a4e986df4c8d#>
-   Insert Reference 9,
    <https://www.dataquest.io/blog/r-markdown-tips-tricks-and-shortcuts/#>
