# EMG_Classification
EMG feature analysis and extraction of rock paper scissors game

## Purpose
Use machine learning to determine if someone threw a rock, paper, or scissors from collected EMG data.

## File Structure
- [Juniper Sun](https://github.com/sam-coleman/EMG_Classification/tree/main/JuniperSun) contains the raw EMG data. JuniperSun has 10 different collection structs, each with 18 trials (180 trials in total). Labels (rock, paper, or scissors) are stored in field "epochlabelscat."  The data is stored in “data” field in a [3x1500X18] matrix where it is [channel X value X trial]. The times are stored in the “alltimes” field which is [1500 X 18] where it is [timeStep X trial].
- [Data](https://github.com/sam-coleman/EMG_Classification/tree/main/data) contains exported mat files. These include test and train data with pre-processing, all extracted features for both test and train, and 3 trained classifiers. 
- [prelim.mlx](https://github.com/sam-coleman/EMG_Classification/blob/main/prelim.mlx) includes preliminary understanding and visualization of data.
- [dataSetUp.mlx](https://github.com/sam-coleman/EMG_Classification/blob/main/dataSetUp.mlx) runs pre-processing and splits the data up into testing and training.
- [extract_features.m](https://github.com/sam-coleman/EMG_Classification/blob/main/extract_features.m) is a class holding all functions to extract features from the data. The features we extract are: mean, maximum value in signal, mean of absolute value in signal, root mean square (rms), variance, average amplitude change (aac), waveform length (lc), willison amplitude (wamp), zero crossing (zc), integrated EMG (iemg), simple squared integral (ssi), number of peaks (np), skewness (skew), difference absolute standard deviation value (dasdv), kurtosis (kurt), difference absolute mean value (damv), and log detector (ld).
- [extractFeatures.mlx](https://github.com/sam-coleman/EMG_Classification/blob/main/extractFeatures.mlx) extracts all features from either test or train data and saves them to a mat file for future use.
- [Documentation of Feature Selection](https://docs.google.com/spreadsheets/d/19WO7bkwY86gnjzJEToPZt_6A1pq4m1qWPwOc_FzCt88/edit?usp=sharing) is a spreadsheet holding the results of different features and algorithms.
- [finalModels.mlx](https://github.com/sam-coleman/EMG_Classification/blob/main/finalModels.mlx) trains (and saves) the top three classifiers.
- [Test.mlx](https://github.com/sam-coleman/EMG_Classification/blob/main/test.mlx) runs our algorithms on the test data.

## Results
[Final Results executive summary report](https://github.com/sam-coleman/EMG_Classification/blob/main/Writeup.pdf).
Our best classifier used an SVM algorithm with Average Amplitude Change (AAC) and Absolute Value of the Mean (abs_mean) across channels 1 and 2 as the features. Our validation classification accuracy is 86.11% on our test data and the confusion matrix is below.

[Confusion Matrix](/figures/list1ConfusionPerc.jpg)

## Authors
[Sam Coleman](https://github.com/sam-coleman) and [Rishita Sarin](https://github.com/rishitasarin)
