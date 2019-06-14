<template>
  <div>
    <h3>Add Todo</h3>
    <div class="add">
      <form @submit.prevent="onSubmit">
        <input type="text" v-model="todoTitle" placeholder="Add Todo">
        <button type="submit">Submit</button>
      </form>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  name: "AddTodo",
  methods: {
    ...mapActions(["addTodo"]),
    onSubmit() {
      this.addTodo(this.todoTitle);
    }
  },
  data() {
    return {
      todoTitle: ""
    };
  }
};
</script>

<style scoped>
form {
  display: flex;
}

input[type="text"] {
  flex: 10;
  padding: 10px;
  border: 1px solid #41b883;
  outline: 0;
}
input[type="submit"] {
  flex: 2;
  background: #41b883;
  color: #fff;
  border: 1px #41b883 solid;
  cursor: pointer;
}
</style>
