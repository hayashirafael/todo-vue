<template>
  <div id="app">
    <h1>Tarefas</h1>
    <NewTask @taskAdded="addTask($event)"/>
    <TaskGrid :tasks="tasks"/>
  </div>
</template>

<script>
import TaskGrid from './components/TaskGrid.vue'
import NewTask from './components/NewTask.vue'
export default {
  name: 'App',
  components: {
    TaskGrid,
    NewTask
  },
  data() {
    return {
      tasks: [
        {name: 'Lavar louça', pending: false},
        {name: 'Comprar roupa', pending: true},
      ]
    }
  },
  methods: {
    addTask(task) {
      const sameName = t => t.name === task.name
      const reallyNew = this.tasks.filter(sameName).length === 0
      if (reallyNew) {
        this.tasks.push({
          name: task.name,
          pending: task.pending || true
        })
      } else {
        alert('Essa task já existe!')
      }
    }
  }
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
