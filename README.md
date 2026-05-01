# DATA3402.Spring.2026
# <img width="200" height="200" alt="pngtree-mail-notification-png-image_6621555" src="https://github.com/user-attachments/assets/c0bf235c-7883-41a3-82d0-da4379ab2c8a" /> Springleaf Marketing Response Project


* **One Sentence Summary**: This project uses a machine learning model to predict how customers will respond to direct mail offers, based on the Springleaf Marketing Response dataset.

## Overview
* **Definition of the tasks / challenge**: The goal is to work with a very large dataset of anonymized features and predict whether a customer will respond to a loan offer.
* **My approach**: I used a Random Forest Classifier after doing a lot of data cleaning, like removing features that don’t change and filling in missing values with the median.
* **Summary of performance**: The model achieved a validation AUC score of 0.7266, which shows that it does a better prediction than a 50/50 chance of customer responses.

## Summary of Workdone

### Data
* **Type**: Tabular CSV file with anonymized customer features.
* **Size**: About 1,934 features and 10,000 rows in the dataset.
* **Instances**: 8,000 samples were used for training and 2,000 for validation (80/20 split).

### Preprocessing / Clean up
* **Constant Column Removal**: Removed features that had the same value in every row since they don’t help with predictions.

* **Missing Value Imputation**: Filled missing numerical values with the median and replaced missing categorical values with “Unknown.”

* **Label Encoding**: Converted 51 categorical features into numerical values so the model could process them.

### Data Visualization
* **Target Distribution**: Analyzed the class imbalance, finding that 78.01% were non-responders and 21.99% were responders.

* **Feature Analysis**: Generated KDE plots for numerical features (like VAR_0002) to compare distributions between classes.
### Problem Formulation
* **Input / Output**: The input is all the cleaned features (excluding the ID column), and the output is a binary target (0 or 1).

* **Models**: I used a Random Forest Classifier since it works well with large datasets and can handle complex patterns.

* **Hyperparameters**: I set the model with 100 trees (n_estimators=100), a max depth of 10, and used random_state=42 for consistency.
* **Training**: Used Python with Pandas and Scikit-Learn, and ran everything on Google Colab for better performance.

* **Performance Metric**: Evaluated the model using AUC (Area Under the ROC Curve).
### Conclusions 
* The project was able to handle a dataset with nearly 2,000 features. The AUC score of 0.7266 shows that even with basic data cleaning and a standard Random Forest model, we can do a solid job predicting which customers are more likely to respond.
### Future Work
* **Advanced Feature Selection**: Try methods like Recursive Feature Elimination (RFE) to reduce the number of features further.
* **Gradient Boosting**: Test models like XGBoost or LightGBM, which usually perform better on tabular datasets like this.
### How to Reproduce the Results

* To fully reproduce this project, follow these steps: Environment: I used Google Colab with a standard Python 3 runtime. No special hardware is needed since the model is a Random Forest.

* **Data Collection**: Download the train.csv and test.csv files from the Springleaf Marketing Response Kaggle competition page.

* **Setup**: Upload both files into your Google Drive, inside the MyDrive folder so Colab can access them easily.

* **Running the Code**: Open the Springleaf_Final.ipynb notebook in Google Colab and run all the cells in order. Make sure the Google Drive mount path matches where your CSV files are stored so the notebook can load the data correctly.
### Overview of files in repository
* **Directory Structure**: All files are located in the root directory for easy access via Google Colab.

* **Springleaf_Final.ipynb**: This is the main Jupyter Notebook containing the end-to-end pipeline, including data loading, cleaning, visualization, and model training.

* **submission.csv**: The final output file containing the predicted probabilities for the test set, formatted exactly as required by the Kaggle competition.
### Required Packages:
* This project uses a few common Python libraries:
  * pandas for handling and analyzing data
  * numpy for numerical computations
  * matplotlib and seaborn for visualizing data
  * scikit-learn for building and evaluating machine learning models
* Installation: These libraries are already included in Google Colab by default. If running the project on a local machine instead, they can be installed using: pip install pandas numpy matplotlib seaborn scikit-learn

* Setup: No additional setup or custom installations are needed. You can simply upload the notebook into Google Colab and mount your Google Drive so it can access the train.csv and test.csv files.
### Data:
* Data Download: The dataset is available from the official Kaggle competition page: Springleaf Marketing Response Data.
* Preprocessing Steps: The train.csv and test.csv files should be uploaded to Google Drive. The code automatically removes constant columns to help manage the high number of features. Missing numerical values are replaced with the median of each column, while missing categorical values are labeled as "Unknown". Categorical variables are converted into numeric form using LabelEncoder so they can be used in the model.

### Training
* How to train the model:Open the Springleaf_Final.ipynb notebook in Google Colab. Run the initial cells to mount Google Drive and import all required libraries. Run the training cell that contains the RandomForestClassifier. The model uses n_estimators=100 and max_depth=10, which provides a balance between performance and training efficiency. The model is configured with n_estimators=100 and max_depth=10 to provide a balance between training speed and predictive power.

### Performance Evaluation
* How to run evaluation: Execute the evaluation cell in the notebook, which splits 20% of the training data for validation. The output includes the Area Under the ROC Curve (AUC) score. You can also generate a ROC curve plot using the provided Matplotlib code to compare predicted probabilities with actual outcomes.
### Citations
* Kaggle. (2015). Springleaf Marketing Response: Predict which customers will respond to a direct mail offer.
* Pedregosa, F., et al. (2011). Scikit-learn: Machine Learning in Python. Journal of Machine Learning Research.
