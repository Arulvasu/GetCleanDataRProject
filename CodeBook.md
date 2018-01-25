# *Cleaning and Getting Data* course project code book

### Analysis process

The analysis script, `run_analysis.R` reads in the processed experiment data and performs a number of steps to get it into summary form.

 - Both the processed test and training datasets are read in and merged into one data frame.
 - The data columns are then given names based on the `features.txt` file.
 - Columns that hold mean or standard deviation measurements are selected from the dataset, while the other measurement columns are excluded from the rest of the analysis.
 - The activity identifiers are replaced with the activity labels based on the `activity_labels.txt` file.
 - Invalid characters (`()` and `-` in this case) are removed from the column names. Also, duplicate phrase `BodyBody` in some columns names is replaced with `Body`.
 - The data is then grouped by subject and activity, and the mean is calculated for every measurement column.
 - Finally, the summary dataset is written to a file, `tidyData.txt`.

Each line in `run_analysis.R` is commented. Reference the file for more information on this process.

### Columns in output file

The columns included in the output file are listed below:

  - subject_id - The id of the experiment participant.
  - activity_labels - The name of the activity that the measurements correspond to, like `LAYING` or `WALKING`.

All of the following fields represent the mean of recorded data points for the given subject and activity. The detailed description of the different measurement types can be found in the `features_info.txt` file included in the data [zip file](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip).

                         _ time_BodyAcceleration_mean_Xaxis    40   numeric  min: 0.266  max: 0.28
                      _ time_BodyAcceleration_mean_Yaxis    40   numeric  min: -0.021  max: -0.013
                        _ time_BodyAcceleration_mean_Zaxis    40   numeric  min: -0.118  max: -0.1
         _ time_BodyAcceleration_standardDeviation_Xaxis    40   numeric  min: -0.992  max: -0.127
          _ time_BodyAcceleration_standardDeviation_Yaxis    40   numeric  min: -0.972  max: 0.121
         _ time_BodyAcceleration_standardDeviation_Zaxis    40   numeric  min: -0.976  max: -0.083
                     _ time_GravityAcceleration_mean_Xaxis    40   numeric  min: 0.475  max: 0.963
                    _ time_GravityAcceleration_mean_Yaxis    40   numeric  min: -0.18  max: 0.281
                   _ time_GravityAcceleration_mean_Zaxis    40   numeric  min: -0.285  max: 0.239
     _ time_GravityAcceleration_standardDeviation_Xaxis    40   numeric  min: -0.996  max: -0.934
     _ time_GravityAcceleration_standardDeviation_Yaxis    40   numeric  min: -0.982  max: -0.901
     _ time_GravityAcceleration_standardDeviation_Zaxis    40   numeric  min: -0.974  max: -0.881
                   _ time_BodyAccelerationJerk_mean_Xaxis    40   numeric  min: 0.057  max: 0.087
                   _ time_BodyAccelerationJerk_mean_Yaxis    40   numeric  min: -0.003  max: 0.02
                   _ time_BodyAccelerationJerk_mean_Zaxis    40   numeric  min: -0.02  max: 0.016
    _ time_BodyAccelerationJerk_standardDeviation_Xaxis    40   numeric  min: -0.994  max: -0.172
     _ time_BodyAccelerationJerk_standardDeviation_Yaxis    40   numeric  min: -0.987  max: 0.004
    _ time_BodyAccelerationJerk_standardDeviation_Zaxis    40   numeric  min: -0.991  max: -0.387
                               _ time_BodyGyro_mean_Xaxis    40   numeric  min: -0.07  max: 0.008
                             _ time_BodyGyro_mean_Yaxis    40   numeric  min: -0.101  max: -0.042
                               _ time_BodyGyro_mean_Zaxis    40   numeric  min: 0.048  max: 0.116
                _ time_BodyGyro_standardDeviation_Xaxis    40   numeric  min: -0.988  max: -0.353
                _ time_BodyGyro_standardDeviation_Yaxis    40   numeric  min: -0.986  max: -0.217
                _ time_BodyGyro_standardDeviation_Zaxis    40   numeric  min: -0.986  max: -0.169
                         _ time_BodyGyroJerk_mean_Xaxis    40   numeric  min: -0.114  max: -0.059
                          _ time_BodyGyroJerk_mean_Yaxis    40   numeric  min: -0.05  max: -0.037
                         _ time_BodyGyroJerk_mean_Zaxis    40   numeric  min: -0.064  max: -0.042
            _ time_BodyGyroJerk_standardDeviation_Xaxis    40   numeric  min: -0.993  max: -0.034
              _ time_BodyGyroJerk_standardDeviation_Yaxis    40   numeric  min: -0.993  max: -0.3
            _ time_BodyGyroJerk_standardDeviation_Zaxis    40   numeric  min: -0.994  max: -0.051
                   _ time_BodyAccelerationMagnitude_mean    40   numeric  min: -0.98  max: -0.055
     _ time_BodyAccelerationMagnitude_standardDeviation    40   numeric  min: -0.975  max: -0.105
                _ time_GravityAccelerationMagnitude_mean    40   numeric  min: -0.98  max: -0.055
  _ time_GravityAccelerationMagnitude_standardDeviation    40   numeric  min: -0.975  max: -0.105
              _ time_BodyAccelerationJerkMagnitude_mean    40   numeric  min: -0.992  max: -0.154
 _ time_BodyAccelerationJerkMagnitude_standardDeviation    40   numeric  min: -0.991  max: -0.088
                          _ time_BodyGyroMagnitude_mean    40   numeric  min: -0.979  max: -0.176
              _ time_BodyGyroMagnitude_standardDeviation    40   numeric  min: -0.98  max: -0.201
                      _ time_BodyGyroJerkMagnitude_mean    40   numeric  min: -0.995  max: -0.203
         _ time_BodyGyroJerkMagnitude_standardDeviation    40   numeric  min: -0.994  max: -0.237
                    _ force_BodyAcceleration_mean_Xaxis    40   numeric  min: -0.992  max: -0.134
                     _ force_BodyAcceleration_mean_Yaxis    40   numeric  min: -0.975  max: 0.102
                    _ force_BodyAcceleration_mean_Zaxis    40   numeric  min: -0.983  max: -0.273
       _ force_BodyAcceleration_standardDeviation_Xaxis    40   numeric  min: -0.992  max: -0.127
        _ force_BodyAcceleration_standardDeviation_Yaxis    40   numeric  min: -0.972  max: 0.059
        _ force_BodyAcceleration_standardDeviation_Zaxis    40   numeric  min: -0.974  max: -0.06
            _ force_BodyAcceleration_meanFrequency_Xaxis    40   numeric  min: -0.349  max: 0.008
            _ force_BodyAcceleration_meanFrequency_Yaxis    40   numeric  min: -0.165  max: 0.136
            _ force_BodyAcceleration_meanFrequency_Zaxis    40   numeric  min: -0.141  max: 0.284
                _ force_BodyAccelerationJerk_mean_Xaxis    40   numeric  min: -0.994  max: -0.209
                _ force_BodyAccelerationJerk_mean_Yaxis    40   numeric  min: -0.987  max: -0.087
                _ force_BodyAccelerationJerk_mean_Zaxis    40   numeric  min: -0.989  max: -0.353
   _ force_BodyAccelerationJerk_standardDeviation_Xaxis    40   numeric  min: -0.994  max: -0.207
    _ force_BodyAccelerationJerk_standardDeviation_Yaxis    40   numeric  min: -0.989  max: 0.035
    _ force_BodyAccelerationJerk_standardDeviation_Zaxis    40   numeric  min: -0.991  max: -0.42
        _ force_BodyAccelerationJerk_meanFrequency_Xaxis    40   numeric  min: -0.271  max: 0.258
          _ force_BodyAccelerationJerk_meanFrequency_Yaxis    40   numeric  min: -0.4  max: 0.088
        _ force_BodyAccelerationJerk_meanFrequency_Zaxis    40   numeric  min: -0.305  max: 0.136
                            _ force_BodyGyro_mean_Xaxis    40   numeric  min: -0.986  max: -0.079
                            _ force_BodyGyro_mean_Yaxis    40   numeric  min: -0.987  max: -0.249
                            _ force_BodyGyro_mean_Zaxis    40   numeric  min: -0.986  max: -0.082
               _ force_BodyGyro_standardDeviation_Xaxis    40   numeric  min: -0.988  max: -0.445
               _ force_BodyGyro_standardDeviation_Yaxis    40   numeric  min: -0.985  max: -0.151
               _ force_BodyGyro_standardDeviation_Zaxis    40   numeric  min: -0.987  max: -0.226
                    _ force_BodyGyro_meanFrequency_Xaxis    40   numeric  min: -0.307  max: 0.123
                    _ force_BodyGyro_meanFrequency_Yaxis    40   numeric  min: -0.403  max: 0.085
                    _ force_BodyGyro_meanFrequency_Zaxis    40   numeric  min: -0.266  max: 0.266
                 _ force_BodyAccelerationMagnitude_mean    40   numeric  min: -0.981  max: -0.056
    _ force_BodyAccelerationMagnitude_standardDeviation    40   numeric  min: -0.975  max: -0.274
         _ force_BodyAccelerationMagnitude_meanFrequency    40   numeric  min: -0.068  max: 0.258
             _ force_BodyAccelerationJerkMagnitude_mean    40   numeric  min: -0.991  max: -0.076
 _ force_BodyAccelerationJerkMagnitude_standardDeviation    40   numeric  min: -0.991  max: -0.11
     _ force_BodyAccelerationJerkMagnitude_meanFrequency    40   numeric  min: -0.024  max: 0.403
                         _ force_BodyGyroMagnitude_mean    40   numeric  min: -0.986  max: -0.156
             _ force_BodyGyroMagnitude_standardDeviation    40   numeric  min: -0.98  max: -0.377
                 _ force_BodyGyroMagnitude_meanFrequency    40   numeric  min: -0.315  max: 0.286
                     _ force_BodyGyroJerkMagnitude_mean    40   numeric  min: -0.994  max: -0.253
        _ force_BodyGyroJerkMagnitude_standardDeviation    40   numeric  min: -0.994  max: -0.271
             _ force_BodyGyroJerkMagnitude_meanFrequency    40   numeric  min: -0.008  max: 0.332 
completeProcessedCast
### More information

Detailed information on the experiment and the data can be found in the `README.txt` and `features_info.txt` files included in the experiment data [zip file](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip) or find more information on the dataset [homepage](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones).
