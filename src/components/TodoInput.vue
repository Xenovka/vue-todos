<template>
  <form @submit.prevent="enterTodoItem" class="todo-form row d-flex justify-content-center">
    <div class="todo-input col-lg-4 offset-lg-1">
      <input class="form-control" type="text" name="input" id="todo-input" ref="todoInput" />
    </div>
    <div class="input-button col-lg-2">
      <button type="submit" class="btn">Enter</button>
    </div>
  </form>
  <todo-items :item="todoItem" />
</template>

<script>
import TodoItems from "@/components/TodoItems.vue";

export default {
  components: {
    TodoItems
  },
  data() {
    return {
      todoItem: ""
    };
  },
  methods: {
    enterTodoItem() {
      const todos = JSON.parse(localStorage.getItem("todos")) || null;
      const itemValue = this.$refs.todoInput.value;

      if (todos !== null) {
        for (let todo of todos) {
          if (todo === itemValue) {
            this.$refs.todoInput.value = "";
            return alert("Failed: Activity already exists!");
          }
        }
      }

      this.todoItem = itemValue;
      this.$refs.todoInput.value = "";
      return alert("Success: Activity added!");
    }
  }
};
</script>

<style scoped>
.todo-form {
  margin-top: 6rem;
}

.form-control,
.btn {
  font-size: 1.8rem;
  padding: 1rem 1.4rem;
}

.btn {
  background-color: #ccc;
  font-weight: 700;
  transition: all 0.3s ease;
}

.btn:hover {
  color: #fff;
}
</style>
