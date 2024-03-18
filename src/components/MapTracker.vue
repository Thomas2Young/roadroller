
<template>
  <div class="map-tracker component-container">
    <header class="app-header">
      <h1>车辆地图</h1>
    </header>
    <!-- 地图容器 -->
    <div id="map" style="width: 100%; height: 500px;"></div>
  </div>
</template>

<script>
/* global BMap */
export default {
  name: "MapTracker",
  mounted() {
    this.initMap();
  },
  methods: {
    initMap() {
      // 初始化地图
      var map = new BMap.Map("map");
      map.centerAndZoom(new BMap.Point(114.529963, 38.003679), 15); // 以石家庄铁路学院为中心
      map.enableScrollWheelZoom(true);

      // 车辆行驶的轨迹点
      var points = [
        new BMap.Point(114.529963, 38.003679),
        new BMap.Point(114.530963, 38.004679),
        // 添加更多点
      ];

      // 绘制轨迹
      var polyline = new BMap.Polyline(points, {strokeColor:"blue", strokeWeight:6, strokeOpacity:0.5});
      map.addOverlay(polyline);

      // 标记起点和终点
      var startMarker = new BMap.Marker(points[0]);
      var endMarker = new BMap.Marker(points[points.length - 1]);
      map.addOverlay(startMarker);
      map.addOverlay(endMarker);
    }
  }
};
</script>

<style>
/* 地图样式 */
#map { height: 400px; }
</style>
