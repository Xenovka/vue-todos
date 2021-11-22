<template>
  <div class="container">
    <base-header />
    <todo-input />
  </div>
</template>

<script>
import BaseHeader from "@/components/BaseHeader.vue";
import TodoInput from "@/components/TodoInput.vue";

export default {
  name: "Home",
  components: {
    BaseHeader,
    TodoInput
  }
};
</script>
