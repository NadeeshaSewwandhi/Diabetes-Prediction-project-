# Diabetes-Prediction-project
# Introduction 
Diabetes is a long term health complication or disease that is registered with millions of patients globally. It is advisable for diabetes to be detected at an early stage and managed effectively so that people who have this disease can lead healthy lifestyles. This project aims at designing an aid in the form of a machine learning predictor model to the possibility of diabetic occurrence in patients through the analysis of determinable, medical predictor variables.

Thus, using the six described machine learning techniques, we strive to construct a stable classifier that would enable diagnosing the presence of diabetes given Pregnancies, Glucose, Blood Pressure, Skin Thickness, Insulin, BMI, Diabetes Pedigree Function, and Age. This model may help physicians and other related healthcare providers to at least find and recognize those patients who are at the highest risk and therefore, to make proper decisions regarding their management.

The structure of the project divided into several stages based on the sequence of operations that involve importing required libraries and data, performing exploratory data analysis, data preprocessing, training the model, and making predictions on new observations. Every stage is explained in detail to help the client comprehend the procedures of constructing and estimating the worth of the machine learning model.


# How it works :
Step 1: Importing Libraries :
In the initial step, we import essential libraries needed for the data analysis and machine learning process. numpy is imported for handling numerical operations and array manipulations efficiently. pandas is used for data manipulation and analysis, providing data structures like DataFrame for managing datasets. The StandardScaler from sklearn.preprocessing is employed to standardize features by removing the mean and scaling to unit variance. train_test_split from sklearn.model_selection is utilized to split the dataset into training and testing sets, ensuring proper evaluation of the model. The svm module from sklearn provides the support vector machine algorithm for classification tasks, and accuracy_score from sklearn.metrics is used to evaluate the model's performance by comparing predicted values with actual values.

Step 2: Loading the Dataset :
In this step, we load the diabetes dataset into a pandas DataFrame using pd.read_csv. This step is crucial as it provides the data needed for analysis and model building. The dataset contains various medical predictor variables and one target variable, 'Outcome', which indicates whether a person has diabetes or not. Loading the data into a DataFrame allows us to utilize pandas' powerful data manipulation capabilities to clean, explore, and preprocess the data before applying machine learning algorithms.

Step 3: Data Exploration :
After loading the data, we perform data exploration to understand its structure and characteristics. We use the describe() method to obtain statistical measures such as mean, standard deviation, minimum, and maximum values for each feature. This helps in identifying any anomalies or outliers in the data. We also count the occurrences of each class in the 'Outcome' column using value_counts() to understand the distribution of diabetic and non-diabetic cases. Additionally, grouping the data by 'Outcome' and calculating the mean of each feature provides insights into how different features vary between the two classes, which can be informative for the model.

Step 4: Separating Data and Labels :
In this step, we separate the features and labels from the dataset. We create the feature set X by dropping the 'Outcome' column from the DataFrame, which contains all the predictor variables. The label set Y is created by extracting the 'Outcome' column, which contains the target variable indicating the presence of diabetes. This separation is necessary because machine learning algorithms require the features and labels to be provided separately during the training and prediction phases.

Step 5: Standardizing the Data :
Standardization is a crucial preprocessing step where we transform the features to have a mean of zero and a standard deviation of one. This is achieved using StandardScaler from sklearn.preprocessing. Standardization ensures that all features contribute equally to the model and prevents features with larger scales from dominating those with smaller scales. In this step, we fit the scaler to the feature set X and transform it, resulting in standardized features that are used for training and testing the model.

Step 6: Splitting the Data :
We split the standardized data into training and testing sets using train_test_split from sklearn.model_selection. We allocate 80% of the data for training and 20% for testing by setting test_size=0.2. The stratify=Y parameter ensures that the split maintains the same proportion of diabetic and non-diabetic cases as in the original dataset. This stratified split is important for maintaining the balance of classes in both training and testing sets, leading to a more reliable evaluation of the model's performance.

Step 7: Training the Model :
In this step, we initialize a support vector machine (SVM) classifier with a linear kernel using svm.SVC. The SVM algorithm is a powerful classification tool that finds the optimal hyperplane to separate different classes in the feature space. We train the classifier using the training data (X_train and Y_train) by calling the fit method. This training process involves finding the best parameters that minimize classification errors on the training data, effectively teaching the model to distinguish between diabetic and non-diabetic cases.

Step 8: Evaluating the Model :
Model evaluation is a critical step to assess the performance of the trained classifier. We first make predictions on the training data using the predict method and calculate the accuracy score by comparing the predicted labels with the actual labels. This gives us the training data accuracy, indicating how well the model has learned from the training set. Similarly, we make predictions on the test data and calculate the accuracy score to evaluate the model's performance on unseen data. This test data accuracy provides an unbiased estimate of the model's generalization capability to new data.

Step 9: Making a Prediction :
The final step involves making a prediction on new input data. We prepare the input data (a tuple of feature values) and convert it into a numpy array. The array is then reshaped to match the expected input shape for the model. We standardize the input data using the same scaler used for training, ensuring consistency in feature scaling. The standardized input data is fed into the trained classifier to make a prediction. The classifier outputs a label (0 or 1), which is interpreted to indicate whether the person is diabetic or not, based on the predicted value. This demonstrates the practical application of the model in making real-time predictions.
