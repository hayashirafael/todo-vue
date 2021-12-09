<template>
  <div class="task-progress">
     <span class="progress">{{progress}}%</span>
     <div class="bar-progress" :style="{width: progress + '%'}"></div>
  </div>
</template>

<script>
export default {
   props: {progress: {type:Number, default: 0}}
}
</script>

<style>
   .task-progress {
      position: relative;
      height: 20px;
      width: 80%;
      border: 1px solid grey;
      border-radius: 10px;
      display: flex;
      flex-direction: column;
      align-items: center;
   }

   .bar-progress {
      position: absolute;
      height: 100%;
      background-color: #4CAF50;
      border-radius: 10px;
      align-self: flex-start;
   }

   .progress {
      z-index: 1;
      font-size: 1.2rem;
   }

</style>