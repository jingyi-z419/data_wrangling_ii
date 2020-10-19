Exploratory analysis
================

## Strings and regex

``` r
string_vec = c("my", "name", "is", "jingyi")

str_detect(string_vec, "jingyi")  #or a single letter will detect anything contains that particular letter, case sensitive
```

    ## [1] FALSE FALSE FALSE  TRUE

``` r
str_replace(string_vec, "jingyi", "Jingyi") #replace some things
```

    ## [1] "my"     "name"   "is"     "Jingyi"

``` r
string_vec = c(
  "i think we all rule for participating",
  "i think i have been caught",
  "i think this will be quite fun",
  "it will be fun, i think"
)

str_detect(string_vec, "^i think") #detect sth begins with...
```

    ## [1]  TRUE  TRUE  TRUE FALSE

``` r
str_detect(string_vec, "i think$") #detect sth ends with...
```

    ## [1] FALSE FALSE FALSE  TRUE

``` r
string_vec = c(
  "Y' all remember Pres. HW Bush?",
  "I saw a green bush",
  "BBQ and Bushwalking at Molonglo Gorge",
  "BUSH -- LIVE IN CONCERT!!"
)

str_detect(string_vec, "[Bb]ush") #capital or lower case "b"
```

    ## [1]  TRUE  TRUE  TRUE FALSE

``` r
string_vec = c(
  '7th inning stretch',
  '1st half soon to begin. Texas won the toss.',
  'she is 5 feet 4 inches tall',
  '3AM - cant sleep :('
)

#number first followed immediately by a letter
str_detect(string_vec, "[0-9][a-zA-Z]")
```

    ## [1]  TRUE  TRUE FALSE  TRUE

``` r
string_vec = c(
  'Its 7:11 in the evening',
  'want to go to 7-11?',
  'my flight is AA711',
  'NetBios: scanning ip 203.167.114.66'
)

str_detect(string_vec, "7.11") # . will match anything
```

    ## [1]  TRUE  TRUE FALSE  TRUE

``` r
str_detect(string_vec, "7\\.11") # an actual . between two numbers
```

    ## [1] FALSE FALSE FALSE  TRUE

``` r
string_vec = c(
  'The CI is [2, 5]',
  ':-]',
  ':-[',
  'I found the answer on pages [6-7]'
)

str_detect(string_vec, "\\[") # anything has "["
```

    ## [1]  TRUE FALSE  TRUE  TRUE

## Factors

``` r
factor_vec = factor(c("male", "male", "female", "female"))

factor_vec
```

    ## [1] male   male   female female
    ## Levels: female male

``` r
as.numeric(factor_vec) # female = 1, male = 2
```

    ## [1] 2 2 1 1

what happens if i relevel

``` r
factor_vec = fct_relevel(factor_vec, "male") #  you can move factors by hand

factor_vec
```

    ## [1] male   male   female female
    ## Levels: male female

``` r
as.numeric(factor_vec) # male = 1, female = 2
```

    ## [1] 1 1 2 2

fct\_reorder

str\_count str\_locate str\_extract

## NSDUH
