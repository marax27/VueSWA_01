<template>
  <div>Hello {{ value }}</div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      value: "World",
    };
  },
};
</script>

<style scoped>
div {
  font-size: 2em;
  text-align: center;
}
</style>
