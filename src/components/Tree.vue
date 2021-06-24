<template>
  <div class="tree-menu">
    <button class="label-wrapper" :style="indent" @click="toggleChildren">{{ label }}</button>
    <div class="line">
    <Tree
        v-show="showChildren"
        v-for="(node, ind) in nodes"
        :nodes="node.nodes"
        :label="node.label"
        :depth="depth + 1"
        :key="ind"
    >
    </Tree>
    </div>
  </div>
</template>
<script>
export default {
  props: ['label', 'nodes', 'depth'],
  name: 'Tree',
  data() {
    return {
      showChildren: false
    }
  },
  computed: {
    indent() {
      return {transform: `translate(${this.depth * 100}px)`}
    }
  },
  methods: {
    toggleChildren() {
      this.showChildren = !this.showChildren
    }
  }
}
</script>
<style>
.label-wrapper {
  background-color: #4CAF50;
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  display: inline-block;
  font-size: 16px;
  border-radius: 20px;
  margin-bottom: 15px;
  cursor: pointer;
  }
</style>

