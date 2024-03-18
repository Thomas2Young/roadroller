<template>
  <div class="vibration-ratio component-container">
    <header class="app-header">
      <h1>碾压开振比</h1>
    </header>
    <!-- 进度条容器 -->
    <label for="vibrationProgress">开振比：</label>
    <progress id="vibrationProgress" value="32" max="100"></progress> <!-- 示例数值 -->
  </div>
</template>

<script>
export default {
  name: 'VibrationRatio',
  data() {
    return {
      vibrationRatio: 0
    };
  },
  methods: {
    fetchVibrationRatio() {
      // 获取开振比数据的逻辑
      this.vibrationRatio =0.52
    }
  }
}
</script>

<style>
/* 样式 */
</style>
