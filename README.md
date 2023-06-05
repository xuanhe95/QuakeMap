<h1><p align="center"> 🗺️ QuakeMap 🗺️ </p></h1>

该项目来自[Object Oriented Java Programming: Data Structures and Beyond](https://www.coursera.org/specializations/java-object-oriented#courses)，由UC San Diego提供了程序的基础框架。   

该程序可以在GUI地图界面上实时显示世界上发生的地震，并根据不同的地震种类标识为不同的图标。
点击一个地震标记可以显示地震会波及到的城市范围。
另一个程序是在GUI地图界面上显示世界上的机场。



---

## 💻 程序设计
- 🗺️ 使用[UnfoldingMaps](http://unfoldingmaps.org)库来进行地图的GUI设计。
- 📖 从互联网API上获取数据并解析为Marker类，以显示在GUI上。
- ⭕️ 通过继承实现了不同Marker类，以实现在GUI地图上不同的显示效果。
- 🖥️ 通过重写PApplet接口，实现GUI的用户操作交互。
- 🔍 EarthQuakeMarker的比较器接口，以实现查找，排序和筛选不同地震级别的功能。

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
