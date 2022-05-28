<script setup lang="ts">
import type { Align } from '../types';
import { computed, withDefaults } from "vue";

type SidebarProps = {
  align?: Align;
  contentMin?: string;
  noDefensive?: boolean;
  noStretch?: boolean;
  side?: 'right' | 'left';
  sideWidth?: string;
  space?: string;
}

const props = withDefaults(defineProps<SidebarProps>(), {
  contentMin: '50%',
  noDefensive: false,
  noStretch: false,
  side: 'left',
  sideWidth: 'auto',
  space: '1rem',
});

const classes = computed(() => ({
  '-no-defensive': props.noDefensive,
  '-no-stretch': props.noStretch,
  '-reverse': props.side === 'right',
}));

const styles = computed(() => ({
  'align-items': props.align,
}));
</script>

<template>
  <div class="with-sidebar" :class="classes" :style="styles">
    <div class="sidebar">
      <slot name="sidebar" />
    </div>
    <div class="not-sidebar">
      <slot name="not-sidebar" />
    </div>
  </div>
</template>

<style scoped>
.with-sidebar {
  display: flex;
  gap: v-bind('props.space');
}

.with-sidebar:not(.-no-defensive) {
  flex-wrap: wrap;
}

.with-sidebar.-no-stretch {
  align-items: flex-start;
}

.with-sidebar.-reverse {
  flex-direction: row-reverse;
}

.sidebar {
  flex-grow: 1;
  flex-basis: v-bind('props.sideWidth');
}

.not-sidebar {
  flex-basis: 0;
  flex-grow: 999;
  min-width: v-bind('props.contentMin');
}
</style>