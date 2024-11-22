"#Trees" 

"#Download NYC Tree Data"
1. Navigate to this link: https://data.cityofnewyork.us/Environment/2015-Street-Tree-Census-Tree-Data/uvpi-gqnh/about_data
2. Click Export in the upper right hand corner, and download as a csv

"#Download NYC ACS Census Tract Data"
1. 

"#Build Demographic_New_York_withborough_census_trackt.csv"
1. Open the NYC ACS Census Tract Data in Excel
2. Delete the first row
3. Add a new column to the right of the column "Geographic Area Name" with the first row value being "Borough"
4. In the second row of the new "Borough" column, input this formula: "=IF(ISNUMBER(SEARCH("Bronx", B2)), "Bronx",
   IF(ISNUMBER(SEARCH("Queen", B2)), "Queen",
   IF(ISNUMBER(SEARCH("Kings", B2)), "Brooklyn",
   IF(ISNUMBER(SEARCH("New York County", B2)), "Manhattan",
   IF(ISNUMBER(SEARCH("Richmond", B2)), "Staten Island", "Other")))))"
5. Autofill the formula for the rest of the rows, and fill out the column
6. Save the file as "Demographic_New_York_withborough_census_trackt.csv"
    
"#Run Data Cleaning on NYC Tree Data and NYC ACS Census Tract Data"
1. After having downloaded the NYC Tree Data and NYC ACS Census Tract Data, navigate to the file named "Data_cleaning.ipynb"
2. Remember to change pd.read_csv('2015_Street_Tree_Census_-_Tree_Data_20241027.csv') because that might not be the name of your file (the name depends on when you download the original tree data set file
3. Run that file to output a "Trees_Quantified.csv" as well as a "Economic_census.csv"

"#Run KNN_Poverty"
1. Obtain both "Trees_Quantified.csv" as well as a "Economic_census.csv" in the steps listed above.
2. Run the file named "KNN_Poverty.ipynb" only until where it says so. There is also test code for optimizing variables that you don't need to run
3. The file will output a "Combined_Prediction.csv"

"#Run Decision_Tree_Health.ipynb"
1. Obtain the "Trees_Quantified.csv" file
2. Run the file named "Decision_Tree_Health.ipynb" only until where it says so. There is also test code for optimizing variables that you don't need to run.
3. The file will output a "DecisionTree_RandomForest_Health_Predictions.csv"

"#Run Decision_Tree_Socioeconomic.ipynb"
1. Obtain the "Demographic_New_York_withborough_census_trackt.csv" file and "DecisionTree_RandomForest_Health_Predictions.csv" file
2. Run the file named "Decision_Tree_Socioeconomic.ipynb" only until where it says so. There is also test code for optimizing variables that you don't need to run
3. The file will output a "DecisionTree_Socioeconomic_Predictions.csv"

"#Run Neural Network"
1. Obtain the "Demographic_New_York_withborough_census_trackt.csv" file and "DecisionTree_RandomForest_Health_Predictions.csv" file
2. Run the file named "Neural Network Health.ipynb" only until where it says so. There is also test code for optimizing variables that you don't need to run
3. The file will output a "DecisionTree_Neural_Health_Predictions.csv"

"#Display the Clorepth Map"
1. Setup an HTTP server to run your D3 visualizations as discussed in the D3 lecture.
2. Open the http://localhost:8000/Interactive_Map_Google_API.html
3. Feel free to explore and change the visualization variables and areas, use google maps api. You can also change the excel names to see predicted results from not the best methods (Decision Tree and Random Forest).

"#Supporting Bar Graph Top 4 Tree Species"
1. After having downloaded the NY Tree Data, run the file named "DataCleaningCountSpecies.py"
2. This will output a csv file named "species_counts.csv"
3. With this csv, run the file named "Top5_Tree_Species_Bar_Graph.html" to output the bar graph
Note: All other supporting graphs are done in Tableau using the NYC Tree Data and American Community Survey Data
