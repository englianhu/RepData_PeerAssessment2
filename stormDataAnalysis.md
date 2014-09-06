---
output: pdf_document
---
# The fatal impact of tornadoes and economic effects of floods #
## Synopsis ##
This report downloads data from NOAA Storm Database and performs a statistical analysis on the impact of physical events to population health and economy.
Examining the event types, we observe that most of the physical phenomena cause injuries to people, which sometimes are fatal. By far, Tornadoes are the most dangerous events, caused ~100.000 injuries on the last 60 years.
When analysing the event types by the impact on the economy, we observe that floods caused $15 billions damages on the last 60 years, mostly on properties.
## Data Processing ##
<<<<<<< HEAD
### Load ###
How the data were loaded into R.
Data are downloaded and imported in stormdata data frame.

```r
fileUrl <- "https://d396qusza40orc.cloudfront.net/repdata%2Fdata%2FStormData.csv.bz2"
download.file(fileUrl, destfile = "tempdata.csv.bz2", method = "curl")
```

```
Warning: running command 'curl  "https://d396qusza40orc.cloudfront.net/repdata%2Fdata%2FStormData.csv.bz2"  -o "tempdata.csv.bz2"' had status 127
Warning: download had nonzero exit status
```

```r
stormdata <- read.csv("./tempdata.csv.bz2")
```

```
Warning: cannot open file './tempdata.csv.bz2': No such file or directory
```

```
Error: cannot open the connection
```
=======
Setup `knitr` options.

```r
library(knitr)
library(markdown)
# knitr configuration
opts_knit$set(progress = FALSE)
opts_chunk$set(echo = TRUE, message = FALSE, tidy = TRUE, comment = NA, fig.path = "figure/", 
    fig.keep = "high", fig.width = 10, fig.height = 6, fig.align = "center")
```

### Load ###
How the data were loaded into R.
Data are downloaded and imported in stormdata data frame.
```r
fileUrl <- "https://d396qusza40orc.cloudfront.net/repdata%2Fdata%2FStormData.csv.bz2"
download.file(fileUrl, destfile = "tempdata.csv.bz2", method = "curl")
stormdata <- read.csv("./tempdata.csv.bz2")
```
>>>>>>> origin/master
### Process ###
How the data are processed for analysis.
To calculate the injuries to humans, `damages` dataframe is being used, to aggregate both fatal and non-fatal injuries.
The economic impact is assessed by calculating the exponential value of the property and corp damage in data frame `economic`.
Two small data frames `dam` and `eco` are used to calculate only the top 10 events in human and economic impact respectively.
<<<<<<< HEAD






