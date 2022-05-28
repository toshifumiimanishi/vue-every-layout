<script setup lang="ts">
import { withDefaults } from "vue";

type BoxProps = {
  backgroundColor?: string;
  borderColor?: string;
  borderRadius?: string;
  borderWidth?: string;
  padding: string;
}

const props = withDefaults(defineProps<BoxProps>(), {
  borderColor: '#e2e8f0',
  padding: '16px',
})
</script>

<template>
  <div class="box">
    <slot />
  </div>
</template>

<style scoped>
.box {
  padding: v-bind('props.padding');
  background-color: v-bind('props.backgroundColor');
  border: v-bind('props.borderWidth') solid v-bind('props.borderColor');
  border-radius: v-bind('props.borderRadius');
}
</style>