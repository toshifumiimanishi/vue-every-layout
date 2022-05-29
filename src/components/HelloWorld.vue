<script setup lang="ts">
import { Box } from "./layouts/Box/";
import { HCenter } from "./layouts/Center/";
import { VStack, HStack } from "./layouts/Stack/";
import { ref } from 'vue'

defineProps<{ msg: string }>()

const count = ref(0)
</script>

<template>
  <VStack space="3rem" :split-after="2">
    <HCenter max-width="640px" gutters="24px" andText intrinsic>
      <h1>{{ msg }}</h1>
      <Box borderWidth="1px" borderRadius="8px">
        <p>
          Recommended IDE setup:
          <a href="https://code.visualstudio.com/" target="_blank">VS Code</a>
          +
          <a href="https://github.com/johnsoncodehk/volar" target="_blank">Volar</a>
        </p>

        <p>See <code>README.md</code> for more information.</p>
      </Box>
      <HStack align="center">
        <p>
          <a href="https://vitejs.dev/guide/features.html" target="_blank">
            Vite Docs
          </a>
          |
          <a href="https://v3.vuejs.org/" target="_blank">Vue 3 Docs</a>
        </p>
        <button type="button" @click="count++">count is: {{ count }}</button>
      </HStack>
      <p>
        Edit
        <code>components/HelloWorld.vue</code> to test hot module replacement.
      </p>
    </HCenter>
  </VStack>
</template>

<style scoped>
a {
  color: #42b983;
}

label {
  font-weight: bold;
}

code {
  background-color: #eee;
  padding: 2px 4px;
  border-radius: 4px;
  color: #304455;
}
</style>
