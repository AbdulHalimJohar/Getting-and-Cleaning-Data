Getting and Cleaning Data
=========================

This is a repository for any and all code written for the Getting and Cleaning Data Coursera course through Johns Hopkins University.

* Copy run_analysis.R into a folder in your local drive (ie: //Users//xxx//Getting and Cleaning Data/)

* Unzip the source (https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip) in the same folder as run_analysis.R script

* Change the name of the source folder to dataset

* In RStudio: setwd("C:\\\\Users\\\\xxx\\\\Getting and Cleaning Data\\\\"), followed by: source("run_analysis.R")

* Use data <- read.table("data_set_with_the_averages.txt") to read the data. It is 180x68 because there are 30 subjects and 6 activities, thus "for each activity and each subject" means 30 * 6 = 180 rows. Note that the provided R script has no assumptions on numbers of records, only on locations of files.
