<template>
<div>
<div class="block">
  <span class="demonstration">默认 click 触发子菜单</span>
  <el-cascader
    :options="options"
    v-model="selectedOptions"
    @change="handleChange">
  </el-cascader>
</div>
<div class="block">
  <span class="demonstration">hover 触发子菜单</span>
  <el-cascader
    expand-trigger="hover"
    :options="options"
    v-model="selectedOptions2"
    @change="handleChange">
  </el-cascader>
</div>
</div>
</template>
<script>
  export default {
    data () {
      return {
        pickerOptions1: {
          disabledDate (time) {
            return time.getTime() > Date.now()
          },
          shortcuts: [{
            text: '今天',
            onClick (picker) {
              picker.$emit('pick', new Date())
            }
          }, {
            text: '昨天',
            onClick (picker) {
              const date = new Date()
              date.setTime(date.getTime() - 3600 * 1000 * 24)
              picker.$emit('pick', date)
            }
          }, {
            text: '一周前',
            onClick (picker) {
              const date = new Date()
              date.setTime(date.getTime() - 3600 * 1000 * 24 * 7)
              picker.$emit('pick', date)
            }
          }]
        },
        value1: '',
        value2: ''
      }
    }
  }
</script>