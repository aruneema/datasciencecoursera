
Getting and Cleaning Data Course Project
===================

This file describes how run_analysis.R script works.

First, unzip the data from https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 

Make sure the unzipped folder "UCI HAR Dataset" and the run_analysis.R script are both in the current working directory.
Second, use source("run_analysis.R") command in RStudio.

Third, you will find two output files are generated in the current working directory:
merged_data.txt (7.9 Mb): it contains a data frame called cleanedData with 10299*68 dimension.
data_with_means.txt (220 Kb): it is the independent tidy data set with the average of each variable for each activity and each subject. 
