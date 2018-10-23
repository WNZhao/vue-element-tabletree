<template>
  <div class="hello">
     <table-tree :colums="dColums" :datas="datas"></table-tree>
  </div>
</template>

<script>
import TableTree from './tabletree/TableTree'

const columns = [{
  treeNode: true,
  _props: {
    key: 'name',
    prop: 'name',
    label: '姓名',
    headerAlign: 'center',
    align: 'center'
  }

}, {
  _props: {
    label: '日期',
    key: 'date',
    prop: 'date',
    headerAlign: 'center',
    align: 'center'
  }
}, {
  _props: {
    label: '地址',
    key: 'address',
    prop: 'address',
    headerAlign: 'center'
  }
}]

const datas = [{
  date: '2016-05-02',
  name: '王小虎',
  align: 'center',
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

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      dColums: columns,
      datas: datas
    }
  },
  components: {
    TableTree
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.hello{
    width: 1024px;
    margin: auto
}
</style>
