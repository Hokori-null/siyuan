<script setup>
import { ref } from "vue";
import { invoke } from "@tauri-apps/api/core";

import { Window } from '@tauri-apps/api/window';

const appWindow = new Window('main');

  const minimize = () => {
    appWindow.minimize();
  }
  const maximize = () => {
    appWindow.toggleMaximize();
  }
  const close = () => {
    appWindow.close();
  }

</script>

<template>
<div data-tauri-drag-region class="titlebar">
  <div @click="minimize" class="titlebar-button" id="titlebar-minimize">
    <img
      src="https://api.iconify.design/mdi:window-minimize.svg"
      alt="minimize"
    />
  </div>
  <div @click="maximize" class="titlebar-button" id="titlebar-maximize">
    <img
      src="https://api.iconify.design/mdi:window-maximize.svg"
      alt="maximize"
    />
  </div>
  <div @click="close" class="titlebar-button" id="titlebar-close">
    <img src="https://api.iconify.design/mdi:close.svg" alt="close" />
  </div>
</div>

</template>


<style>
.titlebar {
  height: 30px;
  background: #329ea3;
  user-select: none;
  display: flex;
  justify-content: flex-end;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000; /* 确保 titlebar 在 iframe 之上 */
}

.titlebar-button {
  display: inline-flex;
  justify-content: center;
  align-items: center;
  width: 30px;
  height: 30px;
  user-select: none;
  -webkit-user-select: none;
}

.titlebar-button:hover {
  background: #5bbec3;
}
</style>
