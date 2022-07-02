<script setup lang="ts">
import { Sidebar } from "./";
</script>

<template>
  <Story title="Sidebar">
    <Sidebar>
      <template v-slot:sidebar>
        🐶
      </template>
      <template v-slot:not-sidebar>
        🦴🦴🦴🦴🦴
      </template>
    </Sidebar>
  </Story>
</template>
