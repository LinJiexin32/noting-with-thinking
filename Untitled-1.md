## Landsat 各代传感器生成的NDVI存在系统性误差的问题
Spatiotemporally consistent global dataset of the GIMMS Normalized 
Difference Vegetation Index (PKU GIMMS NDVI) from 1982 to 2020

中提到NDVI Landsat 5 < 7 < 8。然后使用误差反向传播网络(BNPP)来将Landsat5 和 Landsat 7 矫正到Landsat 7 的水平。

做法是取观测时间在10天以内的7-8/7-5数据作为观测对，将8/5作为自变量，7作为因变量，同时辅以观测时间、经纬度作为协助变量。使用上万个观测对样本来训练模型。将百分之80的观测对作为训练数据，百分之二十的观测对作为验证数据。

文章该处引用了“**Summer warming explains widespread but not
uniform greening in the Arctic tundra biome**”这篇文章。