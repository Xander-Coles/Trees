"#Trees" 
See demo vide: https://youtu.be/Xv14g270618

Description: This package includes ipynb, html, excels (CSV), python and pictures to analyze and showcase tree health and socieconomic analysis. This includes Demographic_New_York_withborough_census_trackt.csv showcasing the socieconomic data; data_cleaning.ipynb to clean data in tree data set (to be dowlaoded by user) and socieconomic data; KNN_Poverty.ipynb to generate predictions for nearest neighbor model for socieconomic data (poverty by census tract); Decision_Tree_Health.ipynb to perform decision tree and random forest to perform analysis on tree health prediction; Decision_Tree_Socioeconomic.ipynb  generate predictions for decision tree for socieconomic data (poverty by census tract); Neural Network.ipynb to use Neural Network to predict tree health in New York; Interactive_Map_Google_API.html to showcase visualization of prediction and distribution of tree health and poverty; DataCleaningCountSpecies.py to clean formating for tree species analysis and further beckground for the tasks; Top5_Tree_Species_Bar_Graph.html to showcase visualization of tree species distribution.

Put precisely, there is a critical need for predictive modeling and geographical classification to address disparities in tree quality and distribution across New York City. Our goal is to estimate tree health outcomes using predictive models while leveraging socioeconomic and demographic data to identify and highlight inequities in tree maintenance and implementation. We feed those models into an interactive Choropleth Map, enabling users to explore the data by switching between models and fine-tuning hyperparameters, providing actionable insights for equitable intervention. This approach seeks to uncover and address the disproportionate adverse health impacts experienced by lower-income and minority communities due to insufficient urban greenery. By combining algorithmic insights with visual evidence, our solution aims to support targeted interventions and promote environmental equity in urban planning and tree maintenance efforts.


Installation:
"#Download NYC Tree Data"
1. Navigate to this link: https://data.cityofnewyork.us/Environment/2015-Street-Tree-Census-Tree-Data/uvpi-gqnh/about_data
2. Click Export in the upper right hand corner, and download as a csv

"#Download NYC ACS Census Tract Data"
1. 

"#Build Demographic_New_York_withborough_census_trackt.csv"
1. Open the NYC ACS Census Tract Data in Excel
2. Delete the first row
3. Save the file as "Demographic_New_York_withborough_census_trackt.csv"
    
"#Run Data Cleaning on NYC Tree Data and NYC ACS Census Tract Data"
1. After having downloaded the NYC Tree Data and NYC ACS Census Tract Data, navigate to the file named "Data_cleaning.ipynb"
2. Remember to change pd.read_csv('2015_Street_Tree_Census_-_Tree_Data_20241027.csv') because that might not be the name of your file (the name depends on when you download the original tree data set file
3. Run that file to output a "Trees_Quantified.csv" as well as a "Economic_census.csv"

"#Run KNN_Poverty.ipynb"
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

"#Run Neural Network.ipynb"
1. Obtain the "Demographic_New_York_withborough_census_trackt.csv" file and "DecisionTree_RandomForest_Health_Predictions.csv" file
2. Run the file named "Neural Network Health.ipynb" only until where it says so. There is also test code for optimizing variables that you don't need to run
3. The file will output a "DecisionTree_Neural_Health_Predictions.csv"

"#Display the Cloropleth Map"
1. Setup an HTTP server to run your D3 visualizations as discussed in the D3 lecture.
2. Create API Key for Google Maps: https://developers.google.com/maps/documentation/javascript/get-api-key.
3. Change the code where it "[ADD YOUR API KEY]".
4. Open the http://localhost:8000/Interactive_Map_Google_API.html
5. Feel free to explore and change the visualization variables and areas, use google maps api. You can also change the excel names to see predicted results from not the best methods (Decision Tree and Random Forest).

"#Supporting Bar Graph Top 4 Tree Species"
1. After having downloaded the NY Tree Data, run the file named "DataCleaningCountSpecies.py"
2. This will output a csv file named "species_counts.csv"
3. With this csv, run the file named "Top5_Tree_Species_Bar_Graph.html" to output the bar graph
Note: All other supporting graphs are done in Tableau using the NYC Tree Data and American Community Survey Data

Execution: The Cloropleth offers many interactive features that can be tried:
1 Selection of variable in toggle (tree health, predicted tree health, actual poverty percent, tree predicted poverty rate)
2 Selection of borough to be colored (All Boroughs, Queens, Bronx, Manhattan, Brooklyn or Staten Island) for better distribution for sub-municipality analysis.
3 tooltip showing mean of selected variable in census tract which has your mouse on it
4 histogram of distribution of variable in census tract which has your mouse on it (note that some census tract might have no trees surveyd or no one living there for census tract making no color and no distribution vaialable). For actual poverty rate this features will showcase just a text as each census tract has only one povert percent
5 Google Maps API mpas- this includes the ability of showing map, setelite map of locations 
6 Google Maps API street view - possibility of using street view.
7 Zoom tool. Zoom is performed when double clickin in map

For extra background on formation of data look for the supporting Top5_Tree_Species_Bar_Graph.html and images from tableau
