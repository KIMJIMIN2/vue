<template>
  <div>
    <input
      type="text"
      v-model="newTodoItem"
      placeholder="Type what you have to do"
      v-on:keyup.enter="addTodo"
    />
    <span class="addContainer" v-on:click="addTodo">
      <i class="addBtn fas fa-plus" aria-hidden="true"></i>
    </span>
  </div>
</template>
<script>
export default {
  data() {
    return {
      newTodoItem: "",
    };
  },
  methods: {
    addsTodo() {
      //      console.log(this.newTodoItem);
      if (this.newTodoITem !== "") {
        var value = this.newTodoItem && this.newTodoItem.trim();
        localStorage.setItem(value, value);
        this.clearInput();
      }
      //      localStorage.setItem(this.newTodoItem, this.newTodoItem); // 로컬 스토리지
    },
  },
};
</script>
<style scoped>
input:focus {
  outline: none;
}
</style>
