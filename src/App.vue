<template>
  <div>
    <h1>Hello {{ value }}</h1>
    <div>{{ authMessage }}</div>
    <ul>
      <li><a href="/.auth/login/google">Login with Google</a></li>
      <li><a href="/.auth/login/facebook">Login with Facebook</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      value: "World",
      authMessage: "n/a",
    };
  },
  mounted() {
    fetch("/.auth/me")
      .then((response) => response.json())
      .then((data) => {
        if (data.clientPrincipal) {
          this.authMessage = `Hello ${data.clientPrincipal.userDetails}`;
        }
      })
      .catch((e) => {
        this.authMessage = `Error: ${e}`;
      });
  },
};
</script>

<style scoped>
h1 {
  text-align: center;
}
</style>
