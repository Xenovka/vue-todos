<template>
  <div class="container item-container d-flex justify-content-center position-relative">
    <ul class="item-wrapper row" v-if="items.length">
      <div v-for="item in items" :key="item" class="d-flex justify-content-center row col-lg-11">
        <li class="todo-item col-lg-6 offset-lg-2">{{ item }}</li>
        <div class="col-lg-2 btn-wrapper">
          <button class="btn btn-danger" @click="deleteItem">Delete</button>
        </div>
      </div>
    </ul>
    <h3 v-else>Nothing todo</h3>
  </div>
</template>

<script>
export default {
  props: ["item"],
  data() {
    return {
      items: []
    };
  },
  methods: {
    setTodoItem(item) {
      this.items.push(item);
      localStorage.setItem("todos", JSON.stringify(this.items));
    },

    getTodoItem() {
      this.items = JSON.parse(localStorage.getItem("todos")) || [];
    },

    deleteItem() {}
  },
  watch: {
    item(newProp, oldProp) {
      this.setTodoItem(newProp);
      console.log(oldProp);
    }
  },
  mounted() {
    this.getTodoItem();
    console.log(this.items);
  }
};
</script>

<style scoped>
.item-container {
  margin-top: 3rem;
}

.item-wrapper {
  width: 100%;
}

.btn-wrapper {
  display: flex;
}

.todo-item {
  font-size: 1.8rem;
  font-weight: 500;
  list-style: none;
  padding: 1rem 1.4rem;
  margin-bottom: 0.6rem;
  background-color: #ccc;
  border-radius: 0.25rem;
}

.btn-danger {
  padding: 1rem 1.4rem;
  font-size: 1.4rem;
  font-weight: 600;
  margin-bottom: 0.6rem;
}
</style>
