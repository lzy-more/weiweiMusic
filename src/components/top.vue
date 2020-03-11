<template>
  <div class="top-container">
    <div class="left-box">
     
      <div class="history-wrapper" style="margin-left: 20px;">
        <span class="iconfont icon-arrow-lift" @click='$router.back(-1)' title="后退"></span>
        <span class="iconfont icon-arrow-right"  @click='$router.back(1)' title="前进"></span>
      </div>
  
     
    </div>
    <div class="icon-wrapper" style="">
      <img src="../assets/banner.jpg" alt="" class="weiwei">
     </div>
     <h1 class="colorText">薇薇一笑很倾城</h1>
    <div class="right-box">
      <div class="el-input el-input--small el-input--prefix">
        <!-- 搜索框 -->
        <input
          type="text"
          autocomplete="off"
          placeholder="搜索"
          class="el-input__inner"
          v-model="inputValue"
          @keyup.enter="toResult"
        />
        <span class="el-input__prefix">
          <i class="el-input__icon el-icon-search"></i>
        </span>
      </div>
    </div>
  </div>
</template>

<script>
  // import  '../assets/colorText.css'
  export default { 
    name: 'top',
    data() {
      return {
        // 输入的内容
        inputValue: ''
      }
    },
    methods: {
      toResult() {
        // 非空判断
        if (this.inputValue == '') {
          // 提示用户
          this.$message.warning('请输入内容')
        }else{
          // 去搜索页 携带数据
          this.$router.push('/result?q='+this.inputValue)
        }
      }
    }
  }
</script>

<style scoped>
  .weiwei{width: 300px;height: 40px;margin-top: 10px;}
  .top-container .left-box .history-wrapper .iconfont:first-child {
    margin-right: 40px;
}
.colorText{text-shadow:10px 7px 5px blueviolet;color: pink;letter-spacing: 30px;}
</style>
