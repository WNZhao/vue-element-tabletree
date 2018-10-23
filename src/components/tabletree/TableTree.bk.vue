<template>
  <el-table
    :data="datas"
    border
    style="width: 100%">
   <template v-for="(col) in colums">
       <el-table-column
           :key="col.key"
           :prop="col.prop"
           :label="col.label+col.prop"
           :headerAlign="col.headerAlign"
           :align="col.align?col.align:'center'"></el-table-column>
   </template>
  </el-table>
</template>

<script>
export default {
  name: 'table-tree',
  props: ['colums', 'datas'],
  data () {
    return {
      tableData: [{
        date: '2016-05-02',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1518 弄'
      }, {
        date: '2016-05-04',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1517 弄'
      }, {
        date: '2016-05-01',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1519 弄'
      }, {
        date: '2016-05-03',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1516 弄'
      }]
    }
  }
}
</script>
