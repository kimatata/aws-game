<template>
  <GameCanvas :nodes="nodes" :edges="edges" />
</template>

<script setup lang="ts">
import type { Edge, Node } from '@vue-flow/core'
definePageMeta({
  layout: 'default'
})

const nodes = ref<Node[]>([
  {
    id: '1',
    position: { x: 50, y: 50 },
    data: { label: 'Users', },
  }
]);
const edges = ref<Edge[]>([])
</script>