<script setup lang="ts">
import { computed, withDefaults } from "vue";

type CenterProps = {
  max?: string;
  andText?: boolean;
  gutters?: string;
  intrinsic?: boolean;
}
const props = withDefaults(defineProps<CenterProps>(), {
  max: 'none',
  andText: false,
  gutters: '0',
  intrinsic: false,
})

const classes = computed(() => ({
  '-and-text': props.andText,
  '-intrinsic': props.intrinsic,
}))
</script>

<template>
  <div class="center" :class="classes">
    <slot />
  </div>
</template>

<style scoped>
.center {
  box-sizing: content-box;
  max-width: v-bind('props.max');
  margin-inline: auto;
  padding-inline: v-bind('props.gutters');
  display: flex;
  flex-direction: column;
}

.center.-and-text {
  text-align: center;
}

.center.-intrinsic {
  align-items: center;
}
</style>