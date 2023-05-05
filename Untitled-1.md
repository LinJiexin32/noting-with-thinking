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

校正方法：取D-1，D+1的均值，与D天的值做最小二乘回归。得到**乘法因子1.03723**。Landsat-5 NDVI乘以该因子，以产生等效的Landsat-7的NDVI。

NDVI平均差值为0.019，且Landsat-5/Landsat-7的NDVI差异幅度(0.02)明显小于本研究中发现的许多NDVI差异，因此绿化的基本地理格局不受差异的影响。

***
文章 **Characterization of Landsat-7 to Landsat-8
Reflective Wavelength and Normalized Difference
Vegetation Index Continuity**中给出了 ETM+ 和 OLI NDVI 和各波段值的转换函数，是USGS最推荐的。

NDVI 转换函数
![](./asset/%E8%BD%AC%E6%8D%A2%E5%85%B3%E7%B3%BBNDVI.png)

各波段转换函数
![](./asset/%E5%90%84%E6%B3%A2%E6%AE%B5%E8%BD%AC%E6%8D%A2%E5%85%B3%E7%B3%BB.png)
***
## 相较于MODIS和AVHRR，Landsat的高空间分辨率特性 对山区植被时序分析的优势

文章 **Landsat-based multi-decadal spatio-temporal assessment of the vegetation greening and browning trend in the Eastern Indian Himalayan Region**中

提到：在喜马拉雅地区，由于植被覆盖类型和土地利用类型的高空间异质性和精细尺度多样性，中分辨率的MODIS和粗分辨率的GIMMS无法准确捕捉到细小空间范围内地形和植被的显著变化。

关于差异性的问题：该文章中引用了其他人的研究，提到在喜马拉雅地区GIMMS/MODIS NDVI评估的植被变化趋势和Landsat的不一致性。
该文章认为差异的原因：应用方法的差异、不同的尺度(像素大小)可以解释这些不一致。

引用了如下内容：
1. 与MODIS和avhrr衍生的植被产品相比，Landsat数据的高空间分辨率特性为山区植被时序分析提供了相当大的优势(Anderson et al, 2020，**Vegetation expansion in the subnival Hindu Kush Himalaya**)
2. Fassnacht等人(2019)证实了500m分辨率的modis衍生的NDVI在绘制青藏高原(TP)高海拔植被变化方面缺乏适合性。（lack of fitness of coarse-grained 500 m resolution MODIS-derived NDVI for mapping changes in high altitude vegetation on the Tibetan Plateau），而基于Landsat的NDVI数据成功捕获了TP土地覆盖变化的详细空间格局(Fassnacht et al, 2019，**A Landsat-based vegetation trend product of the Tibetan Plateau for the time-period 1990–2018**)
3. 利用NDVI时间序列对植被变绿/褐化趋势的估计在很大程度上取决于所分析卫星数据集的特征、它们的时空分辨率、所选择的时间段(月/季)以及研究中应用的统计方法(Forkel et al,2013，**Trend change detection in NDVI time series: effects of inter-annual variability and methodology** ;Fassnacht et al, 2019)。