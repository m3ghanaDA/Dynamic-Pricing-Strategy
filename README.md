# Dynamic Pricing Strategy for Ride-Sharing Company

## 1. Problem Definition

### Objective
The primary goal of this project was to develop a **Dynamic Pricing Strategy** for a ride-sharing company using Machine Learning. The objective was to optimize pricing in real-time by dynamically adjusting ride costs based on supply-demand factors to maximize revenue and improve customer satisfaction.

### Problem
The company previously used a static pricing model that didn’t account for fluctuations in supply and demand. This led to:
- Missed opportunities during high-demand periods.
- Inefficient pricing during low-demand times.

---

## 2. Data Collection & Understanding

### Data Sources
The dataset used for the project included:
- **Historical sales data** (e.g., cost of rides, number of riders, and drivers).
- **Customer behavior data** (e.g., ride durations, vehicle types).
- **Market demand and supply data** (e.g., number of available drivers, traffic patterns).

### Main Features
- **Number of Riders**
- **Number of Drivers**
- **Location Category** (Urban, Suburban, Rural)
- **Expected Ride Duration**
- **Historical Cost of Ride**
- **Vehicle Type** (Premium, Economy)

---

## 3. Data Preprocessing

### Handling Missing Data
- Filled missing numeric values with the mean of the respective feature.
- Filled missing categorical values with the mode (most frequent value).

### Outlier Detection & Removal
- Detected outliers using the Interquartile Range (IQR) method.
- Replaced outliers with the mean for affected features.

### Feature Engineering
- Converted categorical features like **Vehicle Type** into numeric representations (1 for Premium, 0 for Economy).
- Created new features:
  - **Demand Multiplier** and **Supply Multiplier** based on percentile-based thresholds to reflect high or low demand/supply conditions.

---

## 4. Exploratory Data Analysis (EDA)

### Descriptive Statistics
- Calculated mean, median, and standard deviation for ride durations, costs, and number of riders/drivers.

### Visualization
- **Scatter Plots**: Explored relationships (e.g., ride duration vs. historical cost).
- **Box Plots**: Visualized ride cost distributions by vehicle type.
- **Heatmaps**: Displayed correlations between variables such as Number of Riders, Number of Drivers, and Cost of Rides.

---

## 5. Model Development & Implementation

### Dynamic Pricing Algorithm
A dynamic pricing model was developed to adjust prices based on demand and supply:
- **Demand Multiplier**: Calculated using the 75th and 25th percentiles of the Number of Riders. Prices increased with high demand and reduced with low demand.
- **Supply Multiplier**: Calculated using the Number of Drivers. Prices adjusted inversely to supply (higher prices for lower supply).

### Adjusted Ride Cost Formula
Adjusted Ride Cost = Historical Cost × Demand Multiplier × Supply Multiplier

---

## 6. Model Training & Prediction

### Machine Learning Model
A **Random Forest Regressor** was trained to predict the adjusted ride cost using the following features:
- Number of Riders
- Number of Drivers
- Vehicle Type (Economy/Premium)
- Expected Ride Duration

### Model Training
- The dataset was split into training (80%) and test (20%) sets.
- The model was trained on the training set using historical data.

### Model Evaluation
- Predictions from the test set were compared to actual ride costs.
- Scatter plots visualized the relationship between predicted and actual ride costs.

---

## 7. Results & Evaluation

### Profitability Analysis
- The profit percentage for each ride was calculated by comparing the adjusted ride cost with the historical cost.
- **Visualization**: A donut chart displayed the proportion of profitable rides versus loss-making rides.
- **Results**: Significant improvement in profitability, especially during high-demand, low-supply scenarios.

---

## 8. Deployment & Future Work

### Deployment Considerations
- The dynamic pricing model can be deployed in real-time to adjust ride prices based on:
  - Current rider demand.
  - Driver availability.
  - Events affecting traffic conditions.
- The model will require regular updates with real-time data inputs.

### Future Work
1. **Enhancing Features**:
   - Incorporate additional factors such as weather conditions, local events, and competitor pricing.
2. **Model Optimization**:
   - Experiment with advanced machine learning algorithms (e.g., Gradient Boosting, XGBoost) for improved prediction accuracy.
3. **Scalability**:
   - Expand the model to cover different geographic locations, accounting for regional pricing factors.

---

## Conclusion
The implementation of a dynamic pricing strategy significantly improved the company’s revenue potential and customer satisfaction by leveraging real-time supply-demand conditions. This project highlights the power of Machine Learning in driving operational efficiency and profitability in ride-sharing platforms.
