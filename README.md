# Neural Network Model 

**Overview:**
The aim of this model is to create a tool that assists Alaphabet Soup (or other future non-profits) in selecting applicants for funding with the best chance of success in the ventures. 

**Results**
To begin the model, we run the needed dependencies. In this case, we need the tensorflow. The first cell has the code to install tensorflow as a comment, if needed the user can run it to install. 

**_Data Preprocessing_**
1. Dropping unneccesary columns: The model begins by dropping the column "EIN" and "Name" as they are unnecessary.
2. Grouping low-representation categories:
    - Application_type: Using a threshold of 500 Categories with less than 500 instance are grouped together into the Other category.
    - Classification: Grouped together if there were less than 1,000 instances.
3. Converting to numeric format: Categorical features were converted to a numeric format using the pd.get_dummies()
4. StandardScaler implementation: the numerical features were standardized to help with performance.
5. Splitting Data: as the last step, the model set Features as X and target as Y.

**_Model Creation_**

The model has 3 layers:
1. Input Layer
2. Hidden Layers
3. Output Layer

The below photo summarizes the layers and shows the 80, 30 neurons in the Hidden Layers and 1 Neuron used in the output layer. 
<img width="791" alt="image" src="https://github.com/user-attachments/assets/45f13b32-b516-4d76-9e77-53952427c434" />

**_Training_**

We used the compile function with an "adam" as the optimizer to train the X,y variables. We focused on the metric "accuracy" to test the model after cycled through 100 epochs. 

**Results**
1. The target variable in the model is "IS_SUCCESSFUL" which are the possible funding options that were successfully completed.
2. All features are columns except for the aforemnetioned target variable.
3. The overall accuracy was 72.64% - this is below the goal accuracy of 75%. This is likely due to the unnecessary columns that are decreasing the overall accruacy. Further cleaning of the data to get rid of unnecassary fields and to eliminate outliers could help increase the overall accuracy.

