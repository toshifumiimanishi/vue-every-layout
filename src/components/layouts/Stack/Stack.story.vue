<script setup lang="ts">
import { HStack, VStack } from "./";
</script>

<template>
  <Story title="Stack" :layout="{ type: 'grid' }">
    <Variant title="HStack">
      <HStack>
        <div>🐶</div>
        <div>🐶</div>
        <div>🐶</div>
      </HStack>
    </Variant>
    <Variant title="VStack">
      <VStack>
        <div>🐶</div>
        <div>🐶</div>
        <div>🐶</div>
      </VStack>
    </Variant>
  </Story>
</template>

