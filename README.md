DataCleaning
============
### Introduction

This function completes the following tasks:

1. Merge the training set and the test set into one.
2. Clean the data set by subsetting it with the features described in `CodeBook.md`.
   and computing the mean by `melt` and `dcast`.
3. Writes the cleaned data set into `TidyData.txt`.
4. Return the cleaned data set.

###Execution

The way to execute this function is as follows:

1. Set your working directory to the directory that contains the raw data sets
2. Just run `run_analysis()` .


Data Set Information:
http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed 6 activities (walking, walking_upstairs, walking_downstairs, sitting, standing, laying) whilst wearing a smartphone device (Samsung Galaxy S2) on the waist. 

Attribute Information:

For each record in the dataset it is provided: 
- Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration. 
- Triaxial Angular velocity from the gyroscope. 
- A 561-feature vector with time and frequency domain variables. 
- Its activity label. 
- An identifier of the subject who carried out the experiment.
