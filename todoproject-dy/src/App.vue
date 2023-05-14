// App.vue
<template>
  <Title name="TO-DO" />
  <!-- @<customEvent 이름>="실행되는 method이름" -->
  <ToDoInput @add-to-do="addToDo" />
  <ToDoList :todos="todos" />
</template>

<script>
import Title from './components/Title.vue'
import ToDoInput from './components/ToDoInput.vue'
import ToDoList from './components/ToDoList.vue'

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

</style>