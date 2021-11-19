<template>
  <div class="container item-container d-flex justify-content-center position-relative">
    <ul class="item-wrapper row">
      <div v-for="item in items" :key="item" class="d-flex">
        <li class="todo-item col-lg-6 offset-lg-2">{{ item }}</li>
        <button class="btn-delete col-lg-1">Delete</button>
      </div>
    </ul>
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
    getTodoItem(item) {
      this.items.push(item);
      // localStorage.setItem("todos", this.items);
      console.log(this.items);
    }
  },
  watch: {
    item(newProp, oldProp) {
      this.getTodoItem(newProp);
      console.log(oldProp);
    }
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

.todo-item {
  font-size: 1.8rem;
  font-weight: 500;
  list-style: none;
  padding: 1rem 1.4rem;
  margin-bottom: 0.6rem;
  background-color: #ccc;
}

.btn-delete {
  padding: 1rem 1.4rem;
  font-size: 1.4rem;
}
</style>
