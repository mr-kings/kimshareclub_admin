<template>
  <div class="home">
    <el-container>
      <el-header class="header">
        <Header></Header>
      </el-header>
      <el-container>
        <el-aside v-bind:style="{ width: siderWidth + 'px' }" class="sider">
          <SideBar @siderOpen="siderWidthChange"></SideBar>
        </el-aside>
        <el-main class="main">
          <el-button type="primary">{{$t('dashboard.primaryBtn')}}</el-button>
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script>
  import Header from '@/components/header';
  import SideBar from '@/components/sideBar';
  export default {
    components: {
      Header,
      SideBar
    },
    data() {
      return {
        siderWidth: 200,
      };
    },
    created() {

    },
    methods: {
      siderWidthChange(isCollapse) {
        if(isCollapse){
          this.siderWidth = 65;
        }else{
          this.siderWidth = 200;
        }
      },
      // apiTest(){
      //   this.$http.get('/').then(res => {
      //     console.log(res)
      //   })
      // }
    },
    events: {
      // siderWidthChange: function(isCollapse) {
      //   if(isCollapse){
      //     this.siderWidth = 65;
      //   }else{
      //     this.siderWidth = 200;
      //   }
      // }
    }
  }
</script>

<style lang="scss" scoped>
  .header{
    background-color: rgb(84, 92, 100);
    overflow: hidden;
  }
</style>
