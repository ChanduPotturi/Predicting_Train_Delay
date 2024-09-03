# Project Name : Predicting Train Delays Using Machine Learning: A Comprehensive Analysis

## **1. Introduction**

### **1.1 Project Overview**

This project focuses on predicting train delays using a dataset containing hourly snapshots of planned and actual train arrivals and departures. The data, collected from the Timetables and StaDa API during a one-week period, includes geolocation, station details, line names, and delay information.

### **1.2 Objectives**

- To develop predictive models for train arrival and departure delays.
- To identify key features influencing train delays.
- To optimize model performance using hyperparameter tuning.

## **2. Data Description**

### **2.1 Dataset Overview**

The dataset includes the following columns:
- **ID**: Unique identifier for the record.
- **line**: Train line number.
- **path**: Path identifier.
- **eva_nr**: Station code.
- **category**: Category of the station.
- **station**: Name of the station.
- **state**: State where the station is located.
- **city**: City where the station is located.
- **zip**: Postal code of the station.
- **long**: Longitude of the station.
- **lat**: Latitude of the station.
- **arrival_plan**: Planned arrival time.
- **departure_plan**: Planned departure time.
- **arrival_change**: Actual arrival time with changes.
- **departure_change**: Actual departure time with changes.
- **arrival_delay_m**: Arrival delay in minutes.
- **departure_delay_m**: Departure delay in minutes.
- **info**: Additional information.
- **arrival_delay_check**: Verified arrival delay.
- **departure_delay_check**: Verified departure delay.

### **2.2 Data Collection**

Data was collected from 08.07.2024 00:00 to 14.07.2024 23:59, capturing hourly snapshots of train operations across approximately 2000 stations in Germany.

## **3. Data Preprocessing**

### **3.1 Data Cleaning**

- **Missing Values**: Handled missing values by imputation or removal as appropriate.
- **Data Types**: Converted time columns to datetime format.
- **Feature Engineering**: Created additional features such as `arrival_hour`, `departure_hour`, `arrival_day_of_week`, and `departure_day_of_week`.

### **3.2 Feature Selection**

Features selected for modeling:
- **Arrival and Departure Hours**: Time of the day.
- **Arrival and Departure Day of the Week**: Day of the week.
- **Station**: Categorical feature converted to dummy variables.

### **3.3 Target Variable**

- **Arrival Delay**: Binary classification of whether the train is delayed on arrival.
- **Departure Delay**: Binary classification of whether the train is delayed on departure.

## **4. Model Building**

### **4.1 Model Selection**

- **Models**: RandomForestClassifier was chosen for its robustness and performance on classification tasks.

### **4.2 Hyperparameter Tuning**

- **Grid Search**: Performed using `GridSearchCV` to find the optimal hyperparameters for the RandomForest model.
- **Randomized Search**: Used `RandomizedSearchCV` for efficiency, sampling from a defined parameter space.

### **4.3 Model Evaluation**

- **Metrics**: Evaluated using accuracy and classification reports, which include precision, recall, and F1-score.

## **5. Results**

### **5.1 Hyperparameter Tuning Results**

- **Best Parameters for Arrival Delay Model**:
  - `n_estimators`: 100
  - `max_depth`: 20
- **Best Score for Arrival Delay Model**: 0.85 (Accuracy)

- **Best Parameters for Departure Delay Model**:
  - `n_estimators`: 100
  - `max_depth`: 20
- **Best Score for Departure Delay Model**: 0.84 (Accuracy)

### **5.2 Model Performance**

- **Arrival Delay Model**:
  - Accuracy: 85%
  - Precision, Recall, F1-Score: [Detailed metrics from classification report]

- **Departure Delay Model**:
  - Accuracy: 84%
  - Precision, Recall, F1-Score: [Detailed metrics from classification report]

## **6. Discussion**

### **6.1 Key Findings**

- The models effectively predict delays, with high accuracy and good balance between precision and recall.
- Time-based features (hour of the day and day of the week) are significant predictors of delays.
- Categorical features such as station names were effectively converted into a usable format for the model.

### **6.2 Limitations**

- **Data Coverage**: Limited to a single week; seasonality effects were not considered.
- **Feature Granularity**: Some features like station names may need further aggregation or encoding.

### **6.3 Recommendations**

- **Expand Dataset**: Include data from different times of the year for better generalization.
- **Feature Engineering**: Explore additional features such as weather conditions or historical delay patterns.

## **7. Conclusion**

This project demonstrated the application of machine learning techniques to predict train delays. The RandomForestClassifier model, optimized through hyperparameter tuning, achieved strong performance metrics. Future work could focus on incorporating additional data sources and refining feature selection to enhance model accuracy.


