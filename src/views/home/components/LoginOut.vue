<template>
  <div id="loginOut">
    <el-avatar :size="40" :src="circleUrl"></el-avatar>
    <el-dropdown trigger="click"  @command="loginOut">
      <span class="el-dropdown-link">
        admin<i class="el-icon-arrow-down el-icon--right"></i>
      </span>
      <el-dropdown-menu slot="dropdown">
        <el-dropdown-item>个人信息</el-dropdown-item>
        <el-dropdown-item>安全中心</el-dropdown-item>
        <el-dropdown-item>退出</el-dropdown-item>
      </el-dropdown-menu>
    </el-dropdown>
  </div>
</template>

<script>
export default {
  name:"LoginOut",
  data() {
    return {
      circleUrl:
        "https://cube.elemecdn.com/3/7c/3ea6beec64369c2642b92c6726f1epng.png"
    };
  },
  methods:{
    loginOut(){
      var self = this;
      self.$message({
        message: "恭喜你。推出成功",
        type: "success",
        duration: 1000,
        onClose: function(){
          sessionStorage.removeItem("manager");
          self.$router.push({path: "/"});
        }
      });
    }
  }
};
</script>

<style scoped>
#loginOut{
    width: 120px;
    display: flex;
    justify-content: space-around;
    align-items: center;
    cursor: pointer;
}
</style>