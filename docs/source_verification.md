# ✅ qgis-mapping 来源核实报告

> 2026-07-18 对项目中关键信息进行核实

---

## 一、软件安装核实

| 项目 | 路径 | 状态 |
|------|------|------|
| QGIS 3.44.12 | C:\Program Files\QGIS 3.44.12 | ✅ 已安装 |
| Python 2.7 (ArcGIS) | D:\Python27\ArcGIS10.8\ | ✅ ArcPy可用 |
| R 4.6.0 | C:\Program Files\R\R-4.6.0\ | ✅ 已安装 |

## 二、数据文件核实

| 数据 | 路径 | 状态 |
|------|------|------|
| 1-5级河流 shp | D:\ArcGIS\...\全国河流、行政区域shp\ | ✅ 存在 |
| 省界/国界 shp | 同上 | ✅ 存在 |
| 城市点 shp | 同上 | ✅ 存在 |
| DEM 高程 | D:\ArcGIS\DEM数据-中国\ | ✅ 存在 |
| 预处理好 DEM | D:\Reasonix\output\dem_yangtze.tif | ✅ 存在 |

## 三、在线底图URL核实

| 底图 | URL | 状态 |
|------|-----|------|
| ESRI卫星 | services.arcgisonline.com/.../World_Imagery/... | ✅ 可用 |
| OSM标准 | tile.openstreetmap.org/... | ✅ 可用 |

## 四、需要用户注意

| 项目 | 说明 |
|------|------|
| QGIS 插件安装 | QuickOSM 需在 QGIS 插件管理器安装 |
| 在线底图 | 首次加载需缓存，稍慢 |
| 中国地图规范 | 出版前必须申请审图号 |
