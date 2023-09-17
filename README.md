Course Project I: Diamond Dataset
Team ID: 02
Dataset: Diamond

Kaagle's Largest Diamond Dataset
This dataset contains information about various aspects of diamonds. Here is a brief overview of the columns in the dataset:

Cut: This column describes one of the 10 or so most common diamond cuts.

Color: Diamonds are graded from D to Z, with higher letters indicating a more yellowish hue. However, diamonds with higher color grades are often better values since color is difficult to distinguish once the diamond is set in a ring.

Clarity: Clarity refers to the presence of inclusions (internal flaws) in the diamonds as seen through a jeweler's loupe or microscope. Diamonds with fewer and smaller inclusions are considered better in terms of clarity.

Carat Weight: This column refers to the mass of the diamond. It is loosely connected to the dimensions of the diamond, but the cut and cut quality also play significant roles in a diamond's appearance.

Cut Quality: This column refers to the GIA Cut Grading System, which was developed in 2005 and has become the de facto standard for evaluating diamond cuts.

Lab: This column indicates the grading lab responsible for assessing the diamond. The major labs include GIA, IGI, and HRD, each providing a lab certificate for the diamond.

Eye-Clean: This column grades the visibility of blemishes or inclusions to the naked eye, with 10 possible grades.

Culet Size: Culet size is the size of the circle visible when looking straight down at the diamond. None is considered ideal because it affects the amount of reflected light.

Culet Condition: This column indicates if the culet has any chipping, which can cause some diamonds to have a very small flat spot instead of a point.

Fancy Color: Columns related to colored diamonds, which can be natural or lab-grown. These columns provide information about colors, secondary colors, and their intensity.

Fluorescence (Fluor): This column refers to the effect of long-wave UV light on the diamond. Approximately 25-35% of diamonds exhibit fluorescence, with about 10% of those cases being noticeable to an expert.

Depth Percent and Table Percent: These columns represent relative measurements of the flat part on top and the depth of the diamond, which may vary based on the cut.

Measurements (Length, Width, Depth): These columns provide the absolute measurements of the diamond.

Girdle (Min/Max): The girdle is where the ID of a stone is engraved and where the diamond meets the setting. It plays a role in light reflection, with nine possible values ranging from extremely thin to extremely thick.

Fancy (Colored Diamonds): These columns pertain to colored diamonds, which can be natural or lab-grown. They describe different colors, secondary colors, and their intensity.

Total Sales Price: The price of the diamond, denominated in dollars.

This dataset contains valuable information for analyzing and understanding the characteristics and pricing of diamonds.









The size of our dataset is 25 columns and 219703 rows.


Although there are no null values within the feature, our dataset contains entries marked as 'unknown.
Thus, we need to address these 'unknown' values in our dataset and handle those unknown marked values.


Handling the 'Unknown' marked values

We perform the task of identifying 'unknown' values on a copied dataset rather than the original data.

1. handling unknown values in color feature

We will substitute the 'unknown' values with the mode value found in the 'color' feature.

Reason:We have selected the mode as our choice for imputation because 'color' is an independent feature in the dataset, meaning its value cannot be deduced from the values of other features.
2. handling unknown in cut_quality feature

We will replace the 'unknown' values by utilizing information from various other features such as 'symmetry,' 'polish,' and 'clarity.

Reason:The evaluation of 'cut_quality' is based on factors such as symmetry, polish, and clarity, following the guidelines of the GIA
3. handling unknown in culet_size
We will substitute the 'unknown' values with the mode value found in the 'culet_size' feature.

Reason:We have selected the mode as our choice for imputation because 'culet_size' is an independent feature in the dataset, meaning its value cannot be deduced from the values of other features.
4. handling unknown in griddle_min/griddle_max
 We will substitute the 'unknown' values with the mode value found in the 'griddle_min/griddle_max' feature.

Reason:Since this feature can only be derived from physical attributes such as measurements, proportions, and detailed gemological analysis, we will opt for the mode value of the feature to populate null or unknown values.
5. handling unknown in the features like eye_clean, culet_condition, fluor_color, fluor_intensity, fancy_color_dominant_color, fancy_color_secondary_color, fancy_color_overtone, fancy_color_intensity.

Just Remove the above feature from the dataset.

Reason:
We are removing the following features due to the presence of null values in more than half of the total entities. Furthermore, there are features below that are dependent on the removed features, so we must also remove those.
So now we have successfully eliminated the 'unknown' values from the feature.
First, we need to encode the categorical features. To do this, we'll categorize the features into two groups: ordinal features and nominal features. We will then apply encoding techniques specific to each feature type.
If there is Nominal features then we will use one-hot encoding because it's a suitable technique for representing categorical data where there is no inherent order or ranking among the categories and it ensure that the categorical data is properly represented without making any assumptions about the relationships between categories
If there is ordinal features then we will make use of label encoding because it assigns numerical labels to the categories in a way that respects their inherent order.
So now we have converted all the categorial features into the numerical features.

There are 29 features list below.
Below we have divided the independent and dependent features.

The next step in feature engineering involves standardizing or scaling the independent features.
We will make use of RobustScaler Class for the scaling because it is robust to outliers, meaning it is less influenced by extreme values in the dataset.

In below code we have done the scaling after spliting the data into the train and test set. It's actually doesn't make any difference if we do it before.
convert this to simple text

In our modeling phase, we have employed two different models for predicting the dependent feature 'y':

1. Ridge Model
2. Lasso Model

Here's a summary of the steps we followed in our modeling process:

1. Data Splitting: We divided our dataset into two parts, with 80% of the data allocated for training and the remaining 20% for testing.

2. Grid Search Cross-Validation (GSCV): We used the Grid Search Cross-Validation technique to fine-tune the hyperparameters of our models. This approach systematically evaluates the model's performance on various combinations of hyperparameters to identify the best set of hyperparameters.

3.Ridge Model Tuning: We applied GSCV to the Ridge model, searching for the optimal hyperparameters that would yield the best predictive performance.

4. Lasso Model Tuning: Similarly, we used GSCV for the Lasso model to determine the most suitable hyperparameters.

5. Model Evaluation: To assess the quality of our models, we employed three evaluation metrics:
   - Mean Absolute Error (MAE): This metric measures the average absolute difference between the predicted and actual values.
   - Root Mean Squared Error (RMSE):RMSE quantifies the average magnitude of the errors in the predicted values, providing insight into prediction accuracy.
   - R-squared (R^2): R-squared indicates the proportion of variance in the dependent variable that is predictable from the independent features. It ranges from 0 to 1, with higher values indicating better model fit.

By following these steps, we have effectively built and fine-tuned our Ridge and Lasso models, and we have evaluated their performance using MAE, RMSE, and R-squared metrics. These models are now ready for further analysis and deployment, helping us make predictions based on our dataset.
