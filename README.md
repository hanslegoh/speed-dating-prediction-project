# Speed Dating Prediction Project

**Purpose: Create a machine learning model to predict whether two people would be a match after a speed date with an accuracy of 85% or higher.**

## Preprocessing Methods

- Initially dropped three columns, `has_null`, `decision`, `decision_o`, as the decision columns were heavily weighted in the random forest model. This is due to the direct influence that the decision columns have on the target column `match`.
- Cleaned the data by removing unnecessary additions to the data.
- Changed the `gender` column values to binary, then changed the data type for all binary columns to float64.
- Converted columns with categorical data to numeric.
- Dropped rows with any missing values to create a clean dataset.
- Assigned the target variable as `match` and the rest as features.
- Split the data into training and testing sets, and scaled the features.

## Utilized Models

- Logistic Regression Model
    - The accuracy of the model was 0.8511, but both the precision and recall for a *yes* to the match were below optimal at 0.60 and 0.51, respectively.
    - The confusion matrix illustrated both type I and type II errors.
- Random Forest Model
    - The model was set up with 1,000 estimators and in the same way as for the logistic regression model with the confusion matrix, accuracy score, and classification report.
    - The accuracy of the model was 0.8435, which is lower than that for the logistic regression model, fairly unexpected.
    - This model also illustrated lower precision and recall for a *yes* to the match at 0.67 and 0.26, respectively.
- Deep Learning Model
    - The model is a sequential model with the Kerastuner to decide the number of hidden layers, number of neurons, and activation functions.
    - A regularizer was added to the model to control the potential overfitting to the training data.
    - With the tuner search, the resulting model had an accuracy of 0.8817, which is higher than the ones for the previous two models.
    - After fitting the model with the entire training data, it resulted in an accuracy of 0.8321 and a loss of 0.6092, much lower loss and accuracy.

# References

- [Kaggle Dataset](https://www.kaggle.com/datasets/ulrikthygepedersen/speed-dating?resource=download)
- [Stack Overflow - apply() function](https://stackoverflow.com/questions/34962104/how-can-i-use-the-apply-function-for-a-single-column)
- [SaturnCloud - convert columns to string](https://saturncloud.io/blog/how-to-convert-columns-to-string-in-pandas/#:~:text=To%20convert%20columns%20to%20string%20in%20Pandas%2C%20we%20can%20use,to%20a%20specified%20data%20type.&text=This%20code%20will%20convert%20the,for%20further%20analysis%20or%20manipulation.)
- [TensorFlow - Overfit and underfit](https://www.tensorflow.org/tutorials/keras/overfit_and_underfit)
- [Stack Overflow - saving plots to png](https://stackoverflow.com/questions/19555525/saving-plots-axessubplot-generated-from-python-pandas-with-matplotlibs-savefi)
- [Stack Overflow - early stopping in Keras search](https://stackoverflow.com/questions/56208607/early-stopping-does-not-work-in-my-code-in-keras-with-tensorflow)