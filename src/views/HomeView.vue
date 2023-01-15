<template>
  <tree-menu v-bind="tree" />
</template>

<script>
import TreeMenu from '@/components/TreeMenu.vue';
export default {
  components: {
    TreeMenu,
  },
  data() {
    return {
      tree: {
        label: 'root',
        depth: 0,
        nodes: [
          {
            label: 'item1',
            nodes: [
              {
                label: 'item1.1',
              },
              {
                label: 'item1.2',
                nodes: [
                  {
                    label: 'item1.2.1',
                  },
                ],
              },
            ],
          },
          {
            label: 'item2',
          },
        ],
      },
    };
  },
};
</script>

<style scoped lang="scss"></style>
