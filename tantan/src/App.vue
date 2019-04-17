<template>
  <div id="app">
    <Xheader/>
    <Xmain/>
    <Xhint/>
  </div>
</template>

<script>
import Xheader from "./components/Xheader.vue";
import Xmain from "./components/Xmain.vue";
import "../public/iconfont/iconfont.css";
import Xhint from "./components/Xhint.vue";
export default {
  name: "app",
  components: {
    Xheader,
    Xmain,
    Xhint
  }
};
</script>

<style>
</style>
