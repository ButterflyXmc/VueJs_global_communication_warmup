<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <ToastNotification />
    <DeleteButton />
    <PostButton />
  </div>
</template>

<script>
import ToastNotification from "@/components/ToastNotification.vue";
import DeleteButton from "@/components/DeleteButton.vue";
import PostButton from "@/components/PostButton.vue";

export default {
  name: "App",
  components: {
    ToastNotification,
    DeleteButton,
    PostButton,
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
