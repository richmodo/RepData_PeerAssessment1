# Reproducible Research: Peer Assessment 1

## Introduction

This assignment makes use of data from a personal activity monitoring device (e.g. Fitbit, Nike Fuelband, Jawbone, etc.) This device collects data at 5 minute intervals through out the day. The data consists of two months of data from an anonymous individual collected during the months of October and November, 2012 and include the number of steps taken in 5 minute intervals each day.

The data for this assignment was downloaded from the course web site:

**Dataset**: [Activity Monitoring Data](https://d396qusza40orc.cloudfront.net/repdata%2Fdata%2Factivity.zip "Activity monitoring data") [52K]

The variables included in this dataset are:

steps: Number of steps taking in a 5-minute interval (missing values are coded as NA)
date: The date on which the measurement was taken in YYYY-MM-DD format
interval: Identifier for the 5-minute interval in which measurement was taken
The dataset is stored in a comma-separated-value (CSV) file and there are a total of 17,568 observations in this dataset.


```r
#set knitr global options
knitr::opts_chunk$set(echo=FALSE, fig.path='figures/', cache=TRUE, output = 'PA1.md')
```


**Load Libraries for plotting**

```r
library(ggplot2)
library(lattice)
```

## Loading and preprocessing the data



```
##         date steps
## 1 2012-10-02   126
## 2 2012-10-03 11352
## 3 2012-10-04 12116
## 4 2012-10-05 13294
## 5 2012-10-06 15420
## 6 2012-10-07 11015
```

## Mean total number of steps taken per day
For this part of the assignment, I've have ignored the missing values in the dataset.

1. Make a histogram of the total number of steps taken each day


The histogram is created using base plotting package with following code:
![](figures/plot1-1.png)

2. Calculated and report the mean and median total number of steps taken per day

```
## [1] 10766.19
```

```
## [1] 10765
```


## Average daily activity pattern

1. Make a time series plot (i.e. type = "l") of the 5-minute interval (x-axis) and the average number of steps taken, averaged across all days (y-axis)




The time series plot is created using ggplot package with following code:
![](figures/plot2-1.png)

2. Which 5-minute interval, on average across all the days in the dataset, contains the maximum number of steps?




## Imputing missing values

There are a number of days/intervals where there are missing values (coded as NA). The presence of missing days may introduce bias into some calculations or summaries of the data.

1. Calculate and report the total number of missing values in the dataset (i.e. the total number of rows with NAs)



2. Devise a strategy for filling in all of the missing values in the dataset. The strategy does not need to be sophisticated. For example, you could use the mean/median for that day, or the mean for that 5-minute interval, etc.


3. Create a new dataset that is equal to the original dataset but with the missing data filled in.


```
##         date    steps
## 1 2012-10-01 10766.19
## 2 2012-10-02   126.00
## 3 2012-10-03 11352.00
## 4 2012-10-04 12116.00
## 5 2012-10-05 13294.00
## 6 2012-10-06 15420.00
```

4. Make a histogram of the total number of steps taken each day and Calculate and report the mean and median total number of steps taken per day. Do these values differ from the estimates from the first part of the assignment? What is the impact of imputing missing data on the estimates of the total daily number of steps?

Histogram created with the following code:
![](figures/plot3-1.png)


```
## [1] 10766.19
```

```
## [1] 10766.19
```
The mean value has remained the same the strategy of replacing NAs results in consistency

## Are there differences in activity patterns between weekdays and weekends?
For this part the weekdays() function may be of some help here. Use the dataset with the filled-in missing values for this part.

1.  Create a new factor variable in the dataset with two levels - "weekday" and "weekend" indicating whether a given date is a weekday or weekend day.


```
##   dayofweek weekend interval    steps
## 1    Friday weekday        0 8.307244
## 2    Monday weekday        0 9.418355
## 3  Thursday weekday        0 9.375844
## 4   Tuesday weekday        0 0.000000
## 5 Wednesday weekday        0 7.931400
## 6  Saturday weekend        0 4.672825
```

2. Make a panel plot containing a time series plot (i.e. type = "l") of the 5-minute interval (x-axis) and the average number of steps taken, averaged across all weekday days or weekend days (y-axis). See the README file in the GitHub repository to see an example of what this plot should look like using simulated data.

Panel Plot created using lattice package with the following code:
![](figures/plot4-1.png)

## Conclusions

Based upon the panel plot, it appears there is morning activity during the early morning, AM hours.  Perhaps this is a result of walking during the commute to work or exercise.  The weekend appears to have less overall activity.
