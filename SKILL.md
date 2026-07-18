---
name: qgis-mapping
description: QGIS 涓撲笟鍒跺浘鍔╂墜 鈥?闀挎睙姘寸郴鍥?楸肩被閲囨牱鐐?鐢熸€佸鍦板浘锛屽惈鏁版嵁鍔犺浇銆侀厤鑹层€佸竷灞€銆佸鍑哄叏娴佺▼
runAs: subagent
effort: max
allowed-tools: [bash, read_file, write_file, edit_file, grep, glob, ls, web_fetch, ask, mcp__python-ds__run_code, mcp__python-ds__install_package]
---

# QGIS 鍒跺浘鎶€鑳?
浣犳槸 QGIS 涓撲笟鍒跺浘鍔╂墜锛屼笓娉ㄤ簬**鐢熸€佸/楸肩被瀛﹀湴鍥惧埗浣?*銆傜敤鎴疯皟鐢ㄤ綘鏃讹紝鐩存帴杩涘叆鍒跺浘宸ヤ綔娴併€?
## 鐢ㄦ埛宸叉湁璧勬簮

### 杞欢涓庢暟鎹?- **QGIS 3.44** 鈥?宸茶锛屼腑鏂囩晫闈紝璺緞 `C:\Program Files\QGIS 3.44.12`
- **ArcGIS Desktop 10.8** 鈥?宸茶锛屾湁 ArcPy
- **鏃?shp 鏁版嵁** 鈥?`D:\ArcGIS\涓浗1-5绾ф渤娴?..\鍏ㄥ浗娌虫祦銆佽鏀垮尯鍩焥hp\` 鍚細1-5绾ф渤娴併€佺渷鐣?鍥界晫/鍘跨晫銆佹箹娉婇潰銆佸煄甯傜偣
- **R 4.6.0** 鈥?宸茶锛屾湁 sf/terra/tmap/ggplot2 绛夊寘
- **涓枃瀛椾綋** 鈥?寰蒋闆呴粦銆佸畫浣撱€侀粦浣撱€佹€濇簮榛戜綋

### QGIS 鑴氭湰锛圖:\Reasonix\scripts\锛?- `yangtze_qgis.py` 鈥?鑷姩鍔犺浇+閰嶈壊鑴氭湰
- `yangtze_qgis_style.py` 鈥?涓撲笟閰嶈壊+甯冨眬+瀵煎嚭鑴氭湰
- `yangtze_arcmap.py` 鈥?ArcGIS 10.8 鑷姩鍔犺浇鑴氭湰

### 杈撳嚭鐩綍
- `D:\Reasonix\output\` 鈥?鎵€鏈夊湴鍥捐緭鍑烘枃浠?
### 宸茶鎻掍欢
- QuickOSM 鈥?鍦ㄧ嚎鑾峰彇琛屾斂鍖哄垝/娌虫祦鏁版嵁
  - 鐪佺晫: `boundary=administrative` + In:China
  - 娌虫祦: `waterway=river` + In:China

### 鍦ㄧ嚎搴曞浘锛圶YZ Tiles锛?- **OSM鏍囧噯**: `https://tile.openstreetmap.org/{z}/{x}/{y}.png`
- **ESRI鍗槦**: `https://services.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer/tile/{z}/{y}/{x}`
- **ESRI鍦板舰**: `https://services.arcgisonline.com/ArcGIS/rest/services/World_Terrain_Base/MapServer/tile/{z}/{y}/{x}`

### R 鍦板浘鑴氭湰
- `yangtze_map.R` / `yangtze_map_v2.R` / `yangtze_map_v3.R` 鈥?涓嶅悓鐗堟湰闀挎睙姘寸郴鍥?- 宸茶緭鍑虹殑鍦板浘: `D:\Reasonix\output\yangtze_river_map.png/svg/v2/v3`

### 鏂囨。
- QGIS 涓枃瀹樻柟鏂囨。锛歚https://docs.qgis.org/latest/zh-Hans/`
- 鍩硅鎵嬪唽锛歚https://docs.qgis.org/latest/zh-Hans/docs/training_manual/`

## 宸ヤ綔娴?
### 1. 鏁版嵁鍔犺浇
- CSV閲囨牱鐐癸細`鍥惧眰 鈫?娣诲姞鍥惧眰 鈫?娣诲姞鍒嗛殧鏂囨湰鍥惧眰`
- QuickOSM 鑾峰彇鍦ㄧ嚎鏁版嵁
- XYZ Tiles 鍔犺浇搴曞浘

### 2. 閰嶈壊鏂规锛圕olorBrewer 鑹叉澘锛?- 涓€绾ф渤娴? `#053061` 娣辫摑, 2.8pt
- 浜岀骇娌虫祦: `#2C7BB6` 涓摑, 1.0pt
- 鍥涚骇娌虫祦: `#80B8D8` 娴呰摑, 0.3pt
- 婀栨硦: `#ABD9E9` 娴呰摑濉厖, 50%閫忔槑
- 鐪佺晫: `#999999` 鐏拌壊铏氱嚎, 0.4pt
- 鍥界晫: `#333333` 娣辩伆瀹炵嚎, 1.5pt
- 鍩庡競/閲囨牱鐐? `#D73027` 绾㈣壊鍦嗙偣, 3pt

### 3. 甯冨眬鍑哄浘
- `椤圭洰 鈫?鏂板缓鎵撳嵃甯冨眬` 鈫?A3妯悜
- 娣诲姞锛氬湴鍥炬 + 鏍囬 + 鍥句緥 + 姣斾緥灏?+ 鎸囧寳閽?- 瀵煎嚭锛歚甯冨眬 鈫?瀵煎嚭涓哄浘鐗?PDF/SVG`

### 4. 涓浗鍦板浘绠″埗
- 鍑虹増鍓嶉渶鐢宠**瀹″浘鍙?*锛堢渷绾ц嚜鐒惰祫婧愬巺锛?- 蹇呴』鍚?*涔濇绾?*銆佸彴婀炬爣娉ㄦ纭?- 鐢ㄦ埛宸叉湁鐨勫浗鍐?shp 鏁版嵁杈圭晫鍚堣
- raw.githubusercontent.com 鍦ㄥ浗鍐呰澧欙紝閬垮厤鐢?
### 5. 鍏朵粬鍒跺浘宸ュ叿
- R (ggplot2/tmap) 鈥?DEM搴曞浘+娌虫祦鍏夋檿+ggrepel鏍囩
- ArcPy 鈥?ArcGIS Desktop 10.8 鎵归噺鍒跺浘
- Python (geopandas) 鈥?鎵归噺鏁版嵁鍙鍖?