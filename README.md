# Matplotlib_Challenge
Homework: The Power of Plots

## Animal Study / Drugs Test Analysis
The data provided for this analysis are present in two files. One containing the mice data and the other containing the drug regimens used for treatment. 

-   There are 249 mice in the list along with the gender, age, weight and the regimen used. 

-   There are 10 drug regimens used for comparison. The raw data contains the mouse ID, the timepoints when the tumor volume was measured, the tumor volume and Metastatic Sites.

## Script and Results
1.  The script developed for this analysis along with the results can be found in Matplotlib_Challenge/Pymaceuticals/pymaceuticals.ipynb

2.  The data provided for this analysis can be found in Matplotlib_Challenge/Pymaceuticals/Mouse_metadata.csv and Matplotlib_Challenge/Pymaceuticals/Study_results.csv

3.  The script in the Jupyter notebook does the following:
    -   Prepare the data:
        -   The data from the source files are read into the DataFrames mouse_metadata and study_results.
        -   The DataFrames above are merged into one dataset mouse_study_combined. This merged DataFrame is used for all calculations.
        -   The Mouse IDs with duplicate timepoints are identified and removed to create a new dataframe mouse_study_clean. This cleaned DataFrame is used for all calculations and analyses. 

    -   Generate Summary Statistics:
        -   The mean, median, variance, standard deviation, and SEM of the tumor volume for each drug regimen are calculated using the groupby method and stored in summary_statistics dataframe.
        -   The stats above are calculated using agg function and stored in summary_statistics_agg dataframe.

    -   Create bar charts and pie charts:
        -   Bar Charts:
            -   Two identical bar charts are generated one using the DataFrame.plot() method and the other using pyplot methods.   
            -   The bar charts show the total number of time points for all mice tested for each drug regimen throughout the study.
            -   The dataframe count_regimen_timepoints containing the drug regimens and the count of timepoints is created.
        -   Pie Charts:
            -   Two identical pie charts are generated one using the DataFrame.plot() method and the other using pyplot methods.
            -   These charts show the distribution of female versus male mice in the study.
            -   The dataframe distribution_sex containing the unique number of male and female mice counts is created for this.

    -   Calculate quartiles, find outliers, and create a box plot:
        -   Quartiles and Outliers:
            -   The dataframe mouse_last_timepoint is created to hold the last (greatest) timepoint for each mouse along with the tumor volume.
            -   The list tumor_volume is used to hold the Tumor Volume of the final timepoints for each of the 4 selected drugs Capomulin, Ramicane, Infubinol, and Ceftamin.
            -   This list is then used for the calculation of the Quartiles, IQR and Median.
            -   Then the lower and upper bounds are calculated which are in turn used for the outlier identification.
            -   The results are then printed on the console.
        -   Box Plot:
            -   The box plot is then plotted using the list tumor_volume created earlier.
            -   The shape and colour of the outlier in the plot is updated.

    -   Create a line plot and a scatter plot:
        -   Line Plot:
            -   The dataframe mouse_study_capomulin is created from the original cleaned dataframe to hold the data related to the drug regimen Capomulin.
            -   The dataframe capomulin_r554 is created from the dataframe above to hold the data related to the mouse ID r554 which was treated with Capomulin.
            -   A line graph is then plotted tumor volume vs. time point for the mouse ID r554.
        -   Scatter Plot:
            -   The dataframe capomulin_regimen is created from mouse_study_capomulin grouped by mouseID. 
            -   This dataframe holds the weight and average tumor volume of all the mice within the Capomulin regimen.
            -   A scatter plot is created for the tumor volume versus mouse weight for the Capomulin treatment regimen.

    -   Calculate correlation and regression:
        -   The Correlation coefficient for mouse weight and average tumor volume for the Capomulin regimen is calcuated using the scipy pearsonr method.
        -   This is then printed on the console.
        -   The line equation (y=mx+c) is generated using the scipy method lingress using Mouse weight and average tumor volume. 
        -   This line is then plotted on the scatter plot created above for the Capomulin treatment regimen.

    -   Final analysis:    
        -   The observations and inference made from the data and analysis above are updated at the top of the Jupyter notebook.

### Files Submitted
1.  Jupyter Notebook - Matplotlib_Challenge/Pymaceuticals/pymaceuticals.ipynb
2.  Source Data - Matplotlib_Challenge/Pymaceuticals/Mouse_metadata.csv and Matplotlib_Challenge/Pymaceuticals/Study_results.csv
