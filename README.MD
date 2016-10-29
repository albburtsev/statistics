# Basic statistic cheatsheet

## 1. Cases, variables and levels of measurement

Any data set is consists of **cases**: the objects in the collection. Each case has one or more attributes or qualities, called **variables**. This word “variable” emphasizes that it is differences or variation that is often of primary interest. Cases are something or someone for study. Variables are characteristics of something or someone.

### Levels of measurement

The **nominal** variable is made up of various categories, that distinguish from each other, but without order. For example, the nationality of football players (Spanish, French or Mexican) is different from each other, but there is no ranking order.

**Ordinal level** has not only a difference between categories of variables, there is also an order. For example, an order in a football competition. But we don’t know how much team #1 was better than team #2.

With **interval level** we have different categories and an order, but also similar intervals between categories. For example, the age of the football players.

**Ratio level** is like an interval level but has meaningful zero point. For example, the height of football players.

Quantitive variables can also be distinguished in **discrete** and **continuous**.

The method which we employ to analyze data depends on levels of measurement.

|              |          | Difference | Order | Similar intervals | Meaningful zero point |
|---|---|---|---|---|---|
| Categorical  | Nominal  | + | - | - | - |
|              | Ordinal  | + | + | - | - |
| Quantitative | Interval | + | + | + | - |
|              | Ratio    | + | + | + | + |

## 2. Data matrix and frequency table

The **data matrix** is a table with all values of variables for each case. So, it's source of all data for analysis.

|            | Age | Salary |
|---|---|---|
| Worker #1 | 20 | 2 000 |
| Worker #2 | 30 | 3 000  |
| Worker #3 | 40 | 4 000 |

The **frequency table** as a list of all possible values of variable with appropriate **percentage** and **cumulative percentage**.

| Hair color | Frequency | Percentage (%) | Cumulative percentage (%)
|---|---|---|
| Blond | 3 | 30 | 30 |
| Black | 6 | 60  | 90 |
| Ginger | 1 | 10 | 100 |
| Total | 10 | 100 | 100 |

## 3. Graphs

In a **pie chart**, the surface of the slices represent percentages of observations in each category.

Pros: we can see a percentage immediately.

The height of the bars in a **bar graph** represent the percentages of observations in each category.

Pros: easy to retrieve exact number and it can represent high numbers of categories.

Bars in the **histogram** touch each other and this touching represents that the values of an interval ratio variable represent an underlying continuous scale.

## 4. Measures of central tendency

The **mode** is a value, that occurs most frequently (the most common outcome). The pie chart makes it immediately clear what the mode is.

The **median** is a middle value of your observation when they are ordered from the smallest to the largest.

The **mean** is a sum of all values divided by the number of observations.

## 5. Range, interquartile range, outliers and box plot

The **range** is a measure of variability, that calculates as a difference between highest and lowest value.

The **interquartile range** is the distance between third and first quartile (IQR = Q3 — Q1), where quartiles are

```
mim .. Q1 .. Q2 .. Q3 .. max (where Q2 is the same as a median)
```

The main advantage of IQR, that it not affected by outliers.

The **outliers** are the values which lower than `Q1 - 1.5 * IQR` or higher than `Q3 + 1.5 * IQR`.

The **box plot** shows important aspects of distribution in a compact way, using three quartiles, the outliers, and the range of the data after removing the outliers.

## 6. Variance and standard deviation

The **variance** (дисперсия) measures how far a set of numbers are spread out.

Formula:

```
S^2 = SUM((x[i] - mean)^2) / (n - 1)
```

The larger the variance, the large the variability.

The **standard deviation** is a squared root of the variance.
