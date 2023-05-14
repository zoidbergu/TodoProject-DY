// App.vue
<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <Title name="TO-DO" />
  <!-- @<customEvent 이름>="실행되는 method이름" -->
  <to-do-input @add-to-do="addToDo" />
  <to-do-list :todos="todos" />
</template>

<script>
import Title from './views/Title.vue'
import ToDoInput from './views/ToDoInput.vue'
import ToDoList from './views/ToDoList.vue'

export default {
  name: 'App',
  components: {
    Title,
    ToDoInput,
    ToDoList
  },
  data() { 
    return {
      todos: ['과제하기','숙제하기','청소하기']
    }
  },
  methods: {
    addToDo(content) {
      this.todos.push(content) //클릭하면 여기로 전달됨
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>