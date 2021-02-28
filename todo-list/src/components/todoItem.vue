<template>
  <div>
    <div class="row my-3 justify-content-between">
      <h3 v-if="!editing" class="col">{{ todo.title }}</h3>
      <input
        v-bind:value="todoText"
        @change="todoTextChange"
        v-else
        type="text"
        class="col form-control"
      />
      <button @click="updatetodo(todo)" class="col btn btn-primary mx-2">
        {{ editing ? "Update" : "Edit" }}
      </button>
      <button @click="deleteTodo(todo.id)" class="col btn btn-danger">
        Delete
      </button>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  props: {
    todo: {}
  },
  data() {
    return {
      todoText: "",
      editing: false
    };
  },
  methods: {
    ...mapActions(["deleteTodo", "updateTodo"]),
    todoTextChange(e) {
      this.todoText = e.target.value;
    },
    updatetodo(todo) {
      this.editing = this.editing == true ? false : true;
      if (this.editing) {
        this.todoText = todo.title;
        this.updateTodo(todo);
      } else {
        todo.title = this.todoText;
      }
    }
  }
};
</script>

<style>
.btn {
  max-width: 70px;
}
</style>
