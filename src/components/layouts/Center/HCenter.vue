<script setup lang="ts">
import { computed, withDefaults } from "vue";

type HCenterProps = {
  andText?: boolean;
  gutters?: string;
  intrinsic?: boolean;
  maxWidth?: string;
}
const props = withDefaults(defineProps<HCenterProps>(), {
  andText: false,
  gutters: '0',
  intrinsic: false,
  maxWidth: 'none',
})

const classes = computed(() => ({
  '-and-text': props.andText,
  '-intrinsic': props.intrinsic,
}))
</script>

<template>
  <div class="hcenter" :class="classes">
    <slot />
  </div>
</template>

<style scoped>
.hcenter {
  box-sizing: content-box;
  max-width: v-bind('props.maxWidth');
  margin-inline: auto;
  padding-inline: v-bind('props.gutters');
  display: flex;
  flex-direction: column;
}

.hcenter.-and-text {
  text-align: center;
}

.hcenter.-intrinsic {
  align-items: center;
}
</style>