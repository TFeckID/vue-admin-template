<!--
 * @Author: your name
 * @Date: 2021-11-07 20:51:50
 * @LastEditTime: 2022-01-19 16:20:45
 * @LastEditors: Please set LastEditors
 * @Description: 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
 * @FilePath: \vue-admin-template\src\views\form1\index.vue
-->
<template>
  <div class="app-container">

      <el-table
        :data="tableData"
        style="width:100%"
      >
        <el-table-column type="index" lable="序号"/>
        <el-table-column prop="date" label="日期" width="180">
          <template slot-scope="rowData">
            <span v-if="rowData.row.isEdit">
              <el-input v-model="rowData.row.date" size="mini">
                <el-button type="success" icon="el-icon-check" size="mini" slot="append"></el-button>
              </el-input>
            </span>
            <span v-else>{{ rowData.row.date }}</span>
          </template>
        </el-table-column>
        <el-table-column prop="name" label="姓名" width="180">
          <template slot-scope="rowData">
            <span v-if="rowData.row.isEdit">
              <el-input v-model="rowData.row.name" size="mini">
                <el-button type="success" icon="el-icon-check" size="mini" slot="append"></el-button>
              </el-input>
            </span>
            <span v-else>{{ rowData.row.name }}</span>
          </template>
        </el-table-column>
        <el-table-column prop="operation" label="操作" width="180">
            <template slot-scope="rowData">
                <el-link type="primary" :underline="false" @click="edit(rowData)">编辑</el-link>
            </template>
        </el-table-column>
      </el-table>
      <el-button type="primary" @click="goto">跳转</el-button>
      <el-slider v-model="value1"></el-slider>
      <br/>
      <el-date-picker
      v-model="value2"
      type="datetime"
      :time-arrow-control="true"
      placeholder="选择日期时间"/>
    <br/>
    <span>{{ value2 }}</span>

  </div>
</template>

<script>

export default {
  data() {
    return {
      tableData: [
        {
          date: '2020-01-01',
          name: '张三',
          isEdit: false
        },
        {
          date: '2020-01-01',
          name: '李四',
          isEdit: false
        }
      ],
      editingRowData: {},
      isEditStatus: false,
      editingRowIndex: -1,
      value1: 20,
      value2: ''
    }
  },
  methods: {
    edit(rowData) {
      console.log(rowData)
      this.editingRowData = rowData.row
      rowData.row.isEdit = !rowData.row.isEdit
    },
    drawerHandlerClose() {
      this.isEditStatus = false
    },
    goto() {
      this.$router.push('content')
    }
  }

}
</script>

<style scoped>

</style>
