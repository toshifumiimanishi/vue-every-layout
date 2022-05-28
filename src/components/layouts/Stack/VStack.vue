<script setup lang="ts">
import { withDefaults, ref, onMounted, computed } from "vue";

type VstackProps = {
  recursive?: boolean;
  space?: string;
  splitAfter?: number;
}

const rootRef = ref(null);

const props = withDefaults(defineProps<VstackProps>(), {
  space: '1rem',
})

const classes = computed(() => ({
  '-recursive': props.recursive,
}))

onMounted(() => {
  [...rootRef.value.children].map((element, index) => {
    if (props.splitAfter === index + 1) {
      element.style.setProperty('margin-bottom', 'auto');
    }
  });
});
</script>

<template>
  <div class="vstack" ref="rootRef" :class="classes">
    <slot />
  </div>
</template>

<style scoped>
.vstack {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
}

.vstack:not(.-recursive) > :deep(*) {
  margin-block: 0;
}

.vstack.-recursive :deep(*) {
  margin-block: 0;
}

.vstack:not(.-recursive) > :deep(* + *) {
  margin-top: v-bind('props.space');
}

.vstack.-recursive :deep(* + *) {
  margin-top: v-bind('props.space');
}
</style>