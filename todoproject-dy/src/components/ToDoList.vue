<template>
    <div id="todolist">
      <div id="container" v-for="data in todos" :key="data">
        <li id="text">{{ data }}</li>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      todos: Array
    }
  }
  </script>
  
  <style></style>
  