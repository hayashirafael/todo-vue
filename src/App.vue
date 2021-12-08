<template>
  <div id="app">
    <h1>Tarefas</h1>
    <TaskGrid :tasks="tasks"/>
  </div>
</template>

<script>
import TaskGrid from './components/TaskGrid.vue'
export default {
  name: 'App',
  components: {
    TaskGrid
  },
  data() {
    return {
      tasks: [
        {name: 'Lavar louça', pending: false},
        {name: 'Comprar roupa', pending: true},
      ]
    }
  },
}
</script>

<style>
body {
  background: linear-gradient(to right, #2C5364, #203A43, #0F2027);

}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  display: flex;
  flex: 1;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
  }

  
  #app h1 {
    color: #fff;
  }
</style>
