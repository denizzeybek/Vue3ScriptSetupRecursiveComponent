<template>
  <div class="tree-menu">
    <div :style="[indent]" @click="toggleChildren">{{ label }}</div>
    <template v-for="node in nodes" :key="node.id">
      <tree-menu
        v-if="showChildren"
        :nodes="node.nodes"
        :label="node.label"
        :depth="depth + 1"
      ></tree-menu>
    </template>
  </div>
</template>
<script>
export default {
  // If you’re using a component recursively you must either register it globally with Vue.component,
  // or, give it a name property.
  name: 'tree-menu',
};
</script>
<script setup>
import { ref, defineProps, computed } from 'vue';

const props = defineProps(['label', 'nodes', 'depth']);
const showChildren = ref(false);
const indent = computed(() => {
  return { 'margin-left': `${props.depth * 50}px` };
});
const toggleChildren = () => {
  showChildren.value = !showChildren.value;
};
</script>
