<template>
  <div class="home">
    <div class="father">
      <div class="son">哈师大</div>
    </div>
    <el-button @click="editColor">修改颜色</el-button>
  </div>
</template>

<script>
import { lightTheme, darkTheme } from "@/assets/js/variable";
export default {
  data() {
    return {
      theme: true
    };
  },
  methods: {
    editColor(){
      this.theme = !this.theme;
      // 调用 `less.modifyVars` 方法来改变变量值，但是在ie下使用不了
      console.log(window);
      console.log(window.less);
      window.less.modifyVars(this.theme ? lightTheme : darkTheme);
      console.log(lightTheme);
      console.log(darkTheme);
    }
  },
  created() {},
};
</script>

<style lang="less" scoped>
// @text: #3c3c3c;
.home {
  .father {
    width: 200px;
    height: 200px;
    background-color: @text;
    display: flex;
    align-items: center;
    justify-content: center;
    .son {
      color: @text-1;
      width: 50px;
      height: 50px;
      // background-color: #fff;
    }
  }
}
</style>
