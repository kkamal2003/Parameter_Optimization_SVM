# Parameter_Optimization_SVM

### Methodology

#### Data Preparation:
- The dataset used in this project is from the steel industry, specifically for occupancy estimation.
- The dataset consists of various sensor readings such as temperature, light, sound, CO2 levels, and PIR (Passive Infrared) motion detection, along with a target variable indicating room occupancy count.
- The dataset contains 10129 entries and 19 columns.
- Initially, the 'Date' and 'Time' columns were dropped from the dataset since they were not relevant for modeling purposes.

#### Preprocessing:
- Standard scaling was applied to normalize the feature variables using `StandardScaler` from scikit-learn.
- The dataset was split into 10 random samples, each containing training and testing data with a 70:30 ratio, using `train_test_split` from scikit-learn. The randomness was controlled using different random states.

#### Model Training and Evaluation:
- Support Vector Machine (SVM) models were trained using the `SVC` class from scikit-learn with different kernels (linear, polynomial, radial basis function, and sigmoid).
- A grid search approach was employed to tune the hyperparameters `C` (regularization parameter) and `gamma` for the radial basis function and polynomial kernels.
- The `max_iter` parameter was set to 100 to limit the maximum number of iterations for convergence.
- For each sample, the best combination of hyperparameters (kernel, C, gamma) was determined based on the highest accuracy score achieved by the SVM model on the test data.
- The best hyperparameters and corresponding accuracy scores were recorded for each sample.
- The results were stored in a pandas DataFrame for further analysis and comparison.

#### Results:
- The results show the best accuracy achieved along with the corresponding values of C, gamma, and kernel for each sample.
- The DataFrame provides insights into the performance of SVM models with different hyperparameter configurations across multiple random samples.
- This approach helps in understanding the variability of model performance and selecting the most suitable hyperparameters for robust SVM models.
