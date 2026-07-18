# 🗺️ QGIS 专业制图项目

> 长江水系图 / 鱼类采样点 / 生态学地图自动制图
> QGIS 3.44 + 一键加载脚本 + 专业配色

---

## 快速开始

```bash
# 在 Reasonix 会话中
/qgis-mapping 我要画采样点分布图
```

## 项目结构

```
├── README.md                 # 项目总览
├── LICENSE                   # MIT 许可证
├── CHANGELOG.md              # 变更日志
├── .gitignore
│
├── scripts/                  # QGIS Python 脚本
│   ├── yangtze_qgis.py       #   自动加载+配色
│   └── yangtze_qgis_style.py #   专业配色+布局+导出
│
├── docs/                     # 文档
│   ├── references/           #   参考资料
│   │   ├── 配色方案.md       #     ColorBrewer 色板
│   │   ├── 在线底图.md       #     XYZ Tile URL
│   │   ├── 布局指南.md       #     打印布局教程
│   │   └── 中国地图规范.md   #     九段线/审图号
│   └── source_verification.md#   来源核实
│
├── templates/                # QGIS 项目模板
├── data/raw/                 # 采样点数据
├── output/figures/           # 输出图表
├── output/layouts/           # 输出布局
│
├── SKILL.md                  # Reasonix 技能定义
└── README.md                 # 本文件
```

## 数据

### 本地数据（D:\ArcGIS\）
```
D:\ArcGIS\中国1-5级河流...\全国河流、行政区域shp\
├── 一级河流hyd1_4m/      ← 长江主干+湖泊面
├── 二级河流hyd2_4m/      ← 较大支流
├── 四级河流hyd4_4m/      ← 小支流
├── 省界bou2_4m/          ← 省级边界
├── 国界bou1_4m/          ← 国界
└── 首都和省级行政中心res1_4m/  ← 城市点
```

### 在线数据（QuickOSM 插件）
```
插件 → QuickOSM → Key:boundary Value:administrative In:China
插件 → QuickOSM → Key:waterway Value:river In:China
```

## 在线底图（XYZ Tiles）

| 名称 | URL | 类型 |
|------|-----|------|
| 🛰️ **ESRI卫星** | `https://services.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer/tile/{z}/{y}/{x}` | 卫星影像 |
| 🗺️ **OSM标准** | `https://tile.openstreetmap.org/{z}/{x}/{y}.png` | 普通地图 |
| 🏔️ **ESRI地形** | `https://services.arcgisonline.com/ArcGIS/rest/services/World_Terrain_Base/MapServer/tile/{z}/{y}/{x}` | 地形图 |

## 配色方案（ColorBrewer）

| 图层 | 颜色 | 色号 | 线宽 |
|------|------|------|------|
| 一级河流 | 深蓝 | `#053061` | 2.8pt |
| 二级河流 | 中蓝 | `#2C7BB6` | 1.0pt |
| 四级河流 | 浅蓝 | `#80B8D8` | 0.3pt |
| 湖泊 | 浅蓝填充 | `#ABD9E9` | 50%透明 |
| 省界 | 灰色虚线 | `#999999` | 0.4pt |
| 国界 | 深灰实线 | `#333333` | 1.5pt |
| 采样点 | 红色 | `#D73027` | 3pt |

## 工作流

```
QGIS 打开 → XYZ Tiles 加载底图
  → 运行脚本加载数据（Python控制台）
  → 调整配色（手调或用 style 脚本）
  → 新建打印布局（A3横向）
  → 添加：地图框 + 标题 + 图例 + 比例尺 + 指北针
  → 导出：TIFF（出版）/ SVG（矢量）/ PNG
```

## 脚本说明

| 脚本 | 功能 | 运行方式 |
|------|------|---------|
| `yangtze_qgis.py` | 自动加载 shp + 基础配色 + 定位 | QGIS Python 控制台 |
| `yangtze_qgis_style.py` | 专业配色 + 打印布局 + 自动导出 | QGIS Python 控制台（先运行上面） |

## 中国地图规范

- ⚠️ 出版前须申请**审图号**（省级自然资源厅）
- ⚠️ 必须含**九段线**（南海诸岛）, 台湾标注正确
- ✅ 本地 shp 数据（D:\ArcGIS\）边界已合规
- ✅ QGIS 的 QuickOSM 数据来自 OpenStreetMap，边界可能不完整，建议用本地 shp
