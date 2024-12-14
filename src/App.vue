<template>
  <Titlebar />
  <<iframe id="baiduFrame" src="https://note.honulla.com/stage/build/desktop/?r=vt8iq6a"></iframe>>
  <div id="app">
    <!-- 这里将是你的 Titlebar 组件 -->
    
    <!-- 其他内容 -->
  </div>
</template>

<script>
import Titlebar from './componets/titlebar.vue';

export default {
  name: 'App',
  components: {
    Titlebar
  }
}
</script>

<style>
/* 你的样式 */
iframe {
  position: absolute;
  top: 30px; /* 调整这个值以适应 titlebar 的高度 */
  left: 0;
  right: 0;
  bottom: 0;
  width: 100%;
  height: calc(100% - 30px); /* 减去 titlebar 的高度 */
  border: none;
}
</style>
