<!--
 * @Author: your name
 * @Date: 2021-11-07 21:59:25
 * @LastEditTime: 2021-11-09 19:07:21
 * @LastEditors: Please set LastEditors
 * @Description: 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
 * @FilePath: \vue-admin-template\src\views\content\index.vue
-->
<template>
  <div>
      <el-link type="primary" :underline="false" icon="el-icon-back" @click="back">返回</el-link>
  </div>
</template>

<script>
export default {
  methods: {
    back() {
      this.$router.push('form')
    }
  }
}
</script>
