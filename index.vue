<template>
  <div class="bar">
    <el-button type="default" v-on:click="print">获取表格数据</el-button>
    <el-button type="primary" v-on:click="add">添加一条</el-button>
    <el-table
      :data="tableData3"
      highlight-current-row
      @current-change="handleCurrentChange"
      height="250"
      border>
      <el-table-column
        inline-template
        label="日期">
        <div>
          <el-input
            :value="row.date"
            v-model="input">
          </el-input>
        </div>
      </el-table-column>
      <el-table-column
        prop="name"
        label="姓名">
      </el-table-column>
      <el-table-column
        prop="address"
        label="地址">
      </el-table-column>
    </el-table>
  </div>

</template>

<script>
  export default {
    data() {
      return {
        tableData3: [{
          date: '2016-05-03',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-02',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-04',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-01',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-08',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-06',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-07',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }]
      }
    },
    methods: {
      handleCurrentChange(val) {
        this.currentRow = val;
        console.log(val.date,val.name,val.address)
      },
      add(){
        var _data ={
          date: '',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }
        this.tableData3.push(_data);
      },
      print(){
        console.log(this.tableData3)
      }
    }
  }
</script>

<style>
  .bar{
    width: 80%;
    margin: 16px auto;
  }
  .bar button{
    margin-bottom: 8px;
    float: right;
  }
  .bar button:first-child{
      margin-left: 4px;
  }
</style>