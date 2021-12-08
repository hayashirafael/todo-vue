<template>
  <div class="task-grid">
     <template v-if="tasks.length">
        <Task v-for="task in tasks" :key="task.name" :task="task"></Task>
     </template>
     <p v-else class="no-task">Nenhuma task encontrada.</p>

  </div>
</template>

<script>
import Task from './Task.vue'
export default {
   components: {Task},
   props: {
      tasks: {type: Array, required: true},

   }
}
</script>

<style>
body {
   color: #fff;
}

.task-grid {
   display: flex;
   flex-wrap: wrap;
   justify-content: center;
   align-items: center;
   align-content: center;
}

.task-grid .task {
   margin: 10px;
}

.no-task {
   color: #aaa;
   font-size: 1.7rem;
}
</style>