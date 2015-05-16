---
title: "PA1_template"
author: "Vidushi Chaudhary"
date: "Saturday, May 16, 2015"
output: html_document
---

This is an R Markdown document. Markdown is a simple formatting syntax for authoring HTML, PDF, and MS Word documents. For more details on using R Markdown see <http://rmarkdown.rstudio.com>.

When you click the **Knit** button a document will be generated that includes both content as well as the output of any embedded R code chunks within the document. You can embed an R code chunk like this:

```{r}

```



```{r, echo=TRUE}

```

Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.

Basic settings

echo = TRUE  # Always make code visible
options(scipen = 1)  # Turn off scientific notations for numbers
Loading and processing the data

unzip("activity.zip")
data <- read.csv("activity.csv", colClasses = c("integer", "Date", "factor"))
attach(data)
## The following object is masked from avgSteps (position 3):
## 
##     interval
## The following objects are masked from newData (position 4):
## 
##     date, interval, steps
## The following objects are masked from newData (position 5):
## 
##     date, interval, steps
## The following object is masked from avgSteps (position 6):
## 
##     interval
## The following objects are masked from noNA (position 7):
## 
##     date, interval, steps
## The following objects are masked from data (position 8):
## 
##     date, interval, steps
## The following object is masked from avgSteps (position 9):
## 
##     interval
## The following objects are masked from newData (position 10):
## 
##     date, interval, steps
## The following objects are masked from newData (position 11):
## 
##     date, interval, steps
## The following object is masked from avgSteps (position 12):
## 
##     interval
## The following objects are masked from noNA (position 13):
## 
##     date, interval, steps
## The following objects are masked from data (position 14):
## 
##     date, interval, steps
## The following object is masked from avgSteps (position 16):
## 
##     interval
## The following objects are masked from newData (position 17):
## 
##     date, interval, steps
## The following objects are masked from noNA (position 18):
## 
##     date, interval, steps
## The following objects are masked from noNA (position 19):
## 
##     date, interval, steps
## The following objects are masked from noNA (position 20):
## 
##     date, interval, steps
## The following objects are masked from newData (position 21):
## 
##     date, interval, steps
## The following objects are masked from noNA (position 22):
## 
##     date, interval, steps
## The following objects are masked from data (position 23):
## 
##     date, interval, steps
## The following object is masked from avgSteps (position 24):
## 
##     interval
## The following objects are masked from data (position 25):
## 
##     date, interval, steps
## The following objects are masked from data (position 26):
## 
##     date, interval, steps
## The following object is masked from avgSteps (position 27):
## 
##     interval
## The following objects are masked from data (position 28):
## 
##     date, interval, steps
## The following objects are masked from data (position 29):
## 
##     date, interval, steps
## The following objects are masked from noNA (position 31):
## 
##     date, interval, steps
## The following objects are masked from noNA (position 32):
## 
##     date, interval, steps
## The following objects are masked from dataWithoutNA (position 35):
## 
##     date, interval, steps
## The following objects are masked from dataWithoutNA (position 36):
## 
##     date, interval, steps
## The following objects are masked from dataWithoutNA (position 37):
## 
##     date, interval, steps
## The following objects are masked from dataWithoutNA (position 38):
## 
##     date, interval, steps
## The following objects are masked from dataWithoutNA (position 39):
## 
##     date, interval, steps
## The following objects are masked from data (position 41):
## 
##     date, interval, steps
data$month <- as.numeric(format(date, "%m"))
noNA <- na.omit(data)
rownames(noNA) <- 1:nrow(noNA)
head(noNA)
##   steps       date interval month
## 1     0 2012-10-02        0    10
## 2     0 2012-10-02        5    10
## 3     0 2012-10-02       10    10
## 4     0 2012-10-02       15    10
## 5     0 2012-10-02       20    10
## 6     0 2012-10-02       25    10
dim(noNA)
## [1] 15264     4
library(ggplot2)
What is mean total number of steps taken per day?

For this part of the assignment, you can ignore the missing values in the dataset.

Make a histogram of the total number of steps taken each day
attach(noNA)
## The following objects are masked from data (position 3):
## 
##     date, interval, steps
## The following object is masked from avgSteps (position 4):
## 
##     interval
## The following objects are masked from newData (position 5):
## 
##     date, interval, month, steps
## The following objects are masked from newData (position 6):
## 
##     date, interval, month, steps
## The following object is masked from avgSteps (position 7):
## 
##     interval
## The following objects are masked from noNA (position 8):
## 
##     date, interval, month, steps
## The following objects are masked from data (position 9):
## 
##     date, interval, steps
## The following object is masked from avgSteps (position 10):
## 
##     interval
## The following objects are masked from newData (position 11):
## 
##     date, interval, month, steps
## The following objects are masked from newData (position 12):
## 
##     date, interval, month, steps
## The following object is masked from avgSteps (position 13):
## 
##     interval
## The following objects are masked from noNA (position 14):
## 
##     date, interval, month, steps
## The following objects are masked from data (position 15):
## 
##     date, interval, steps
## The following object is masked from avgSteps (position 17):
## 
##     interval
## The following objects are masked from newData (position 18):
## 
##     date, interval, month, steps
## The following objects are masked from noNA (position 19):
## 
##     date, interval, month, steps
## The following objects are masked from noNA (position 20):
## 
##     date, interval, month, steps
## The following objects are masked from noNA (position 21):
## 
##     date, interval, month, steps
## The following objects are masked from newData (position 22):
## 
##     date, interval, month, steps
## The following objects are masked from noNA (position 23):
## 
##     date, interval, month, steps
## The following objects are masked from data (position 24):
## 
##     date, interval, steps
## The following object is masked from avgSteps (position 25):
## 
##     interval
## The following objects are masked from data (position 26):
## 
##     date, interval, steps
## The following objects are masked from data (position 27):
## 
##     date, interval, steps
## The following object is masked from avgSteps (position 28):
## 
##     interval
## The following objects are masked from data (position 29):
## 
##     date, interval, steps
## The following objects are masked from data (position 30):
## 
##     date, interval, steps
## The following objects are masked from noNA (position 32):
## 
##     date, interval, steps
## The following objects are masked from noNA (position 33):
## 
##     date, interval, month, steps
## The following objects are masked from dataWithoutNA (position 36):
## 
##     date, interval, month, steps
## The following objects are masked from dataWithoutNA (position 37):
## 
##     date, interval, month, steps
## The following objects are masked from dataWithoutNA (position 38):
## 
##     date, interval, steps
## The following objects are masked from dataWithoutNA (position 39):
## 
##     date, interval, steps
## The following objects are masked from dataWithoutNA (position 40):
## 
##     date, interval, steps
## The following objects are masked from data (position 42):
## 
##     date, interval, steps
ggplot(noNA, aes(date, steps)) + geom_bar(stat = "identity", colour = "steelblue", fill = "steelblue", width = 0.7) + facet_grid(. ~ month, scales = "free") + labs(title = "Histogram of Total Number of Steps Taken Each Day", x = "Date", y = "Total number of steps")
plot of chunk unnamed-chunk-3

Calculate and report the mean and median total number of steps taken per day
Mean total number of steps taken per day:

totalSteps <- aggregate(steps, list(Date = date), FUN = "sum")$x
mean(totalSteps)
## [1] 10766
Median total number of steps taken per day:

median(totalSteps)
## [1] 10765
What is the average daily activity pattern?

Make a time series plot (i.e. type = "l") of the 5-minute interval (x-axis) and the average number of steps taken, averaged across all days (y-axis)
avgSteps <- aggregate(steps, list(interval = as.numeric(as.character(interval))), FUN = "mean")

ggplot(avgSteps, aes(interval, y = x)) + geom_line(color = "steelblue", size = 0.8) + labs(title = "Time Series Plot of the 5-minute Interval", x = "5-minute intervals", y = "Average Number of Steps Taken")
plot of chunk unnamed-chunk-6

Which 5-minute interval, on average across all the days in the dataset, contains the maximum number of steps?
attach(avgSteps)
## The following object is masked from noNA (position 3):
## 
##     interval
## The following object is masked from data (position 4):
## 
##     interval
## The following object is masked from avgSteps (position 5):
## 
##     interval
## The following object is masked from newData (position 6):
## 
##     interval
## The following object is masked from newData (position 7):
## 
##     interval
## The following object is masked from avgSteps (position 8):
## 
##     interval
## The following object is masked from noNA (position 9):
## 
##     interval
## The following object is masked from data (position 10):
## 
##     interval
## The following object is masked from avgSteps (position 11):
## 
##     interval
## The following object is masked from newData (position 12):
## 
##     interval
## The following object is masked from newData (position 13):
## 
##     interval
## The following object is masked from avgSteps (position 14):
## 
##     interval
## The following object is masked from noNA (position 15):
## 
##     interval
## The following object is masked from data (position 16):
## 
##     interval
## The following object is masked from avgSteps (position 18):
## 
##     interval
## The following object is masked from newData (position 19):
## 
##     interval
## The following object is masked from noNA (position 20):
## 
##     interval
## The following object is masked from noNA (position 21):
## 
##     interval
## The following object is masked from noNA (position 22):
## 
##     interval
## The following object is masked from newData (position 23):
## 
##     interval
## The following object is masked from noNA (position 24):
## 
##     interval
## The following object is masked from data (position 25):
## 
##     interval
## The following objects are masked from avgSteps (position 26):
## 
##     interval, x
## The following object is masked from data (position 27):
## 
##     interval
## The following object is masked from data (position 28):
## 
##     interval
## The following objects are masked from avgSteps (position 29):
## 
##     interval, x
## The following object is masked from data (position 30):
## 
##     interval
## The following object is masked from data (position 31):
## 
##     interval
## The following object is masked from avgSteps (position 32):
## 
##     x
## The following object is masked from noNA (position 33):
## 
##     interval
## The following object is masked from noNA (position 34):
## 
##     interval
## The following object is masked from dataWithoutNA (position 37):
## 
##     interval
## The following object is masked from dataWithoutNA (position 38):
## 
##     interval
## The following object is masked from dataWithoutNA (position 39):
## 
##     interval
## The following object is masked from dataWithoutNA (position 40):
## 
##     interval
## The following object is masked from dataWithoutNA (position 41):
## 
##     interval
## The following object is masked from data (position 43):
## 
##     interval
avgSteps[x == max(x), ]
##     interval     x
## 104      835 206.2
Imputing missing values

The total number of rows with NAs:
sum(is.na(data))
## [1] 2304
Devise a strategy for filling in all of the missing values in the dataset. The strategy does not need to be sophisticated. For example, you could use the mean/median for that day, or the mean for that 5-minute interval, etc.
My strategy is to use the mean for that 5-minute interval to fill each NA value in the steps column.

Create a new dataset that is equal to the original dataset but with the missing data filled in.
newData <- data 
for (i in 1:nrow(newData)) {
    if (is.na(newData$steps[i])) {
        newData$steps[i] <- avgSteps[which(newData$interval[i] == avgSteps$interval), ]$x
    }
}

head(newData)
##     steps       date interval month
## 1 1.71698 2012-10-01        0    10
## 2 0.33962 2012-10-01        5    10
## 3 0.13208 2012-10-01       10    10
## 4 0.15094 2012-10-01       15    10
## 5 0.07547 2012-10-01       20    10
## 6 2.09434 2012-10-01       25    10
sum(is.na(newData))
## [1] 0
Make a histogram of the total number of steps taken each day and Calculate and report the mean and median total number of steps taken per day.
ggplot(newData, aes(date, steps)) + geom_bar(stat = "identity", colour = "steelblue", fill = "steelblue", width = 0.7) + facet_grid(. ~ month, scales = "free") + labs(title = "Histogram of Total Number of Steps Taken Each Day (no missing data)", x = "Date", y = "Total number of steps")
plot of chunk unnamed-chunk-10

Do these values differ from the estimates from the first part of the assignment? What is the impact of imputing missing data on the estimates of the total daily number of steps?

Mean total number of steps taken per day:

attach(newData)
## The following object is masked from avgSteps (position 3):
## 
##     interval
## The following objects are masked from noNA (position 4):
## 
##     date, interval, month, steps
## The following objects are masked from data (position 5):
## 
##     date, interval, steps
## The following object is masked from avgSteps (position 6):
## 
##     interval
## The following objects are masked from newData (position 7):
## 
##     date, interval, month, steps
## The following objects are masked from newData (position 8):
## 
##     date, interval, month, steps
## The following object is masked from avgSteps (position 9):
## 
##     interval
## The following objects are masked from noNA (position 10):
## 
##     date, interval, month, steps
## The following objects are masked from data (position 11):
## 
##     date, interval, steps
## The following object is masked from avgSteps (position 12):
## 
##     interval
## The following objects are masked from newData (position 13):
## 
##     date, interval, month, steps
## The following objects are masked from newData (position 14):
## 
##     date, interval, month, steps
## The following object is masked from avgSteps (position 15):
## 
##     interval
## The following objects are masked from noNA (position 16):
## 
##     date, interval, month, steps
## The following objects are masked from data (position 17):
## 
##     date, interval, steps
## The following object is masked from avgSteps (position 19):
## 
##     interval
## The following objects are masked from newData (position 20):
## 
##     date, interval, month, steps
## The following objects are masked from noNA (position 21):
## 
##     date, interval, month, steps
## The following objects are masked from noNA (position 22):
## 
##     date, interval, month, steps
## The following objects are masked from noNA (position 23):
## 
##     date, interval, month, steps
## The following objects are masked from newData (position 24):
## 
##     date, interval, month, steps
## The following objects are masked from noNA (position 25):
## 
##     date, interval, month, steps
## The following objects are masked from data (position 26):
## 
##     date, interval, steps
## The following object is masked from avgSteps (position 27):
## 
##     interval
## The following objects are masked from data (position 28):
## 
##     date, interval, steps
## The following objects are masked from data (position 29):
## 
##     date, interval, steps
## The following object is masked from avgSteps (position 30):
## 
##     interval
## The following objects are masked from data (position 31):
## 
##     date, interval, steps
## The following objects are masked from data (position 32):
## 
##     date, interval, steps
## The following objects are masked from noNA (position 34):
## 
##     date, interval, steps
## The following objects are masked from noNA (position 35):
## 
##     date, interval, month, steps
## The following objects are masked from dataWithoutNA (position 38):
## 
##     date, interval, month, steps
## The following objects are masked from dataWithoutNA (position 39):
## 
##     date, interval, month, steps
## The following objects are masked from dataWithoutNA (position 40):
## 
##     date, interval, steps
## The following objects are masked from dataWithoutNA (position 41):
## 
##     date, interval, steps
## The following objects are masked from dataWithoutNA (position 42):
## 
##     date, interval, steps
## The following objects are masked from data (position 44):
## 
##     date, interval, steps
newTotalSteps <- aggregate(steps, list(Date = date), FUN = "sum")$x
newMean <- mean(newTotalSteps)
newMean
## [1] 10766
Median total number of steps taken per day:

newMedian <- median(newTotalSteps)
newMedian
## [1] 10766
Compare them with the two before imputing missing data:

oldMean <- mean(totalSteps)
oldMedian <- median(totalSteps)
newMean - oldMean
## [1] 0
newMedian - oldMedian
## [1] 1.189
So, after imputing the missing data, the new mean of total steps taken per day is the same as that of the old mean; the new median of total steps taken per day is greater than that of the old median.

Are there differences in activity patterns between weekdays and weekends?

Create a new factor variable in the dataset with two levels -- "weekday" and "weekend" indicating whether a given date is a weekday or weekend day.
head(newData)
##     steps       date interval month
## 1 1.71698 2012-10-01        0    10
## 2 0.33962 2012-10-01        5    10
## 3 0.13208 2012-10-01       10    10
## 4 0.15094 2012-10-01       15    10
## 5 0.07547 2012-10-01       20    10
## 6 2.09434 2012-10-01       25    10
newData$weekdays <- factor(format(newData$date, "%A"))
levels(newData$weekdays)
## [1] "Friday"    "Monday"    "Saturday"  "Sunday"    "Thursday"  "Tuesday"  
## [7] "Wednesday"
levels(newData$weekdays) <- list(weekday = c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday"), weekend = c("Saturday", "Sunday"))
levels(newData$weekdays)
## [1] "weekday" "weekend"
table(newData$weekdays)
## 
## weekday weekend 
##   12960    4608
Make a panel plot containing a time series plot (i.e. type = "l") of the 5-minute interval (x-axis) and the average number of steps taken, averaged across all weekday days or weekend days (y-axis).
attach(newData)
## The following objects are masked from newData (position 3):
## 
##     date, interval, month, steps
## The following object is masked from avgSteps (position 4):
## 
##     interval
## The following objects are masked from noNA (position 5):
## 
##     date, interval, month, steps
## The following objects are masked from data (position 6):
## 
##     date, interval, steps
## The following objects are masked from avgSteps (position 7):
## 
##     interval, weekdays
## The following objects are masked from newData (position 8):
## 
##     date, interval, month, steps, weekdays
## The following objects are masked from newData (position 9):
## 
##     date, interval, month, steps
## The following objects are masked from avgSteps (position 10):
## 
##     interval, weekdays
## The following objects are masked from noNA (position 11):
## 
##     date, interval, month, steps
## The following objects are masked from data (position 12):
## 
##     date, interval, steps
## The following objects are masked from avgSteps (position 13):
## 
##     interval, weekdays
## The following objects are masked from newData (position 14):
## 
##     date, interval, month, steps, weekdays
## The following objects are masked from newData (position 15):
## 
##     date, interval, month, steps
## The following objects are masked from avgSteps (position 16):
## 
##     interval, weekdays
## The following objects are masked from noNA (position 17):
## 
##     date, interval, month, steps
## The following objects are masked from data (position 18):
## 
##     date, interval, steps
## The following objects are masked from avgSteps (position 20):
## 
##     interval, weekdays
## The following objects are masked from newData (position 21):
## 
##     date, interval, month, steps, weekdays
## The following objects are masked from noNA (position 22):
## 
##     date, interval, month, steps
## The following objects are masked from noNA (position 23):
## 
##     date, interval, month, steps
## The following objects are masked from noNA (position 24):
## 
##     date, interval, month, steps
## The following objects are masked from newData (position 25):
## 
##     date, interval, month, steps
## The following objects are masked from noNA (position 26):
## 
##     date, interval, month, steps
## The following objects are masked from data (position 27):
## 
##     date, interval, steps
## The following object is masked from avgSteps (position 28):
## 
##     interval
## The following objects are masked from data (position 29):
## 
##     date, interval, steps
## The following objects are masked from data (position 30):
## 
##     date, interval, steps
## The following object is masked from avgSteps (position 31):
## 
##     interval
## The following objects are masked from data (position 32):
## 
##     date, interval, steps
## The following objects are masked from data (position 33):
## 
##     date, interval, steps
## The following objects are masked from noNA (position 35):
## 
##     date, interval, steps
## The following objects are masked from noNA (position 36):
## 
##     date, interval, month, steps
## The following objects are masked from dataWithoutNA (position 39):
## 
##     date, interval, month, steps
## The following objects are masked from dataWithoutNA (position 40):
## 
##     date, interval, month, steps
## The following objects are masked from dataWithoutNA (position 41):
## 
##     date, interval, steps
## The following objects are masked from dataWithoutNA (position 42):
## 
##     date, interval, steps
## The following objects are masked from dataWithoutNA (position 43):
## 
##     date, interval, steps
## The following objects are masked from data (position 45):
## 
##     date, interval, steps
avgSteps <- aggregate(steps, list(interval = as.numeric(as.character(interval)), weekdays = weekdays), FUN = "mean")
names(avgSteps)[3] <- "meanOfSteps"
attach(avgSteps)
## The following objects are masked from newData (position 3):
## 
##     interval, weekdays
## The following object is masked from newData (position 4):
## 
##     interval
## The following object is masked from avgSteps (position 5):
## 
##     interval
## The following object is masked from noNA (position 6):
## 
##     interval
## The following object is masked from data (position 7):
## 
##     interval
## The following objects are masked from avgSteps (position 8):
## 
##     interval, meanOfSteps, weekdays
## The following objects are masked from newData (position 9):
## 
##     interval, weekdays
## The following object is masked from newData (position 10):
## 
##     interval
## The following objects are masked from avgSteps (position 11):
## 
##     interval, meanOfSteps, weekdays
## The following object is masked from noNA (position 12):
## 
##     interval
## The following object is masked from data (position 13):
## 
##     interval
## The following objects are masked from avgSteps (position 14):
## 
##     interval, meanOfSteps, weekdays
## The following objects are masked from newData (position 15):
## 
##     interval, weekdays
## The following object is masked from newData (position 16):
## 
##     interval
## The following objects are masked from avgSteps (position 17):
## 
##     interval, meanOfSteps, weekdays
## The following object is masked from noNA (position 18):
## 
##     interval
## The following object is masked from data (position 19):
## 
##     interval
## The following objects are masked from avgSteps (position 21):
## 
##     interval, meanOfSteps, weekdays
## The following objects are masked from newData (position 22):
## 
##     interval, weekdays
## The following object is masked from noNA (position 23):
## 
##     interval
## The following object is masked from noNA (position 24):
## 
##     interval
## The following object is masked from noNA (position 25):
## 
##     interval
## The following object is masked from newData (position 26):
## 
##     interval
## The following object is masked from noNA (position 27):
## 
##     interval
## The following object is masked from data (position 28):
## 
##     interval
## The following object is masked from avgSteps (position 29):
## 
##     interval
## The following object is masked from data (position 30):
## 
##     interval
## The following object is masked from data (position 31):
## 
##     interval
## The following object is masked from avgSteps (position 32):
## 
##     interval
## The following object is masked from data (position 33):
## 
##     interval
## The following object is masked from data (position 34):
## 
##     interval
## The following object is masked from noNA (position 36):
## 
##     interval
## The following object is masked from noNA (position 37):
## 
##     interval
## The following object is masked from dataWithoutNA (position 40):
## 
##     interval
## The following object is masked from dataWithoutNA (position 41):
## 
##     interval
## The following object is masked from dataWithoutNA (position 42):
## 
##     interval
## The following object is masked from dataWithoutNA (position 43):
## 
##     interval
## The following object is masked from dataWithoutNA (position 44):
## 
##     interval
## The following object is masked from data (position 46):
## 
##     interval
library(lattice)
xyplot(meanOfSteps ~ interval | weekdays, layout = c(1, 2), type = "l", xlab = "Interval", ylab = "Number of steps")
plot of chunk unnamed-chunk-15

