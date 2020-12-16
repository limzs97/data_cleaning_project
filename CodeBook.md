`run_analysis.R` performs the following functions:

**1. Read and assign datasets to data frames.**

* `features` <- `features.txt`: 561 rows, 2 columns
* `activity_labels` <- `activity_labels.txt`: 6 rows, 2 columns
* `subject_test` <- `test/subject_test.txt`: 2947 rows, 1 column
* `x_test` <- `test/X_test.txt`: 2947 rows, 561 columns
* `y_test` <- `test/y_test.txt`: 2947 rows, 1 columns
* `subject_train` <- `test/subject_train.txt`: 7352 rows, 1 column
* `x_train` <- `test/X_train.txt`: 7352 rows, 561 columns
* `y_train` <- `test/y_train.txt`: 7352 rows, 1 columns

**2. Merge training and test sets to create one data set.**

* `train_test_merged` (10299 rows, 563 column) is created by applying the `cbind()` function to three data frames that are respectively created by applying the `rbind()` function to `subject_train` and `subject_test`, `y_train` and `y_test`, and `x_train` and `x_test`.

**3. Extract the mean and standard deviation for each measurement.**

* `TidyData` (10299 rows, 88 columns) is created by selecting from `train_test_merged` the columns subject, code and the mean and standard deviation for each measurement.

**4. Use descriptive activity names to name the activities in the data set.**

* Replaces code column of `TidyData` with corresponding activity taken from `activity_labels` variable.

**5. Label the data set with descriptive variable names.**

* Short-form names in the columns of `TidyData` are replaced by long-form names.

**6. Create a second, independent tidy data set with the average of each variable for each activity and each subject.**

* `TidyData2` (180 rows, 88 columns) is created by summarising `TidyData` after grouping it by subject and activity, before it is written into `TidyData2.txt`.