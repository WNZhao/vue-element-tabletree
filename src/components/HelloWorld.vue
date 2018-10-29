<template>
  <div class="hello">
     <tree-table :data="tDatas" :columns="columns"></tree-table>
  </div>
</template>

<script>
import TreeTable from './tabletree/index'

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      tDatas: [{
        key: 1,
        name: 'John Brown sr.',
        age: 60,
        address: 'New York No. 1 Lake Park',
        children: [
          {
            key: 12,
            name: 'John Brown jr.',
            age: 30,
            address: 'New York No. 3 Lake Park',
            children: [{
              key: 121,
              name: 'Jimmy Brown',
              age: 16,
              address: 'New York No. 3 Lake Park'
            }]
          }, {
            key: 11,
            name: 'John Brown',
            age: 42,
            address: 'New York No. 2 Lake Park'
          }, {
            key: 13,
            name: 'Jim Green sr.',
            age: 72,
            address: 'London No. 1 Lake Park',
            children: [{
              key: 131,
              name: 'Jim Green',
              age: 42,
              address: 'London No. 2 Lake Park',
              children: [{
                key: 1311,
                name: 'Jim Green jr.',
                age: 25,
                address: 'London No. 3 Lake Park'
              }, {
                key: 1312,
                name: 'Jimmy Green sr.',
                age: 18,
                address: 'London No. 4 Lake Park'
              }]
            }]
          }]
      }, {
        key: 2,
        name: 'Joe Black',
        age: 32,
        address: 'Sidney No. 1 Lake Park'
      }],
      columns: [
        {'text': '姓名', 'value': 'name', 'width': 200},
        {'text': '年龄', 'value': 'age', 'width': 100},
        {'text': '地址', 'value': 'address'}
      ]
    }
  },
  components: {
    TreeTable
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
