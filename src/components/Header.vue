<template>
  <div class="header">
    <span id="title">📺 B 站视频各项数据排行榜 📆 更新至 2018-03-05</span>
    <span id="profile">✨ 由 <a href="https://github.com/chenjiandongx">chenjiandongx</a> 贡献 ✨ <el-button type="text" @click="open">打赏作者</el-button> </span>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    methods: {
      open() {
        this.$alert('<div align="center"><img src="https://user-images.githubusercontent.com/19553554/35425854-504e716a-0299-11e8-81fc-4a511f1c47e8.png" width=231 height=265>', '谢谢您的慷慨捐赠！！', {
          dangerouslyUseHTMLString: true
        });
      }
    }
  };
</script>

<style scoped>
  span {
    height: 40px;
    line-height: 40px;
  }
  #profile {
    float: right;
    margin-right: 1%;
  }
  #title {
    margin-left: 1%;
  }
  .header {
    width: 100%;
    height: 40px;
    background-color: #c0ccda;
  }
</style>
