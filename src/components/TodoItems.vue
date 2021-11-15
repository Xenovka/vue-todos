<template>
  <div class="todo-items">
    <ul>
      <li></li>
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
      console.log(this.item);
    }
  },
  updated() {
    this.getTodoItem();
  }
};
</script>
