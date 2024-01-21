<template>
  <div class="flex flex-col items-center justify-center h-screen">

    <h1 class="text-4xl">Hii from Aniket</h1>
    <TodoList />
  </div>
</template>
  
  
<script>
import TodoList from './components/TodoList.vue';

export default {
  name: "app",
  components: {
    TodoList
  }

}
</script>
  
<style>
body {
  background-color: rgb(66, 66, 66);
  color: aliceblue;
}
</style>
