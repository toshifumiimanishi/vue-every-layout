<script setup lang="ts">
import { HCenter, VCenter } from "./";
</script>

<template>
  <Story title="Center" :layout="{ type: 'grid' }">
    <Variant title="HCenter">
      <HCenter gutters="20px" max-width="200px" and-text>
        🐶
      </HCenter>
    </Variant>
    <Variant title="VCenter">
      <VCenter gutters="20px" min-height="200px">
        <div>🐶</div>
      </VCenter>
    </Variant>
  </Story>
</template>