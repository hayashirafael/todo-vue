<template>
  <div class="new-task">
     <input v-model="name" @keydown.enter="add" type="text" class="form" placeholder="Digite uma tarefa">
     <button @click="add" class="form">+</button>
  </div>
</template>

<script>
export default {
   data() {
      return {
         name: ''
      }
   },
   methods: {
      add() {
         this.$emit('taskAdded', {name: this.name})
         this.name = ''
      }
   }
}
</script>

<style>
   .new-task {
      margin: 35px;
   }

   .form {
      outline: none;
      font-size: 1.7rem;
      border: 1px groove rgb(255, 255, 255);
      padding: 5px 10px 8px;
      color: #fff;
   }

   input.form {
      width: 420px;
      background: #fff2;
      border-top-left-radius: 8px;
      border-bottom-left-radius: 8px;

   }

   button.form {
      border-left: none;
      background-color: #2196f3;
      border-top-right-radius: 8px;
      border-bottom-right-radius: 8px;
   }
</style>