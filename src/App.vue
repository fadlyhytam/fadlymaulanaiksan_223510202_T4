<template>
  <div id="app">
    <parent-component></parent-component>
  </div>
</template>

<script>
import ParentComponent from './components/ParentComponent.vue'

export default {
  components: {
    ParentComponent
  }
}
</script>

<style>
body {
  font-family: Arial, sans-serif;
  background-color: #e9ecef;
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
#app {
  width: 600px;
}
</style>
