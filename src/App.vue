<template>
  <header class="app-header">
      <h1>主界面</h1>
    </header>
  <div class="grid-container">
    
    <!-- 左侧上方组件 -->
    <roller-list class="grid-roller-list" />
    
    <!-- 左侧下方组件 -->
    <construction-area class="grid-construction-area" />
    
    <!-- 右侧上方跨两列的组件 -->
    <map-tracker class="grid-map-tracker" />
    
    <!-- 右侧下方两个组件 -->
    <roll-frequency class="grid-roll-frequency" />
    <vibration-ratio class="grid-vibration-ratio" />
  </div>
</template>

<script>
import RollerList from './components/RollerList.vue';
import ConstructionArea from './components/ConstructionArea.vue';
import MapTracker from './components/MapTracker.vue';
import RollFrequency from './components/RollFrequency.vue';
import VibrationRatio from './components/VibrationRatio.vue';

export default {
  components: {
    RollerList,
    ConstructionArea,
    MapTracker,
    RollFrequency,
    VibrationRatio
  }
}
</script>

<style>
.grid-container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr; /* 三列 */
  grid-template-rows: auto 1fr 1fr; /* Updated for the header row */
  gap: 10px;
  padding: 10px;
}
.app-header {
  grid-column: 1 / -1; /* The header spans all columns */
  text-align: center;
}
.component-container {
  border: 1px solid #ccc; /* Example border */
  border-radius: 4px; /* Optional for rounded corners */
  padding: 10px;
}

.grid-roller-list {
  grid-area: 1 / 1 / 2 / 2;
}

.grid-construction-area {
  grid-area: 2 / 1 / 3 / 2;
}

.grid-map-tracker {
  grid-area: 1 / 2 / 2 / 4;
}

.grid-roll-frequency {
  grid-area: 2 / 2 / 3 / 3;
}

.grid-vibration-ratio {
  grid-area: 2 / 3 / 3 / 4;
}
</style>
