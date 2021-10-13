<template>
  <div class="dashboard-editor-container">
    <github-corner class="github-corner" />

    <panel-group @handleSetLineChartData="handleSetLineChartData" />

    <el-row style="background: #fff; padding: 16px 16px 0; margin-bottom: 32px">
      <bar-chart ref="barch" />
    </el-row>

    <el-row :gutter="32">
      <el-col :xs="24" :sm="24" :lg="8">
        <div class="chart-wrapper">
          <raddar-chart />
        </div>
      </el-col>
      <el-col :xs="24" :sm="24" :lg="8">
        <div class="chart-wrapper">
          <line-chart :chart-data="lineChartData" />
        </div>
      </el-col>
      <el-col :xs="24" :sm="24" :lg="8">
        <div class="chart-wrapper">
          <pie-chart />
        </div>
      </el-col>
    </el-row>

    <el-row :gutter="8">
      <el-col
        :xs="{ span: 24 }"
        :sm="{ span: 24 }"
        :md="{ span: 24 }"
        :lg="{ span: 12 }"
        :xl="{ span: 12 }"
        style="padding-right: 8px; margin-bottom: 30px"
      >
        <transaction-table />
      </el-col>
      <el-col
        :xs="{ span: 24 }"
        :sm="{ span: 12 }"
        :md="{ span: 12 }"
        :lg="{ span: 6 }"
        :xl="{ span: 6 }"
        style="margin-bottom: 30px"
      >
        <todo-list />
      </el-col>
      <el-col
        :xs="{ span: 24 }"
        :sm="{ span: 12 }"
        :md="{ span: 12 }"
        :lg="{ span: 6 }"
        :xl="{ span: 6 }"
        style="margin-bottom: 30px"
      >
        <box-card />
      </el-col>
    </el-row>
  </div>
</template>

<script>
import GithubCorner from '@/components/GithubCorner'
import PanelGroup from './components/PanelGroup'
import LineChart from './components/LineChart'
import RaddarChart from './components/RaddarChart'
import PieChart from './components/PieChart'
import BarChart from './components/BarChart'
import TransactionTable from './components/TransactionTable'
import TodoList from './components/TodoList'
import BoxCard from './components/BoxCard'

const animationDuration = 6000
const lineChartData = {
  newVisitis: {
    expectedData: [100, 120, 161, 134, 105, 160, 165],
    actualData: [120, 82, 91, 154, 162, 140, 145]
  },
  messages: {
    expectedData: [200, 192, 120, 144, 160, 130, 140],
    actualData: [180, 160, 151, 106, 145, 150, 130]
  },
  purchases: {
    expectedData: [80, 100, 121, 104, 105, 90, 100],
    actualData: [120, 90, 100, 138, 142, 130, 130]
  },
  shoppings: {
    expectedData: [130, 140, 141, 142, 145, 150, 160],
    actualData: [120, 82, 91, 154, 162, 140, 130]
  }
}

const barchat = {
  newVisitis: [
    {
      name: 'pageA',
      type: 'bar',
      stack: 'vistors',
      barWidth: '40%',
      data: [79, 52, 200, 334, 390, 330, 220],
      animationDuration
    },
    {
      name: 'pageB',
      type: 'bar',
      stack: 'vistors',
      barWidth: '40%',
      data: [80, 52, 200, 334, 390, 330, 220],
      animationDuration
    },
    {
      name: 'pageC',
      type: 'bar',
      stack: 'vistors',
      barWidth: '40%',
      data: [30, 52, 200, 334, 390, 330, 220],
      animationDuration
    }
  ],
  messages: [
    {
      name: 'pageA',
      type: 'bar',
      stack: 'vistors',
      barWidth: '40%',
      data: [12, 44, 45, 55, 172, 221, 239],
      animationDuration
    },
    {
      name: 'pageB',
      type: 'bar',
      stack: 'vistors',
      barWidth: '40%',
      data: [34, 55, 77, 84, 229, 330, 410],
      animationDuration
    },
    {
      name: 'pageC',
      type: 'bar',
      stack: 'vistors',
      barWidth: '40%',
      data: [51, 52, 56, 88, 260, 330, 550],
      animationDuration
    }
  ],
  purchases: [
    {
      name: 'pageA',
      type: 'bar',
      stack: 'vistors',
      barWidth: '40%',
      data: [12, 89, 54, 84, 33, 221, 440],
      animationDuration
    },
    {
      name: 'pageB',
      type: 'bar',
      stack: 'vistors',
      barWidth: '40%',
      data: [65, 88, 22, 1, 78, 45, 327],
      animationDuration
    },
    {
      name: 'pageC',
      type: 'bar',
      stack: 'vistors',
      barWidth: '40%',
      data: [67, 12, 34, 67, 230, 310, 550],
      animationDuration
    }
  ],
  shoppings: [
    {
      name: 'pageA',
      type: 'bar',
      stack: 'vistors',
      barWidth: '40%',
      data: [2, 44, 51, 84, 90, 234, 341],
      animationDuration
    },
    {
      name: 'pageB',
      type: 'bar',
      stack: 'vistors',
      barWidth: '40%',
      data: [90, 46, 52, 135, 77, 3, 61],
      animationDuration
    },
    {
      name: 'pageC',
      type: 'bar',
      stack: 'vistors',
      barWidth: '40%',
      data: [67, 12, 34, 67, 230, 310, 643],
      animationDuration
    }
  ]
}
export default {
  name: 'DashboardAdmin',
  components: {
    GithubCorner,
    PanelGroup,
    LineChart,
    RaddarChart,
    PieChart,
    BarChart,
    TransactionTable,
    TodoList,
    BoxCard
  },
  data() {
    return {
      lineChartData: lineChartData.newVisitis,
      barchat: barchat.newVisitis
    }
  },
  methods: {
    async handleSetLineChartData(type) {
      this.lineChartData = lineChartData[type]
      // this.barchat = barchat[type];
      // console.log(this.$refs.barch.datas)
      this.$refs.barch.datas = barchat[type]
      // this.$refs.barch.datas.initChart()
    }
  }
}
</script>

<style lang="scss" scoped>
.dashboard-editor-container {
  padding: 32px;
  background-color: rgb(240, 242, 245);
  position: relative;

  .github-corner {
    position: absolute;
    top: 0px;
    border: 0;
    right: 0;
  }

  .chart-wrapper {
    background: #fff;
    padding: 16px 16px 0;
    margin-bottom: 32px;
  }
}

@media (max-width: 1024px) {
  .chart-wrapper {
    padding: 8px;
  }
}
</style>
