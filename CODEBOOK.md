Introduction
============

This code book summarizes the data in the tidy.txt dataset submitted for this project. The script used to generate the tidy dataset is documented separately in the README.md file, which provides a detailed explanation of how the original data was transformed into the tidy.txt dataset.

The original data used for this project was based on data recorded by a smartphone accelerometer and gyroscope. The phones were worn on the waists of 30 subjects laying, sitting, standing, walking, walking upstairs and walking downstairs [Anguita et al, 2013, 2012].

The primary measurements were triaxial linear acceleration from the accelerometer and triaxial angular velocity from the gyroscope [Anguita et al, 2013, 2012]. According to documentation with the original data (features\_info.txt), "The body linear acceleration and angular velocity were derived in time to obtain Jerk signals (tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ). Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag)."

There were two pairs of duplicate columns in the original data, although the columns had different names. The correct names in these instances could not be determined, so both pairs of duplicated columns remain in the data. This issue was documented in the code and the README.md document. The original names of the duplicated columns were:

1.  tBodyAccMag-mean() = tGravityAccMag-mean()
2.  tBodyAccMag-Std() = tGravityAccMag-Std()

In the tidy.txt file, the affected columns are:

1.  Mean.tBodyAccMag.mean = Mean.tGravityAccMag.mean (columns 32 and 34, respectively)
2.  Mean.tBodyAccMag.std = Mean.tGravityAccMag.std (columns 33 and 35, respectively)

Signals were collected at a rate of 50 Hz and recorded for several seconds. Signals were summarized for fixed time periods by mean, standard deviation and other statistical measures for the 30 subjects studied. Temporal measurements were preceded by a "t" in the variable names. A graph of these variables with acceleration on the y-axis and time on the x-axis would plot 50 measurements per second (50 Hz). These measurements cycle between high and low values and would look like waves. Fast Fourier Transform (FFT) was applied to the data, which measures the frequencies of forces as they fluctuate over time. FFT variables were preceded by an "f" in variable names. FFT output units are volts.

Variable Names
--------------

The signals were separated into body and gravitational components, indicated in variables names as "Body" or "Gravity." Accelerometer measurements, measured as m/s<sup>2</sup>, were indicated by "ACC.". Gyroscope measurements, measured in m/s<sup>3</sup> units, were indicated by "Gyro" in variable names.

Summarizing Variable Naming Nomenclature
----------------------------------------

-   t: indicates temporal data
-   f: indicates Fast Fourier Transform data
-   Accelerometer: ACC
-   Gyroscope: Gyro
-   Body signals: Body
-   Gravity signals: Gravity
-   Jerk measurements: Jerk
-   Magnitude of signals: Mag (The issue of duplicate Mag columns has been noted)
-   Mean: mean
-   Standard deviation: std
-   Axis: X, Y or Z

The tidy.txt dataset comprised 66 statistical variables and 1 categorical variable, called meanGroup. The statistical data consisted of mean values subsetted for 30 subjects (subject01 through subject30) and six activities (laying, sitting, standing, walking, walking upstairs and walking downstairs). Thus, there were 67 columns and 36 rows of data, plus the column headers.

Tidy.txt numeric data consisted solely of the means of the variables listed, even for "std" variables. These means were calculated for the groups identified in the groupMean column of the data (column 1). The column names were preceded by "Mean." to indicate that the column values were mean values of the original data, as subsetted by meanGroup.

Variables in the following table with an XYZ suffix indicate separate X-, Y- and Z-axis measurements (as indicated by 3 columns).

Data Summary for tidy.txt Dataset
---------------------------------

### All data presented are means by meanGroup

    ##                       Variable Columns         Type  Units
    ## 1                    meanGroup       1  Categorical     NA
    ## 2       Mean.tBodyAcc.mean.XYZ     2-4   Continuous  m/s^2
    ## 3        Mean.tBodyAcc.std.XYZ     5-7   Continuous  m/s^2
    ## 4    Mean.tGravityAcc.mean.XYZ    8-10   Continuous  m/s^2
    ## 5     Mean.tGravityAcc.std.XYZ   11-13   Continuous  m/s^2
    ## 6   Mean.tBodyAccJerk.mean.XYZ   14-16   Continuous  m/s^2
    ## 7    Mean.tBodyAccJerk.std.XYZ   17-19   Continuous  m/s^2
    ## 8      Mean.tBodyGyro.mean.XYZ   20-22   Continuous  m/s^3
    ## 9       Mean.tBodyGyro.std.XYZ   23-25   Continuous  m/s^3
    ## 10 Mean.tBodyGyroJerk.mean.XYZ   26-28   Continuous  m/s^3
    ## 11  Mean.tBodyGyroJerk.std.XYZ   29-31   Continuous  m/s^3
    ## 12       Mean.tBodyAccMag.mean      32   Continuous  m/s^2
    ## 13        Mean.tBodyAccMag.std      33   Continuous  m/s^2
    ## 14    Mean.tGravityAccMag.mean      34   Continuous  m/s^2
    ## 15     Mean.tGravityAccMag.std      35   Continuous  m/s^2
    ## 16   Mean.tBodyAccJerkMag.mean      36   Continuous  m/s^2
    ## 17    Mean.tBodyAccJerkMag.std      37   Continuous  m/s^2
    ## 18      Mean.tBodyGyroMag.mean      38   Continuous  m/s^3
    ## 19       Mean.tBodyGyroMag.std      39   Continuous  m/s^3
    ## 20  Mean.tBodyGyroJerkMag.mean      40   Continuous  m/s^3
    ## 21   Mean.tBodyGyroJerkMag.std      41   Continuous  m/s^3
    ## 22      Mean.fBodyAcc.mean.XYZ   42-44   Continuous      V
    ## 23       Mean.fBodyAcc.std.XYZ   45-47   Continuous      V
    ## 24  Mean.fBodyAccJerk.mean.XYZ   48-50   Continuous      V
    ## 25   Mean.fBodyAccJerk.std.XYZ   51-53   Continuous      V
    ## 26     Mean.fBodyGyro.mean.XYZ   54-56   Continuous      V
    ## 27      Mean.fBodyGyro.std.XYZ   57-59   Continuous      V
    ## 28       Mean.fBodyAccMag.mean      60   Continuous      V
    ## 29        Mean.fBodyAccMag.std      61   Continuous      V
    ## 30   Mean.fBodyAccJerkMag.mean      62   Continuous      V
    ## 31    Mean.fBodyAccJerkMag.std      63   Continuous      V
    ## 32      Mean.fBodyGyroMag.mean      64   Continuous      V
    ## 33       Mean.fBodyGyroMag.std      65   Continuous      V
    ## 34  Mean.fBodyGyroJerkMag.mean      66   Continuous      V
    ## 35   Mean.fBodyGyroJerkMag.std      67   Continuous      V

References:
-----------

The original data was obtained from: <http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones> Source: \# Jorge L. Reyes-Ortiz(1,2), Davide Anguita(1), Alessandro Ghio(1), Luca Oneto(1) and Xavier Parra(2) 1 - Smartlab - Non-Linear Complex Systems Laboratory DITEN - Università degli Studi di Genova, Genoa (I-16145), Italy. 2 - CETpD - Technical Research Centre for Dependency Care and Autonomous Living Universitat Politècnica de Catalunya (BarcelonaTech). Vilanova i la Geltrú (08800), Spain activityrecognition '@' smartlab.ws

Citation: Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra and Jorge L. Reyes-Ortiz. A Public Domain Dataset for Human Activity Recognition Using Smartphones. 21th European Symposium on Artificial Neural Networks, Computational Intelligence and Machine Learning, ESANN 2013. Bruges, Belgium 24-26 April 2013.