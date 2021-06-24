<template>
  <div id="app">
    <Tree :label="tree.label"
              :nodes="tree.nodes"
              :depth="0"
    ></Tree>
  </div>
</template>

<script>
let tree = {
  label: 'Food',
  nodes: [
    {
      label: 'Plant',
      nodes: [
        {
          label: 'Fruits',
          nodes:[
            {
              label: 'Apples'
            },
            {
              label: 'Mangos'
            },
            {
              label: 'Oranges'
            },
          ]
        },
        {
          label: 'Vegetables',
          nodes: [
            {
              label: 'Tomatoes'
            },
            {
              label: 'Potatoes'
            },
            {
              label: 'Cucumber'
            },
          ]
        }
      ]
    },
    {
      label: 'Animal',
      nodes: [
        {
          label: 'Meat'
        },
        {
          label: 'Milk'
        },
        {
          label: 'Eggs'
        },
      ]
    }
  ]
};



import Tree from '@/components/Tree'
export default {
  name: 'app',
  data () {
    return {
      tree
    }
  },
  components: {
    Tree
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
