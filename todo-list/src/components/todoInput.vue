<template>
  <div>
    <div class="row">
      <input
        @change="todoTextChange"
        v-bind:value="todoText"
        type="text"
        name="todoItem"
        class="col form-control mr-2"
      />
      <button @click="addTodoV" class="col btn btn-primary">
        Add
      </button>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";
import { v1 } from "uuid";
export default {
  data() {
    return {
      todoText: ""
    };
  },
  methods: {
    ...mapActions(["addTodo"]),
    todoTextChange(e) {
      this.todoText = e.target.value;
    },
    addTodoV() {
      if (this.todoText != "") {
        this.addTodo({
          id: v1(),
          title: this.todoText
        });
        this.todoText = "";
      }
    }
  }
};
</script>

<style></style>
