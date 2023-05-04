## Landsat 各代传感器生成的NDVI存在系统性误差的问题
文章**Spatiotemporally consistent global dataset of the GIMMS Normalized 
Difference Vegetation Index (PKU GIMMS NDVI) from 1982 to 2020**

中提到NDVI Landsat 5 < 7 < 8。然后使用误差反向传播网络(BPNN)来将Landsat5 和 Landsat 8 矫正到Landsat 7 的水平。

做法是取观测时间在10天以内的7-8/7-5数据作为观测对，将8/5作为自变量，7作为因变量，同时辅以观测时间、经纬度作为协助变量。使用上万个观测对样本来训练模型。将百分之80的观测对作为训练数据，百分之二十的观测对作为验证数据。

文章该处引用了“**Summer warming explains widespread but not
uniform greening in the Arctic tundra biome**”这篇文章。

***

文章**The Vegetation Greenness Trend in Canada and US Alaska from 1984–2012**
中同样提到：
1. 存在Landsat5 NDVI < landsat7 NDVI的问题。
2. Landsat-5近红外SR相对小于Landsat-7近红外SR。
3. Landsat-5的红SR 相对大于Landsat-7的红SR。
   
NDVI观测三元的概念：对于同一位置，三天内有三个观测。假设第D天的观测值由Landsat7提供，则D-1，D+1天的观测值由landsat5提供。即5-7-5组合或7-5-7组合。

校正方法：取D-1，D+1的均值，与D天的值做最小二乘回归。得到乘法因子1.03723。Landsat-5 NDVI乘以该因子，以产生等效的Landsat-7的NDVI。

NDVI平均差值为0.019，且Landsat-5/Landsat-7的NDVI差异幅度(0.02)明显小于本研究中发现的许多NDVI差异，因此绿化的基本地理格局不受差异的影响。