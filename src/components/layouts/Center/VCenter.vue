<script setup lang="ts">
import { withDefaults } from "vue";

type VCenterProps = {
  minHeight?: string;
  gutters?: string;
}

const props = withDefaults(defineProps<VCenterProps>(), {
  gutters: '16px',
})
</script>

<template>
  <div class="vcenter">
    <slot />
  </div>
</template>

<style scoped>
.vcenter {
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  min-height: v-bind('props.minHeight');
  padding-block: v-bind('props.gutters');
}

.vcenter > :deep(*) {
  margin-block: auto;
}
</style>