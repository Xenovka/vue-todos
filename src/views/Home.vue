<template>
  <div v-if="isUsernameExist" class="container">
    <base-header :name="username" />
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
  },
  data() {
    return {
      username: "",
      isUsernameExist: false
    };
  },
  methods: {
    insertUsername() {
      this.username = prompt("Insert Your username:");

      if (!this.username.length) {
        alert("You have to insert your username!");
        this.insertUsername();
      } else {
        this.isUsernameExist = true;
        return;
      }
    }
  },
  mounted() {
    this.insertUsername();
  }
};
</script>
