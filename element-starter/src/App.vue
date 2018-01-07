<template>
  <div>
  <el-checkbox :indeterminate="isIndeterminate" v-model="checkAll" @change="handleCheckAllChange">全选</el-checkbox>
  <el-button @click="xxx">xxxx</el-button>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        checkAll: false
      };
    },
    methods: {
      handleCheckAllChange(val) {
        alert("xxxx");
      },
      xxx() {
        this.checkAll=false
      }
    }
  };
</script>