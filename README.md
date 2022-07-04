6/27 Github学习 
=
1、向github上传本地项目文件： 
#
1)创建数据仓库 注：private最多五个人看，多了受限制 
##
2)初始化本地仓库：git init （成功后项目文件夹下会出现.git文件）
##
3)git add . 
##
4)检查是否有别名：git remote -v 
##
5）创建别名：git remote add 别名 
##
6）提交说明：git commit add “说明”
##
7）建立远程连接：git remote add 别名 http版url 
##
8)上传项目文件：git push 别名 分支名（master） 
##
2、克隆远程仓库到本地： 
#
1)git clone http的url (拉取代码、初始化本地仓库、创建别名) 
##
3、团队协作：
#
1）进入自己创建的仓库，找到设置，添加团队成员
##
6/28
=
梳理starlink项目文件夹，但是代码无法看懂，其中的变量命名不可读，代码中加载的本地数据不可获取
##
6/29 
=
1、梳理satvis项目文件，标注项目功能的具体代码，条件控制代码 
#
2、思考如何将星历数据一次性展示在界面上 
#
3、考虑将原有的功能注释，直接让项目读取.txt的星历文件，并且以点的形式展现在页面上，根据不同类型卫星特点，统一设置条件控制卫星在页面显示的颜色
#
6/30
==
7/4
==
# starlink.sx  websites localization

## 1. download everything
  wget -r -p -np -k https://starlink.sx
  or save the page (everything)

## 2. create nodejs http server
  add index.js
  create public folder, change name to index.html
  node index.js

## 3. replenish shortage files from starlink.sx
  failedsats.json, gateways.json, ip.php, launched.json, starlink_supplemental.txt, starlink.txt

## 4. note: public folder setting
  set the public folder as my project!
  
## 5. download starlink.txt and starlink_supllymental.txt
  http://www.celestrak.com/NORAD/elements/gp.php?GROUP=starlink&FORMAT=tle
  http://www.celestrak.com/NORAD/elements/supplemental/starlink.txt
  
## 6. satbeam网站里的EIRP等高线都是图片，并不是想象中的svg画的线
  https://satbeams.com/footprints
7.index.e5e2695f.js文件分析
==
<!-- 1.React文件引用  @license React v17.0.2  构建界面的javascript库-->
react-jsx-runtime.production.min.js  
react.production.min.js
react-dom.production.min.js
../render/Event.js
<!-- 2.@license React v0.20.2  React调度文件 -->
scheduler.production.min.js
<!-- 3.jQuery JavaScript Library v3.6.0 -->
jQuery JavaScript Library v3.6.0
https://jquery.com/
<!-- 4.Includes Sizzle.js -->
https://sizzlejs.com/
<!-- 5. Vector3d 三维空间中的点或位置 -->
vector3d.js
<!-- 6.  -->
https://github.com/mapbox/mapbox-gl-js/blob/001c7b9/js/ui/handler/scroll_zoom.js
<!-- 7.geodesy  https://github.com/chrisveness/geodesy
JS大地测量库，对大地椭球体表面点进行运算 -->
'/js/geodesy/latlon-ellipsoidal.js'
import LatLon, { Dms } from '../latlon-ellipsoidal-vincenty.js';
import { datums }   from '../latlon-ellipsoidal-datum.js';
<!-- 8.三角洲归一化灵感来源 -->
https://github.com/mapbox/mapbox-gl-js/blob/001c7b9/js/ui/handler/scroll_zoom.js
<!-- 9.OpenLayers    https://openlayers.org/      https://openlayers.org/en/latest/apidoc/module-ol_VectorTile-VectorTile.html -->
PluggableMap.js
coordinate.js     <!--获取地图地理坐标-->
MapBrowserEvent.js
extent.js
../source/Source.js
../render/Event.js
./Fill.js
./Stroke.js
../colorlike.js
../geom/Geometry.js  <!--抽象的基础类，创建子类的时候使用>
../source/Vector.js   <!--提供矢量图-->
../source/VectorTile.js  <!--支持矢量瓦片-->
../geom/SimpleGeometry.js  <!--  -->
../../geom/MultiPolygon.js
../../geom/LineString.js
../../geom/Circle.js
../proj/Projection.js
../tilecoord.js
../tilegrid/TileGrid.js
../featureloader.js
../format/Feature.js
./interaction/Interaction.js   <!-- 地球数据交互可视化 -->
./Overlay.js    <!--地图覆盖物-->
./renderer/Map.js    <!--渲染地图-->
./WMSServerType.js
<!-- 10.Layer.js  H-ui前端框架，弹出层-->
Layer.js
<!-- 11. ../size.js 获取浏览器和元素size-->
../size.js
<!-- 12.Feature.js   轻量级的浏览器特性检测JavaScript库插件 -->
https://github.com/viljamis/feature.js
../Feature.js
<!-- 13.ol-contextmenu - v4.1.0 -->
<!-- 14.satellite-js v4.1.3 -->
<!-- 15.Sizzle CSS Selector Engine v2.3.6 -->
<!-- 16.D3.js   (https://d3js.org/) -->

