<template>
  <div class="home">
    <div class="father">
      <div class="son">哈师大</div>
    </div>
    <el-button @click="editColor">修改颜色</el-button>
  </div>
</template>

<script>
import { initTheme } from "../theme";
export default {
  data() {
    return {
      theme: true
    };
  },
  methods: {
    editColor(){
      this.theme = !this.theme;
      initTheme(this.theme)
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
    background-color: var(--text);
    // background-color: #3c3c3c;
    display: flex;
    align-items: center;
    justify-content: center;
    .son {
      color: var(--text-1);
      width: 50px;
      height: 50px;
      // background-color: #fff;
    }
  }
}
</style>
