# Course Project I: Diamond Dataset
*Team ID*: 02
*Dataset*: Diamond

## Kaagle's Largest Diamond Dataset
This dataset contains information about various aspects of diamonds. Here is a brief overview of the columns in the dataset:

- *Cut*: This column describes one of the 10 or so most common diamond cuts.
- *Color*: Diamonds are graded from D to Z, with higher letters indicating a more yellowish hue. However, diamonds with higher color grades are often better values since color is difficult to distinguish once the diamond is set in a ring.
- *Clarity*: Clarity refers to the presence of inclusions (internal flaws) in the diamonds as seen through a jeweler's loupe or microscope. Diamonds with fewer and smaller inclusions are considered better in terms of clarity.
- *Carat Weight*: This column refers to the mass of the diamond. It is loosely connected to the dimensions of the diamond, but the cut and cut quality also play significant roles in a diamond's appearance.
- *Cut Quality*: This column refers to the GIA Cut Grading System, which was developed in 2005 and has become the de facto standard for evaluating diamond cuts.
- *Lab*: This column indicates the grading lab responsible for assessing the diamond. The major labs include GIA, IGI, and HRD, each providing a lab certificate for the diamond.
- *Eye-Clean*: This column grades the visibility of blemishes or inclusions to the naked eye, with 10 possible grades.
- *Culet Size*: Culet size is the size of the circle visible when looking straight down at the diamond. None is considered ideal because it affects the amount of reflected light.
- *Culet Condition*: This column indicates if the culet has any chipping, which can cause some diamonds to have a very small flat spot instead of a point.
- *Fancy Color*: Columns related to colored diamonds, which can be natural or lab-grown. These columns provide information about colors, secondary colors, and their intensity.
- *Fluorescence (Fluor)*: This column refers to the effect of long-wave UV light on the diamond. Approximately 25-35% of diamonds exhibit fluorescence, with about 10% of those cases being noticeable to an expert.
- *Depth Percent and Table Percent*: These columns represent relative measurements of the flat part on top and the depth of the diamond, which may vary based on the cut.
- *Measurements (Length, Width, Depth)*: These columns provide the absolute measurements of the diamond.
- *Girdle (Min/Max)*: The girdle is where the ID of a stone is engraved and where the diamond meets the setting. It plays a role in light reflection, with nine possible values ranging from extremely thin to extremely thick.
- *Fancy (Colored Diamonds)*: These columns pertain to colored diamonds, which can be natural or lab-grown. They describe different colors, secondary colors, and their intensity.
- *Total Sales Price*: The price of the diamond, denominated in dollars.

## Dataset Information
- *Size*: 25 columns and 219,703 rows.

## Handling 'Unknown' Values
- We perform the task of identifying 'unknown' values on a copied dataset rather than the original data.
- Handling 'unknown' values for various features:
    - For the 'Color' feature, we substitute 'unknown' values with the mode value.
    - For 'Cut Quality,' we utilize information from other features to replace 'unknown' values.
    - 'Culet Size' is imputed with the mode value.
    - 'Girdle Min/Max' values are replaced with the mode value.
    - Features like 'Eye-Clean,' 'Culet Condition,' 'Fluorescence Color,' 'Fluorescence Intensity,' 'Fancy Color Dominant Color,' 'Fancy Color Secondary Color,' 'Fancy Color Overtone,' and 'Fancy Color Intensity' are removed due to a high number of 'unknown' values.

## Feature Engineering
- Categorical features are encoded into numerical features:
    - Nominal features are one-hot encoded.
    - Ordinal features are label encoded.
- Features are divided into independent and dependent features.
- Feature scaling is applied using the RobustScaler class.

## Modeling
We utilized two different models for predicting the dependent feature 'y':
1. Ridge Model
2. Lasso Model

Our modeling process included data splitting, Grid Search Cross-Validation (GSCV) for hyperparameter tuning, and model evaluation using metrics such as Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and R-squared (R^2).

By following these steps, our models are now ready for further analysis and deployment.
