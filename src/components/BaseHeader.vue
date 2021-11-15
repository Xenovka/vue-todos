<template>
  <div class="header">
    <h1 class="text-center">{{ username }}'s Todo list</h1>
  </div>
</template>

<script>
export default {
  props: ["name"],
  data() {
    return {
      username: this.name
    };
  }
};
</script>

<style scoped>
.header {
  padding: 1rem 0;
}

.header > h1 {
  font-size: 4.4rem;
  font-weight: 800;
}
</style>
