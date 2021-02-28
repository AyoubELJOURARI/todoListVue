<template>
  <div id="todo" class="container">
    <Todoinput />
    <Todolist />
  </div>
</template>
<script>
import Todoinput from "@/components/todoInput";
import Todolist from "@/components/todoList";
export default {
  name: "Todo",
  components: {
    Todoinput,
    Todolist
  }
};
</script>
<style scoped>
#todo {
  margin-top: 30px;
}
</style>
