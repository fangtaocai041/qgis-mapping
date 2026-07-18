# 🗺️ QGIS 专业制图项目

> QGIS 3.44 长江水系图 / 鱼类采样点 / 生态学地图
> 配合 `/qgis-mapping` 技能调用

---

## 核心脚本

| 脚本 | 功能 | 位置 |
|------|------|------|
| `yangtze_qgis.py` | QGIS 自动加载 shp + 基础配色 + 地图定位 | `D:\Reasonix\scripts\` |
| `yangtze_qgis_style.py` | 专业配色 + 打印布局 + 自动导出 PNG/SVG | `D:\Reasonix\scripts\` |
| SKILL.md | Reasonix 技能定义（入口：`/qgis-mapping`） | 本目录 |

### 用法

```
QGIS → 插件 → Python 控制台 → 依次运行：

# 第一步：加载数据+配色
exec(open(r"D:\Reasonix\scripts\yangtze_qgis.py", encoding='utf-8').read())

# 第二步：专业布局+导出
exec(open(r"D:\Reasonix\scripts\yangtze_qgis_style.py", encoding='utf-8').read())
```

## 数据源

### 本地 shp（D:\ArcGIS\）
```
全国河流、行政区域shp/
├── 一级河流/湖泊面
├── 二级河流
├── 四级/五级河流
├── 省界/国界
└── 省会城市点
```

### 在线底图（QGIS XYZ Tiles）

| 名称 | URL |
|------|-----|
| 🛰️ ESRI卫星 | `https://services.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer/tile/{z}/{y}/{x}` |
| 🗺️ OSM标准 | `https://tile.openstreetmap.org/{z}/{x}/{y}.png` |
| 🏔️ ESRI地形 | `https://services.arcgisonline.com/ArcGIS/rest/services/World_Terrain_Base/MapServer/tile/{z}/{y}/{x}` |

> 添加：QGIS左侧浏览器 → XYZ Tiles → 右键 → 新建连接 → 粘贴URL

### QuickOSM 插件（在线抓取）
```
插件 → QuickOSM
省界: Key=boundary Value=administrative In=China
河流: Key=waterway Value=river In=China
```

## 配色速查

| 图层 | 色号 | 线宽 |
|------|------|------|
| 一级河流 | `#053061` 深蓝 | 2.8pt |
| 二级河流 | `#2C7BB6` 中蓝 | 1.0pt |
| 四级河流 | `#80B8D8` 浅蓝 | 0.3pt |
| 湖泊 | `#ABD9E9` 填充 | 50%透明 |
| 省界 | `#999999` 灰色虚线 | 0.4pt |
| 国界 | `#333333` 深灰实线 | 1.5pt |
| 采样点 | `#D73027` 红色 | 3pt |

## ⚠️ 中国地图规范

- 出版前须申请**审图号**（省级自然资源厅）
- 必须含**九段线**、台湾标注正确
- 本地 shp 边界已合规
- 详见 `docs/中国地图规范.md`

## 输出

所有地图输出到 `D:\Reasonix\output\`：
- `yangtze_river_map.png/svg`（v1 tmap版）
- `yangtze_river_map_v2.png`（v2 含湖泊）
- `yangtze_river_v3.png/svg`（v3 ggplot2精细版）
- `yangtze_qgis_layout.png/svg`（QGIS布局版）

## 其他制图方式

| 方式 | 脚本 | 说明 |
|------|------|------|
| R tmap | `yangtze_map.R` / v2 / v3 | DEM底图+河流光晕 |
| ArcPy | `yangtze_arcmap.py` | ArcGIS Desktop 10.8 |
| ggplot2 | `yangtze_map_v3.R` | ggrepel标签+精细控制 |

> 需要制图时，直接输入 `/qgis-mapping` 调出技能
