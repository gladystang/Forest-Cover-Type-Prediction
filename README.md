# Forest-Cover-Type-Prediction
Rather than having to rely on costly and time-consuming recordings by forestry personnel,
it would be beneficial to create an accurate model for predicting cover type in a given 
wilderness area. This is the purpose of the topic, and it comesdirectly from a data competition 
on the Kaggle website.
Kaggle obtained the data from the US Geological Survey and USFS. The training data set consists 
of 15,120 observations, containing 55 descriptive cartographic attributes (including elevation,
slope, 40 binary variables indicating soil type, and other variables), as well as a column 
indicatingone of seven predominant forest cover types. In contrast, the test set consists of 
565,892 observations, containing only the descriptive features. For each observation in the 
test set, we are to predict an integer classification, indicating the predominant cover type 
for a given 30 m by 30 m patch of land in the Roosevelt National Forest.

Due to the high dimensionality (both in variables and in classification options), it is suspect
that support vector machine and neural network would not be effective classification techniques.
Therefore, we have used RandomForest (RF), ExtraTrees (ET) and Gradient Boosting (GBM), which 
perform well in a high-dimensional situation. Early prediction results and confusion matrices
indicate that the testing data is probably highly unbalanced. While the training data set has 
2160 observations for each of the seven cover types, the test data set appears to be primarily cover types
1 and 2 (Spruce/Fir and Lodgepole Pine). Moreover, types 1 and 2 are not easily distinguishable 
from each other and are often misclassified. This motivates the idea of using a two-step boosting
method, which is discussed in greater detail in the Data Mining section of this report. Another 
challenge with this classification problem is that we have an extremely small training data set
relative to the test data set. We used resampling of the training data to combat this challenge,
which did not improve our results. However, resampling techniques to counteract the unbalanced
cover type observations did improve results. With the resampling technique, the two-step boosting idea,
and several new variables, we achieved our best prediction accuracy of 0.83347 using ET,
which placed us 19th out of more than 1611 teams in the Kaggle competition
