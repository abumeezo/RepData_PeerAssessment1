#Reproducible Research Programming Project 1
by Zeid M. Rusan  
&nbsp;

###Just in case, to be explicit, we set echo = TRUE globally

```r
knitr::opts_chunk$set(echo = TRUE)
```
&nbsp;

###Loading and preprocessing the data
First, we read in the data, check it out with str, and format the dates with as.Date.

```r
activity_data <- read.csv("activity.csv")
```

```
## Warning in file(file, "rt"): cannot open file 'activity.csv': No such file
## or directory
```

```
## Error in file(file, "rt"): cannot open the connection
```

```r
str(activity_data)
```

```
## Error in str(activity_data): object 'activity_data' not found
```

```r
activity_data$date <- as.Date(activity_data$date)
```

```
## Error in as.Date(activity_data$date): object 'activity_data' not found
```
&nbsp;

###What is the mean total number of steps taken per day?
Will use aggregate to sum step over each day (in list).  
Then, we will plot these data across time with a histogram.  
Finally, we will report the mean and median of the step sums per days across all days.

```r
sumOfsteps <- aggregate(activity_data$steps, by=list(activity_data$date), FUN=sum)
```

```
## Error in aggregate(activity_data$steps, by = list(activity_data$date), : object 'activity_data' not found
```

```r
hist(sumOfsteps$x,col = "green",xlab = "Total steps per day",ylab = "Number of days",breaks = 8,main = "Number of steps for two months")
```

```
## Error in hist(sumOfsteps$x, col = "green", xlab = "Total steps per day", : object 'sumOfsteps' not found
```

```r
meanOfStep <- mean(sumOfsteps$x,na.rm = T)
```

```
## Error in mean(sumOfsteps$x, na.rm = T): object 'sumOfsteps' not found
```

```r
medianOfStep <- median(sumOfsteps$x,na.rm = T)
```

```
## Error in median(sumOfsteps$x, na.rm = T): object 'sumOfsteps' not found
```









