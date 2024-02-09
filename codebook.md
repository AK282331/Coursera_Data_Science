I have created a script run_analysis.R which get the data from UCI HAR Dataset and then merge test and train dataset and then make the tidy dataset. To achieve this i have followed 5 steps. This codebook will explain all the variables which i have created in the script.

## Dataset
Below is the link which is used to download the dataset on UCI HAR Dataset. This link is provided by Coursera
"https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip"
  
## Set Directory path

path = This is the variable to store the path to the directory from where i have uploaded the data and saved the final tidy data.

## Loading features,activities and train files on R
features = This variable is created to store the list of the features/variable with time and frequency domain variables from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ. This variable has 561 rows and 2 columns.

activities = This variable is created to store the list of the activies performed by the subjects for the study. This variable has 6 rows and 2 columns.

subject_train = This variable is created to store the data of the subjects from the train file who performed the activity. It consists of 21 subjects out of 30. This variable has 7352 rows and 1 column.

activity_train = This variable is created to store the data (codes) of the activities performed by the subjects who has assigned under the train data. This variable has 7352 rows and 1 column.

value_train = This variable is created to store the data of the actual measurements collected from activities done by subjects who has assigned under the test data. This variable has 7352 rows and 561 columns

## Loading test files on R
subject_test = This variable is created to store the data of the subjects from the test file who performed the activity. It consists of 9 subjects out of 30. This variable has 2947 rows and 1 column.

activity_test = This variable is created to store the data (codes) of the activities performed by the subjects who has assigned under the test data. This variable has 2947 rows and 1 column.

value_test = This variable is created to store the data of the actual measurements collected from activities done by subjects who has assigned under the test data. This variable has 2947 rows and 561 columns

## Merge Train and Test Data Frames
Train_Data = Merged subject_train,activity_train and value_train by cbind(subject_train,activity_train,value_train) and store in this variable. This variable has 7352 rows and 563 columns.

Test_Data = Merged subject_test,activity_test and value_test by cbind(subject_test,activity_test,value_test) and store in this variable. This variable has 2947 rows and 563 columns.

Merged_Data = This is the final merged file created by rbind(Train_Data,Test_Data). This variable has 10299 rows and 563 columns.

## Extracting features containing mean and standard deviation for each measurement

Merged_Data = Merged_Data contains 563 columns, selecting only those features which has mean and standard deviation for each measurement. After filtering this variable has 10299 rows and 88 columns.

## Assigning descriptive names to name the activities in the data set
Tidy_data = I have merged Merged_Data with activities variable to assign descriptive name to the activites.

## Labeling the data set with descriptive variable names
Assign descriptive column name to Tidy_data. Below are the changes i have done.
Replaced all "tbody" text to "TimeBody".
Replaced all "BodyBody" text to "Body".
Replaced all "Acc" text to"Accelerometer".
Replaced all text starts with "t" to "Time"
Replaced all Mag text to "Magnitude"
Replaced all Freq to Frequency
Replaced all text starts with "f" to "Frequency"
Replaced all angle text to "Angle"
Replaced all gravity text to Gravity"
Replaced all -std text to ".STD"
Replaced all -mean text to ".Mean"
Replaced all all //() to "..."
Replaced all "-" to ""

## Creating second, independent tidy data set with the average of each variable for each activity and each subject.
final_tidy_data = I have grouping the data on the basis of subjects and activities and then calculate the mean of all the variable. And store the final summarise data in this variable.

##Create a directory to store the output file.
Created a directory to store the final tidy data set.


## Saving the file
Save the tidy data set locally.



