<template>
  <div class="container item-container d-flex justify-content-center">
    <ul>
      <li class="todo-item" v-for="item in items" :key="item">{{ item }}</li>
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

.todo-item {
  font-size: 1.8rem;
}
</style>
