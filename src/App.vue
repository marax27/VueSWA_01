<template>
  <div>
    <h1>Hello {{ value }}</h1>
    <p><a href="/.auth/login/auth0">Login</a></p>
  </div>
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
h1,
p {
  text-align: center;
}
</style>
