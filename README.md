# QuakeMap

该程序基于UC San Diego提供的程序框架。   
使用了[UnfoldingMaps](http://unfoldingmaps.org)库。

---



## 💻程序设计
- 面向对象编程，使用继承创建出不同的Marker，并显示在UnfoldingMaps库提供的地图上。
- 实现了EarthQuakeMarker的比较器接口，以此筛选符合条件的地震级别。
- 标明每个地震可影响的城市范围。

---

## 🗺️ 程序截图
![](https://github.com/xuanhe95/QuakeMap/blob/main/JapanQuake.jpeg?raw=true)
---

# ⭕️ CommonMarker
CommonMarker类继承自UnfoldingMap库中的SimplePointMarker类。
- 项目中的所有Marker均继承CommonMarker类。
## 🌆 CityMarker
CityMarker继承了CommonMarker，
- 用来显示城市，在地图上显示为三角形。
## 🫨 EarthQuakeMarker
EarthQuakeMarker类是一个抽象类。
- 继承了CommonMarker，并实现了Comparable接口。
- 提供了抽象方法drawEarthquake。
### ⛰️ LandQuakeMarker
LandQuakeMarker继承了EarthQuakeMarker类，用来显示陆地上的地震。
- 重写了drawEarthquake方法，在地图上显示为圆形。
### 🌊 OceanQuakeMarker
OceanQuakeMarker继承了EarthQuakeMarker类，用来显示海洋中的地震。
- 重写了drawEarthquake方法，在地图上显示为方形。
## 🌍 EarthquakeCityMap
EarthquakeCityMap继承了PApplet接口。
- EarthquakeCityMap解析了[JSON](https://earthquake.usgs.gov/earthquakes/feed/v1.0/summary/2.5_week.atom)数据。
- 重写了mouseMoved()，mouseClicked()等方法以实现🖱️鼠标与🗺️地图的交互。
## ✈️ AirportMarker
AirportMarker类继承了CommonMarker类。
- 用来显示机场，在地图上显示为圆形。
- 重写了draw()，drawMark()以及showTitle()等方法。
## 🗺 AirportMap
AirportMarker继承了PApplet接口。
- AirportMarker解析了"airports.dat"文件的数据。
- 重写了mouseMoved()，mouseClicked()等方法以实现🖱️鼠标与🗺️地图的交互。
