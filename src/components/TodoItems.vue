<template>
  <div class="todo-items">
    <ul>
      <li v-for="item in items" :key="item">{{ item }}</li>
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
    getTodoItem() {
      this.items.push(this.item);
      // localStorage.setItem("todos", this.items);
      console.log(this.items);
    }
  },
  updated() {
    this.getTodoItem();
  }
};
</script>
