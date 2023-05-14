<template>
    <div id="todoinput">
      <input type="text" v-model="content" />
      <button type="button" @click="addToDo">확인</button>
    </div>
  </template>
  
  <script>
export default {
  data() {
    return {
      content: ''
    }
  },
  methods: {
    addToDo() {
      // emit: 자식컴포넌트에서 부모컴포넌트의 특정 이벤트를 발생시키는 기능
      // 1st 파라미터는 지정된 이벤트의 이름
      // 2nd 파라미터는 전달하고자하는 데이터의 이름 명시
      // v-model을 통해 할일내용을 content에 바인딩
      this.$emit('add-to-do', this.content) //이용해서 이벤트와 데이터를 부모한테 전달
      this.content = ''
    }
  }
}
</script>
  
  <style></style>
  