
<template>
  <div class="drop-zone">
    <div v-for="item in getList(1)" :key="item.id" class="drag-el">
      {{item.title}}
    </div>
  </div>

  <div class="drop-zone">
    <div v-for="item in getList(2)" :key="item.id" class="drag-el">
      {{item.title}}
    </div>
  </div>
</template>

<script>
import {ref} from "vue"

export default {
  setup() {
    const items = ref([
      {id: 0, title: "Item A", list: 1},
      {id: 1, title: "Item B", list: 1},
      {id: 2, title: "Item C", list: 2},
    ])

    const getList = (list) => {
      return items.value.filter(item => item.list === list)
    }

    return {
      getList
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  text-align: center;
  margin-top: 60px;
}

.drop-zone {
  width: 50%;
  background-color: #f1f1f1;
  margin: 50px auto;
  padding: 10px;
  min-height: 10px;
}

.drag-el {
  background-color: #3498db;
  padding: 5px;
  color: #fff;
  margin-button: 10px;
}
</style>
