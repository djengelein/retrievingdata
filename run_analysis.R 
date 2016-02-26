## notes
## // indicates mac directory to run files
## Merges the training and the test sets to create one data set.
## Extracts only the measurements on the mean and standard deviation for ## each measurement.
## Uses descriptive activity names to name the activities in the data set
## Appropriately labels the data set with descriptive variable names.
## From the data set in step 4, creates a second, independent tidy data ## set with the average of each variable for each activity and each subject.o ## `TidyData.txt`.
## Return the cleaned data set.

run_analysis <- function() {		
    features <- read.table("features.txt")
    meanstd <- grep(".*(mean|std).*", features$V2) 
    setwd("~/data/UCI HAR Dataset")
    X_train <- read.table(".//train//X_train.txt")
    X_train <- X_train[meanstd]
    y_train <- read.table(".//train//y_train.txt")
    subject_train <- read.table(".//train//subject_train.txt")
    res <- cbind(subject_train, y_train, X_train)
    
    X_test <- read.table(".//test//X_test.txt")
    X_test <- X_test[meanstd]
    y_test <- read.table(".//test//y_test.txt")
    subject_test <- read.table(".//test//subject_test.txt")
    res <- rbind(res, cbind(subject_test, y_test, X_test))
    
    label <- read.table("activity_labels.txt")
    
    titles <- c("Subject","Activity")
    titles <- c(titles, as.character(features[meanstd,]$V2))
    names(res) <- titles
    for (i in 1:6) {
        res$Activity[res$Activity == i] <- as.character(label$V2[i])
    }
    
    molten = melt(res, id = c("Subject", "Activity"))
    meanData <- dcast(molten, formula = Subject + Activity ~ variable, mean)
    write.table(meanData, file = "TidyData.txt", sep="\t")
    return(meanData)
}