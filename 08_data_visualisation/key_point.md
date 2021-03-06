# 数据可视化相关概念
## 数据可视化过程
1. 确定数据可视化的主题  
2. 提炼可视化主题的数据  
    1. 确定数据指标  
    2. 确定数据相互关系：趋势型、对比型、比例型、分布型、区间型、关联性、地理型
    3. 确定用户关注的重点指标  
3. 根据数据关系确定图表  
4. 进行可视化布局及设计：页面布局、图表制作  

## 数据可视化的基本流程
1. 数据采集：内部数据、外部数据
2. 数据处理和变换
    1. 常见质量问题：手机错误、离群点、遗漏值、不一致或不合常理、大量重复值
    2. 常用处理方法：降维、数据聚类和切分、抽样等
3. 可视化映射：可视化空间+标记+视觉通道
4. 人机交互：滚动和缩放、颜色映射的控制、数据映射方式的控制、数据细节层次控制
5. 用户感知

# 数据类型与图表
1. 趋势型：折线图、拟合曲线图、面积图、堆积面积图、阶梯图  
2. 对比型：对比≥2组数据的差异
    1. 高度差异/宽度差异：  
    柱状图：数据<12条，单一柱状图、重叠性柱状图（实际、目标）、并列柱状图（≤3类）、堆叠柱状图（总体&构成≤5类）  
    条形图：<30条数据  
    2. 面积差异：  
    面积图：重叠对比型、堆砌对比性  
    气泡图：三维数据可视化  
    3. 字号差异：词云  
    4. 形状差异：  
    雷达图：一体多维  
    星状图：多体多维 
    南丁格尔图（极坐标图）  
    切尔诺夫脸谱图  
3. 时序型：
  1. 离散时间：  
  单一柱状图：单一系列随时间变化, data<12条  
  并列柱状图：多系列（≤3）随时间变化  
  堆叠柱状图：普通堆叠、百分比堆叠，分组≤5  
  散点图：数据点与时间的相对关系，不同颜色体现不同系列  
  2. 连续时间：  
  折线图：点线图(<12条)、折线图(>12条)、曲线图  
  阶梯图：相邻时间节点的数据升降  
  拟合曲线图：多个离散点拟合一个连续函数  
  面积图、堆叠面积图  
4. 比例型  
    1. 不含时间属性：  
    饼图：5-7个扇区  
    环形图：中空部分方标签、整体、平均数值  
    矩形树图：树状结构数据（一级分类、二级分类...）  
    2. 含时间属性：  
    百分比堆叠面积图  
    百分比堆叠柱状图  
5. 分布型：研究数据分布的集中趋势、离散程度、偏态、峰度  
散点图、气泡图：二维v.s.三维  
直方图：频率分布直方图、频数分布直方图  
概率密度图  
茎叶图  
箱线图：多组数据的分布情况，检测离群点  
热力图：热力地图、网页分析、业务数据  
地图：二维、三维  
6. 区间型：仪表盘、进度条、环形进度图  
7. 关联性：韦恩图、漏斗图、桑基图、矩形树图、节点关系图  
8. 地理型：二维地图（区域地图、道路地图、室内地图）、三维地图（全景地图）  

# 图表类型
1. 散点图：变量之间关系  
2. 折线图：数据趋势，x轴为时间  
3. 柱形图：堆积柱形图、瀑布图、横向条形图、横轴正负图  
4. 地理图  
5. 饼图：扇面、圆环、多圆环嵌套，表达一类占比较大  
6. 雷达图  
7. 箱线图  
8. 热力图  
9. 关系图  
10. 矩形树图：面积表现数值，颜色表现类目  
11. 桑基图：用户行为和流量分析  
12. 漏斗图  
13. 其他：词云图、气泡图、K线图  
