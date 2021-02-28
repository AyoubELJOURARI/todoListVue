<template>
  <div v-for="todo in AllTodo" :key="todo.id">
    <Todoitem :todo="todo" />
  </div>
</template>

<script>
import Todoitem from "@/components/todoItem";
import { mapGetters } from "vuex";
export default {
  name: "List",
  components: {
    Todoitem
  },
  computed: {
    ...mapGetters(["AllTodo"])
  }
};
</script>

<style></style>
