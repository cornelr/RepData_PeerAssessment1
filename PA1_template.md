# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data


```r
filename <- "activity.zip"
unzip(filename)
filedata <- read.csv("activity.csv", na.strings = c("NA"))
```


## What is mean total number of steps taken per day?

```r
list1 <- split(filedata$steps, filedata$date)
totalsteps <- as.numeric(sapply(list1, sum))
hist(totalsteps, col = "red", main = "Total number of steps taken each day", 
    xlab = "Steps per day")
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2.png) 

```r

stepsAgg <- aggregate(filedata$steps, list(filedata$date), sum)
stepsMean = mean(stepsAgg[, 2], na.rm = TRUE)
stepsMedian = median(stepsAgg[, 2], na.rm = TRUE)

stepsMean
```

```
## [1] 10766
```

```r
stepsMedian
```

```
## [1] 10765
```


## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
