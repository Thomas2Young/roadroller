<template>
  <div class="roller-list component-container">
    <header class="app-header">
      <h1>压路机列表</h1>
    </header>
    <table>
      <thead>
        <tr>
          <th>压路机名称</th>
          <th>上线时间</th>
          <th>下线时间</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="roller in rollers" :key="roller.id" :class="{ 'online': roller.isOnline }">
          <td>{{ roller.name }}</td>
          <td>{{ roller.onlineTime }}</td>
          <td>{{ roller.offlineTime }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'RollerList',
  data() {
    return {
      // 假设数据
      rollers: [
        { id: 1, name: '压路机A', onlineTime: '08:00', offlineTime: '17:00', isOnline: true },
        // ...其他数据
      ]
    };
  }
}
</script>

<style>
.roller-list table {
  width: 100%;
  /* 其他表格样式 */
}
.roller-list .online {
  background-color: green;
}
.roller-list .offline {
  background-color: gray;
}
/* 添加更多样式 */
</style>
