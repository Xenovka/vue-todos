<template>
  <form @submit.prevent="enterTodoItem" class="todo-form row d-flex justify-content-center">
    <div class="todo-input col-lg-4 offset-lg-1">
      <input class="form-control" type="text" name="input" id="todo-input" ref="todoInput" v-model.lazy="todoItem" />
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
      this.$refs.todoInput.value = "";
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
}

.btn {
  background-color: #ccc;
  padding: 0.375rem 1.4rem;
  font-weight: 700;
  transition: all 0.3s ease;
}

.btn:hover {
  color: #fff;
}
</style>
