<template>
    <h1>Hii from Aniket</h1>
    <TodoList/>
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
    background-color: rgb(66,66,66);
    color: aliceblue;
  }
  </style>
  