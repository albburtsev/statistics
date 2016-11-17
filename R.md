# R cheatsheet

## Basics

```r
# Assign the value 42 to x
x <- 42

# Find out data type
class(1) # "numeric"
class(1.5) # "numeric"
class(TRUE) # "logical"
class("string") # "character"

# Type coercion
as.numeric("3.5") # 3.5
as.numeric("abc") # NA
as.numeric(TRUE) # 1
as.numeric(FALSE) # 0

as.integer(3.5) # 3
as.integer("3.5") # 3

as.character(3) # "3"
as.character(TRUE) # "TRUE"
```

## Vector

```r
# Vector is one-dimension array creates with the combine function `c()`
numeric_vector <- c(1, 2, 3)
character_vector <- c("a", "b", "c")
boolean_vector <- c(TRUE, FALSE)

# Indexing in vectors (begining from 1)
numeric_vector <- c(1, 10, 100)
numeric_vector[2] # 10

# Vector comparison
numeric_vector <- c(1, 10, 100)
numeric_vector < 50 # TRUE TRUE FALSE
numeric_vector < c(0, 50, 99) # FALSE TRUE FALSE

# Selection from vector
c(1,10,100)[c(TRUE, FALSE, TRUE)] # 1 100

# Short syntax
1:9 # 1 2 3 4 5 6 7 8 9
```

## Matrices

```r
# Matrix is a collection of elements of the same data type arranged into a fixed number of rows and columns

matrix(1:9, byrow = TRUE, nrow = 3, ncol = 3)
#      [,1] [,2] [,3]
# [1,]    1    2    3
# [2,]    4    5    6
# [3,]    7    8    9

matrix(1:9, byrow = FALSE, nrow = 3, ncol = 3)
#      [,1] [,2] [,3]
# [1,]    1    4    7
# [2,]    2    5    8
# [3,]    3    6    9
```

## Factors

```r
# Factor is a statistical data type used to store categorical variables
married_status <- factor(c("single", "married", "widower")) # single  married widower
```

## Dataframes

```r
# Data frame has the variables of a data set as columns and the observations as rows.
# Several useful functions:
# `head`: this by default prints the first 6 rows of the dataframe
# `tail`: this by default prints the last 6 rows to the console
# `str`: this prints the structure of your dataframe
# `dim`: this by default prints the dimensions, that is, the number of rows and columns of your dataframe
# `colnames`: this prints the names of the columns of your dataframe

# planets vector
name <- c("Mercury", "Venus", "Earth", "Mars", "Jupiter", "Saturn", "Uranus", "Neptune")

# type vector
type <- c("Terrestrial", "Terrestrial", "Terrestrial", "Terrestrial", "Gas giant", "Gas giant", "Gas giant", "Gas giant")

# diameter vector
diameter <- c(0.382, 0.949, 1, 0.532, 11.209, 9.449, 4.007, 3.883)

# rings vector
rings <- c(FALSE, FALSE, FALSE, FALSE, TRUE, TRUE, TRUE, TRUE)

# construct a dataframe planet_df from all the above variables
planets <- data.frame(name, type, diameter, rings)

planets
#      name        type diameter rings
# 1 Mercury Terrestrial    0.382 FALSE
# 2   Venus Terrestrial    0.949 FALSE
# 3   Earth Terrestrial    1.000 FALSE
# 4    Mars Terrestrial    0.532 FALSE
# 5 Jupiter   Gas giant   11.209  TRUE
# 6  Saturn   Gas giant    9.449  TRUE
# 7  Uranus   Gas giant    4.007  TRUE
# 8 Neptune   Gas giant    3.883  TRUE

planets[2, 1] # Venus

planets$name # Mercury Venus   Earth   Mars    Jupiter Saturn  Uranus  Neptune

planets[4, c(1, 3)]
#   name    diameter
# 4 Mars    0.532

# The first value returned by `dim()` is the number of cases (rows) and the second value is the number of variables (columns)
dim(planets)
# 8 4

# The output of `srt()` shows the variable names, their type, and the values of the first observations
str(planets)
# $ name    : Factor w/ 8 levels "Earth","Jupiter",..: 4 8 1 3 2 6 7 5
# $ type    : Factor w/ 2 levels "Gas giant","Terrestrial": 2 2 2 2 1 1 1 1
# $ diameter: num  0.382 0.949 1 0.532 11.209 ...
# $ rings   : logi  FALSE FALSE FALSE FALSE TRUE TRUE ...

# Shows levels of factor
levels(planets$name)
# "Earth"   "Jupiter" "Mars"    "Mercury" "Neptune" "Saturn"  "Uranus" "Venus"

# To look at a frequency table of the data in R, use the function `table()`
table(planets$type)
# Gas giant Terrestrial 
#         4           4

# The first argument of barplot() is a vector containing the heights of each bar
# Variable `ylab` adds label to Y axis
# Variable `names.arg` should be vector of bar's names
barplot(table(planets$type), ylab = "# of planets", names.arg = c("Gas", "Terra"))

mean(planets$diameter)
# 3.926375

median(planets$diameter)
# 2.4415

sort(planets$diameter)
# 0.382  0.532  0.949  1.000  3.883  4.007  9.449 11.209

sort(planets$diameter, decreasing=TRUE)
# 11.209  9.449  4.007  3.883  1.000  0.949  0.532  0.382

# sort in composition with table helps to find mode
sort(table(c("a", "a", "a", "b", "b", "c")), decreasing=TRUE)
# a b c 
# 3 2 1

range(planets$diameter)
# 0.382 11.209

min(planets$diameter)
# 0.382

max(planets$diameter)
# 11.209

# Easy to calculate quartiles
quantile(planets$diameter)
#      0%      25%      50%      75%     100% 
# 0.38200  0.84475  2.44150  5.36750 11.20900

# Make a boxplot of qsec
boxplot(planets$diameter)

# Calculate the interquartile range of qsec
IQR(planets$diameter)
# 4.52275

# Calculate standard deviation
sd(planets$diameter)
4.226738
```
