<template>
  <div id="app">
    <div class="page-header">
      <el-button type="primary" @click="pushDate">产生新的日期</el-button>
    </div>
    <div class="date-list">
      <div class="date-item" v-for="(date, $index) in dateList" :key="$index">
        <pyzl-date-table
          :date="new Date(date)"
          :event-dates="eventDates"
          :key="renderKey"
        ></pyzl-date-table>
      </div>
    </div>
  </div>
</template>

<script>
import PyzlDateTable from "./components/PyzlDateTable.vue";

export default {
  name: "App",
  components: {
    PyzlDateTable,
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

      eventDates: ["2023-05-10"],

      renderKey: Date.now(),

      count: 0,
    };
  },

  methods: {
    refreshRenderKey() {
      console.log("refresh render key:");
      this.renderKey = Date.now();
    },

    pushDate() {
      if (this.count === 0) {
        this.count++;
        this.eventDates = this.eventDates.concat([
          "2023-04-01",
          "2023-01-01",
          "2023-01-02",
        ]);
        return;
      }
      if (this.count === 1) {
        this.count++;
        this.eventDates = this.eventDates.concat(["2023-08-01", "2023-09-15"]);
        return;
      }
      if (this.count === 2) {
        this.count++;
        this.eventDates = this.eventDates.concat(["2023-06-01", "2023-07-13"]);
        return;
      }
      if (this.count === 3) {
        this.count = 0;
        this.eventDates = [];
        return;
      }
      // this.refreshRenderKey();
    },
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
