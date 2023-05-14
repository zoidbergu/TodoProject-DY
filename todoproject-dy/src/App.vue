// App.vue
<template>
  <div class="container-sm mt-5">
    <h4>Todo</h4>
    <div class="input-group mb-3">
      <input 
        type="text" 
        class="form-control" 
        placeholder="할일을 입력해주세요" 
        aria-describedby="button-addon2"
        v-model="inputData"
      >
      <button 
      class="btn btn-outline-danger" 
      type="button" id="button-addon2"
      @click="addTodo"
      >
        추가
      </button>
    </div>
  </div>
  <div class="container-sm mt-5">
    <ul>
      <li v-for="(todos,index) in todos " :key="index">{{ todos }}<hr></li>
    </ul>
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
  },
  data() { 
    return {
      inputData : '',
      todos:[],
    }
  },
  methods: {
    addTodo(){
      if(this.inputData.trim() === '') {
        alert('할일을 입력해주세요!');
        return;
      }
      this.todos.push(this.inputData);
      this.inputData = '';
    },
    deleteTodo(){
      this.todos.pop();
    }
  },
  
}
</script>

<style>

</style>