<<<<<<< HEAD
<template>
  <div>
=======
  
<template>
  <div class="inputBox shadow">
>>>>>>> 3272edd6af1d4226d94a88360a361ba8da0c424b
    <input
      type="text"
      v-model="newTodoItem"
      placeholder="Type what you have to do"
<<<<<<< HEAD
      v-on:keyup.enter="addTodo"
=======
      v-on:keypress.enter="addTodo"
>>>>>>> 3272edd6af1d4226d94a88360a361ba8da0c424b
    />
    <span class="addContainer" v-on:click="addTodo">
      <i class="addBtn fas fa-plus" aria-hidden="true"></i>
    </span>
<<<<<<< HEAD
  </div>
</template>
<script>
=======

    <modal v-if="showModal" @close="showModal = false">
      <h3 slot="header">경고</h3>
      <span slot="footer" @click="showModal = false"
        >할 일을 입력하세요.
        <i class="closeModalBtn fas fa-times" aria-hidden="true"></i>
      </span>
    </modal>
  </div>
</template>

<script>
import Modal from "./common/Modal.vue";
>>>>>>> 3272edd6af1d4226d94a88360a361ba8da0c424b
export default {
  data() {
    return {
      newTodoItem: "",
<<<<<<< HEAD
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
=======
      showModal: false,
    };
  },
  methods: {
    addTodo() {
      if (this.newTodoItem !== "") {
        var value = this.newTodoItem && this.newTodoItem.trim();
        this.$emit("addTodo", value);
        this.clearInput();
      } else {
        this.showModal = !this.showModal;
      }
    },
    clearInput() {
      this.newTodoItem = "";
    },
  },
  components: {
    Modal: Modal,
  },
};
</script>

>>>>>>> 3272edd6af1d4226d94a88360a361ba8da0c424b
<style scoped>
input:focus {
  outline: none;
}
<<<<<<< HEAD
</style>
=======
.inputBox {
  background: white;
  height: 50px;
  line-height: 50px;
  border-radius: 5px;
}
.inputBox input {
  border-style: none;
  font-size: 0.9rem;
}
.addContainer {
  float: right;
  background: linear-gradient(to right, #6478fb, #8763fb);
  display: inline-block;
  width: 3rem;
  border-radius: 0 5px 5px 0;
}
.addBtn {
  color: white;
  vertical-align: middle;
}
</style>
>>>>>>> 3272edd6af1d4226d94a88360a361ba8da0c424b
