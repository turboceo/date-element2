<template>
  <div id="app">
    <div class="date-list">
      <div class="date-item" v-for="(date, $index) in dateList" :key="$index">
        <date-table :date="new Date(date)"></date-table>
      </div>
    </div>
  </div>
</template>

<script>
import DateTable from "element-ui/packages/date-picker/src/basic/date-table.vue";

export default {
  name: "App",
  components: {
    DateTable,
  },

  data() {
    return {
      dateList: [
        "2023-01-01",
        "2023-02-01",
        "2023-03-01",
        "2023-04-01",
        "2023-05-01",
        "2023-06-01",
        "2023-07-01",
        "2023-08-01",
        "2023-09-01",
        "2023-10-01",
        "2023-11-01",
        "2023-12-01",
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.date-list {
  display: flex;
  flex-wrap: wrap;
}

.date-item {
  flex: 0 0 25%;
  padding: 10px;
  box-sizing: border-box;
  // background: rgba(153, 228, 253, 0.557);
  display: flex;
  justify-content: center;
}
</style>
