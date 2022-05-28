<script setup lang="ts">
import type { Align,  Justify } from "../types";
import { computed, withDefaults } from "vue";

type HStackProps = {
  align?: Align;
  justify?: Justify;
  noDefensive?: boolean;
  space?: string;
}

const props = withDefaults(defineProps<HStackProps>(), {
  align: 'flex-start',
  justify: 'flex-start',
  noDefensive: false,
  space: '1rem',
});

const classes = computed(() => ({
  '-no-defensive': props.noDefensive,
}));

const styles = computed(() => ({
  'align-items': props.align,
  'justify-content': props.justify,
}));
</script>

<template>
  <div class="hstack" :class="classes" :style="styles">
    <slot />
  </div>
</template>

<style scoped>
.hstack {
  display: flex;
  gap: v-bind('props.space');
}

.hstack:not(.-no-defensive) {
  flex-wrap: wrap;
}

.hstack > :deep(*) {
  margin-inline: 0;
}
</style>