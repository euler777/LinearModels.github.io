# Simple Linear Regression

Motivation: Linear regression is a method that summarizes how the average values of a numerical outcome variable vary over subpopulations defined by linear functions of predictors. Introductory statistics and regression textbooks often focus on how regression can be used to represent relationships between variables, rather than a comparison of average outcomes. By focusing on regression as a comparison of averages, we are being explicit about its limitations for defining these relationships causally.

# Getting Started

To begin, we will load our dataset into Python and R and immediately fit linear model to explore whether or not linear relationships exists in our data.

```markdown
Auto = read.csv("../data/Auto.csv", header=T, na.strings="?")
Auto = na.omit(Auto)
summary(Auto)
attach(Auto)
lm.fit = lm(mpg ~ horsepower)
summary(lm.fit)
```

