Course Project Code Book
========================

Original data is downloaded from https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

Original data description is explained in the file from the URL http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

run_analysis.R script performs the following:

Task 1: Merges the training and the test sets to create one data set.
* Merges the training and test sets to create one data set, namely dataset/train/X_train.txt with dataset/test/X_test.txt, dataset/train/subject_train.txt with dataset/test/subject_test.txt, and dataset/train/y_train.txt with dataset/test/y_test.txt.

Task 2: Extracts only the measurements on the mean and standard deviation for each measurement. 
* Reads features.txt and extracts only the measurements on the mean and standard deviation for each measurement. The result is a 10299x66 data frame, because only 66 out of 561 attributes are measurements on the mean and standard deviation. All measurements appear to be floating point numbers in the range (-1, 1).

Task 3: Uses descriptive activity names to name the activities in the data set
* Reads activity_labels.txt and applies descriptive activity names to name the activities in the data set:

        walking
        
        walkingupstairs
        
        walkingdownstairs
        
        sitting
        
        standing
        
        laying

Task 4: Appropriately labels the data set with descriptive variable names. 
* The script also appropriately labels the data set with descriptive names: all feature names (attributes) and activity names are converted to lower case, underscores and brackets () are removed. Then it merges the 10299x66 data frame containing features with 10299x1 data frames containing activity labels and subject IDs. The result is saved as merged_clean_data.txt, a 10299x68 data frame such that the first column contains subject IDs, the second column activity names, and the last 66 columns are measurements. Subject IDs are integers between 1 and 30 inclusive. The names of the attributes are similar to the following:

        tbodyacc-mean-x 
        
        tbodyacc-mean-y 
        
        tbodyacc-mean-z 
        
        tbodyacc-std-x 
        
        tbodyacc-std-y 
        
        tbodyacc-std-z 
        
        tgravityacc-mean-x 
        
        tgravityacc-mean-y

Task 5: From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.
* Finally, the script creates a 2nd, independent tidy data set with the average of each measurement for each activity and each subject. The result is saved as data_set_with_the_averages.txt, a 180x68 data frame, where as before, the first column contains subject IDs, the second column contains activity names (see below), and then the averages for each of the 66 attributes are in columns 3...68. There are 30 subjects and 6 activities, thus 180 rows in this data set with averages.
