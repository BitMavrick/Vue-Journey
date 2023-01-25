<template>
  <h1>{{ title }}</h1>
  <input type="text" ref="input" />
  <button @click="handleClick">Click me</button>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      title: "This is my first Vue App guys!",
    };
  },
  methods: {
    handleClick() {
      console.log(this.$refs.input);
      // Add a new class to the input
      this.$refs.input.classList.add("active");
      // Focus menthod
      this.$refs.input.focus();
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
