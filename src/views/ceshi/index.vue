<template>
  <div>
    <div style="margin:30px 0px 0px 30px">
      <el-row>
        <el-button @click="setceshitoken">加测试token</el-button>
        <el-button type="primary" @click="ceshitokenremove">清除测试token</el-button>

      </el-row>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      ceshitoken: "Brkalkfkkajsbdoih1llnkxhclasiwella;sdljljsdciuha",
    };
  },
  methods: {
    setceshitoken() {
      sessionStorage.setItem("ceshi", this.ceshitoken);
    },
    ceshitokenremove() {
      sessionStorage.removeItem("ceshi");
    },
  },
  mounted() {
    //挂载后
  },
};
</script>

<style>
</style>
