### Scaling in Pandas (Pre-processing of data values)
#### Standard scalar 
The StandardScaler assumes your data is normally distributed within each feature and will scale them such that the distribution is now centred around 0, with a standard deviation of 1.
If data is not normally distributed, this is not the best scaler to use.

#### Min-Max scalar
It essentially shrinks the range such that the range is now between 0 and 1 (or -1 to 1 if there are negative values). This scaler works better for cases in which the standard scaler might not work so well. If the distribution is not Gaussian or the standard deviation is very small, the min-max scaler works better. However, it is sensitive to outliers, so if there are outliers in the data, you might want to consider the Robust Scaler.

#### Robust scalar
The RobustScaler uses a similar method to the Min-Max scaler but it instead uses the interquartile range, rathar than the min-max, so that it is robust to outliers. Of course this means it is using the less of the data for scaling so it’s more suitable for when there are outliers in the data.

#### Normalizer
The normalizer scales each value by dividing each value by its magnitude in n-dimensional space for n number of features.

* Ref link - http://benalexkeen.com/feature-scaling-with-scikit-learn/
