<template>

    <el-container>
      <el-aside width="300px">
        <el-row class="tac">
          <el-col :span="12">
              <ul>
                <li class="p_item" v-for="(item,index) in items" :key="index">
                  <router-link :to="item.url" class="p_title" > 
                    <i class="iconfont" :class="item.icon"></i>{{item.title}}
                  </router-link>
                </li>
            </ul>
          </el-col>
        </el-row>
      </el-aside>
      <el-container>
        <el-header>
          <el-breadcrumb separator="/">
            <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
            <el-breadcrumb-item>
              <a href="/">活动管理</a>
            </el-breadcrumb-item>
            <el-breadcrumb-item>活动列表</el-breadcrumb-item>
            <el-breadcrumb-item>活动详情</el-breadcrumb-item>
          </el-breadcrumb>
        </el-header>
        <el-main>
          <router-view/>
        </el-main>
        <!---<el-footer>Footer</el-footer>-->
      </el-container>
    </el-container>
  
</template>

<script>
  
  export default {
    name:'index',
    methods: {
      tableRowClassName({row, rowIndex}) {
        if (rowIndex === 1) {
          return 'warning-row';
        } else if (rowIndex === 3) {
          return 'success-row';
        }
        return '';
      },
      handleOpen(key, keyPath) {
        console.log(key, keyPath);
      },
      handleClose(key, keyPath) {
        console.log(key, keyPath);
      }
    },
    data() {
      return {
        items:[
          {title:'首页',url:'/home',icon:'icon-jia'},
          {title:'新闻',url:'/news',icon:'icon-jiazheng'},
          {title:'列表',url:'/list',icon:'icon-jiajujiafang'},
          {title:'其它页',url:'/other',icon:'icon-xiaoyan'}
        ],
        tableData: [{
          date: '2016-05-02',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄',
        }, {
          date: '2016-05-04',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-01',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄',
        }, {
          date: '2016-05-03',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }]
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .el-table .warning-row {
    background: oldlace;
  }

  .el-table .success-row {
    background: #f0f9eb;
  }

  .active {
      color:#f60;
      background:#fff
		}
</style>
