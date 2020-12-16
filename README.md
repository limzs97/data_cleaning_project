`CodeBook.md` describes the variables, data, and any transformations performed to clean up the data.

`run_analysis.R` performs the functions required:

* Read and assign datasets to data frames.
* Merge training and test sets to create one data set.
* Extract the mean and standard deviation for each measurement
* Use descriptive activity names to name the activities in the data set.
* Label the data set with descriptive variable names.
* Create a second, independent tidy data set with the average of each variable for each activity and each subject.

`TinyData2.txt` is the exported tidy data set from step 6 in `run_analysis.R`.