<template>
  <div v-if="isUsernameExist" class="container">
    <base-header :name="getUsername" />
  </div>
</template>

<script>
import BaseHeader from "@/components/BaseHeader.vue";

export default {
  name: "Home",
  components: {
    BaseHeader
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
  computed: {
    getUsername() {
      return this.username;
    }
  },
  mounted() {
    this.insertUsername();
  }
};
</script>

<style scoped></style>
