<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import HelloWorld from './components/HelloWorld.vue'
import { Center } from "./components/layouts/Center/";
import { Sidebar } from "./components/layouts/Sidebar/";

</script>

<template>
  <Center max="1200px">
    <Sidebar space="3rem" side="right" content-min="75%" noStretch>
      <template v-slot:sidebar>
        <Center intrinsic>
          <img alt="Vue logo" src="./assets/logo.png" />
        </Center>
      </template >
      <template v-slot:not-sidebar>
        <HelloWorld msg="Hello Vue 3 + TypeScript + Vite" />
      </template>
    </Sidebar>
  </Center>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
