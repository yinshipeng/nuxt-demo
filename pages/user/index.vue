<template>
    <div>
        <el-table
                :data="tableData"
                border
                style="width: 100%">
            <el-table-column
                    prop="id"
                    label="ID"
                    width="100">
            </el-table-column>
            <el-table-column
                    prop="title"
                    label="Title"
                    width="180">
            </el-table-column>
            <el-table-column
                    prop="desc"
                    label="Desc"
                    width="180">
            </el-table-column>
            <el-table-column
                    prop="views"
                    label="Views"
                    width="180">
            </el-table-column>
            <el-table-column
                    prop="images"
                    label="Images">
            </el-table-column>
        </el-table>
    </div>
</template>
<script>
    import axios from 'axios'
    import UserMiddleware from '../../middleware/user-middleware'
    export default{
      data () {
        return {
          msg: 'hello vue',
          name: '22',
          tableData: []
        }
      },
      asyncData (context) {
        console.log(1111)
        console.log(context)
        return axios.get('http://127.0.0.1:4000/news').then(res => {
          console.log(res)
          return {tableData: res.data}
        })
    //            return {name:'哈哈'}
      },
      fetch ({ store, params }) {
        // 设置store
      }
//        middleware: [UserMiddleware]
    }
</script>
<style>
</style>
