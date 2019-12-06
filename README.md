# Simple Linear Regression

Linear regression is a method that summarizes how the average values of a numerical outcome variable vary over subpopulations defined by linear functions of predictors. Introductory statistics and regression textbooks often focus on how regression can be used to represent relationships between variables, rather than a comparison of average outcomes. By focusing on regression as a comparison of averages, we are being explicit about its limitations for defining these relationships causally.

# Getting Started

To begin, we start by loading our first dataset into R to fit a linear model to explore the question of how can we can infer casual relationships with varying levels of certainty and confirm if linear modelling is appropriate for your needs.

See the code in [Python](https://euler777.github.io/pyLinearModels.github.io/)

# R 
```markdown
# Loading Libraries
library(MASS)
library(ISLR)

```

```markdown
# Simple Linear Regression
fix(Boston)
names(Boston)
lm.fit=lm(medv~lstat)
lm.fit=lm(medv~lstat,data=Boston)
attach(Boston)
lm.fit=lm(medv~lstat)
lm.fit
summary(lm.fit)
names(lm.fit)
coef(lm.fit)
confint(lm.fit)
predict(lm.fit,data.frame(lstat=(c(5,10,15))), interval="confidence")
predict(lm.fit,data.frame(lstat=(c(5,10,15))), interval="prediction")
plot(lstat,medv)
abline(lm.fit)
abline(lm.fit,lwd=3)
abline(lm.fit,lwd=3,col="red")
plot(lstat,medv,col="red")
plot(lstat,medv,pch=20)
plot(lstat,medv,pch="+")
plot(1:20,1:20,pch=1:20)
par(mfrow=c(2,2))
plot(lm.fit)
plot(predict(lm.fit), residuals(lm.fit))
plot(predict(lm.fit), rstudent(lm.fit))
plot(hatvalues(lm.fit))
which.max(hatvalues(lm.fit))

```
![image](https://user-images.githubusercontent.com/58537175/70355914-15b28180-1828-11ea-8c28-8f1dc1b8fd00.png)

```markdown
# Multiple Linear Regression

lm.fit=lm(medv~lstat+age,data=Boston)
summary(lm.fit)
lm.fit=lm(medv~.,data=Boston)
summary(lm.fit)
library(car)
vif(lm.fit)
lm.fit1=lm(medv~.-age,data=Boston)
summary(lm.fit1)
lm.fit1=update(lm.fit, ~.-age)

```

```markdown
# Interaction Terms

summary(lm(medv~lstat*age,data=Boston))

```

```markdown
# Non-linear Transformations of the Predictors

lm.fit2=lm(medv~lstat+I(lstat^2))
summary(lm.fit2)
lm.fit=lm(medv~lstat)
anova(lm.fit,lm.fit2)
par(mfrow=c(2,2))
plot(lm.fit2)
lm.fit5=lm(medv~poly(lstat,5))
summary(lm.fit5)
summary(lm(medv~log(rm),data=Boston))

```

```markdown
# Qualitative Predictors

fix(Carseats)
names(Carseats)
lm.fit=lm(Sales~.+Income:Advertising+Price:Age,data=Carseats)
summary(lm.fit)
attach(Carseats)
contrasts(ShelveLoc)


```

```markdown
# Writing Functions

LoadLibraries
LoadLibraries()
LoadLibraries=function(){
 library(ISLR)
 library(MASS)
 print("The libraries have been loaded.")
 }
LoadLibraries
LoadLibraries()


```


