
<script>
export default {
  name: 'table-tree',
  props: ['colums', 'datas'],
  data () {
    return {
      testData: [{
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
      }]
    }
  },
  methods: {
    formatter (row, column, cellValue, index) {
      return <span>{cellValue}</span>
    },
    flatTreeData (data = [], level = 0, mapDatas = [], parentName = '') {
      data.forEach(element => {
        /* let space = (level === 0 && element.children) ? '+' : ' '
        for (let i = 0; i < level; i++) {
          space += '\t'
        } */
        mapDatas.push(Object.assign({}, element, {name: element.name, level: level, isParent: !!element.children, parentName: parentName}))
        console.log(element.name, level)
        if (element.children) {
          this.flatTreeData(element.children, level + 1, mapDatas, element.name)
        }
      })
    }
  },
  render () {
    const {colums, formatter} = this
    /* const cols = colums.map((item, idx, arr) => {
      if (item.treeNode) {
        return <el-table-column {...{props: item._props}} formatter={formatter}></el-table-column>
      } else {
        return <el-table-column {...{props: item._props}}></el-table-column>
      }
    }) */

    let flatData = []
    this.flatTreeData(this.testData, 0, flatData)
    const cols = colums.map((item, idx, arr) => {
      if (item.treeNode) {
        return <el-table-column {...{props: item._props}} formatter={formatter}></el-table-column>
      } else {
        return <el-table-column {...{props: item._props}}></el-table-column>
      }
    })
    return <el-table
      border
      style="width: 100%" {...{props: {data: flatData}}}>
      {cols}
    </el-table>
  }
}
</script>
<style scoped>
  .white-placeholder{
      display:
  }
</style>
