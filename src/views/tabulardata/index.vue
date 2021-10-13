<template>
  <div class="heads">
    <template>
      <el-table :data="tableData" border style="width: 100%">
        <el-table-column fixed prop="date" label="日期" />
        <el-table-column prop="name" label="姓名" />
        <el-table-column prop="province" label="省份" />
        <el-table-column prop="city" label="市区" />
        <el-table-column prop="address" label="地址" />
        <el-table-column prop="zip" label="邮编" />
        <el-table-column fixed="right" label="操作">
          <template slot-scope="scope">
            <el-button
              type="text"
              size="small"
              @click="handleClick(scope.row)"
            >查看456</el-button>
            <el-button type="text" size="small">编辑123</el-button>
          </template>
        </el-table-column>
      </el-table>
    </template>
    <div class="pagin">
      <el-pagination background layout="prev, pager, next" :total="1000" />
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      tableData: []
    }
  },
  mounted() {
    for (let i = 0; i < 20; i++) {
      this.tableData.push({
        date: '2016-05-02',
        name: '王小虎',
        province: '上海',
        city: '普陀区',
        address: '上海市普陀区金沙江路 1518 弄',
        zip: 200333
      })
    }
  },
  methods: {
    handleClick(row) {
      console.log(row)
    }
  }
}
</script>
<style lang="scss" scope>
.heads {
  width: 95%;
  margin-left: 2.5%;
  margin-top: 1%;

  margin-bottom: 1%;
  .pagin{
    margin: 1% 0;
  }
}
</style>
