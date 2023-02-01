<template>
  <h1>{{ title }}</h1>
  <Modal :header="props1" :text="props2" :theme="theme" />
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      title: "This is my first Vue App guys!",
      props1: "this is the main props",
      props2: "This is another props",
      theme: "sale",
    };
  },
  methods: {
    handleClick() {
      console.log(this.$refs.input);
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
