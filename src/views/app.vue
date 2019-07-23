<template>
  <div class="center">
    <!-- <text class="h2">Dolphin weex ui</text>
    <text class="h4">专注于weex最佳实践</text>-->
    <wxc-minibar
      title="标题"
      background-color="#009ff0"
      text-color="#FFFFFF"
      right-text="更多"
      @wxcMinibarLeftButtonClicked="minibarLeftButtonClick"
      @wxcMinibarRightButtonClicked="minibarRightButtonClick"
    ></wxc-minibar>
    
    <image src="../image/logo.png" class="logo"></image>
  </div>
</template>
<script>
 import { WxcMinibar } from 'weex-ui';
 const globalEvent = weex.requireModule("globalEvent");
  const modal = weex.requireModule('modal');
module.exports = {
  data() {
    return {};
  },
  mounted() {
    globalEvent.addEventListener("androidback", e => {
      this.$pop();
    });
  },
  components: { WxcMinibar },
  methods: {
    minibarLeftButtonClick() {},
    minibarRightButtonClick() {
      modal.toast({ message: "click rightButton!", duration: 1 });
    }
  }
};
</script>
<style scoped>
.logo {
    width: 80px;
    height: 80px;
}
</style>
