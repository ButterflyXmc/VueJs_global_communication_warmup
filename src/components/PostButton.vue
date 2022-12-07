<template>
  <div>
    <!-- 3. -->
    <button @click="toastNotify">POST</button>
  </div>
</template>

<script>
export default {
  name: "PostButton",
  //   1.
  data() {
    return {
      message: `Successfully Posted`,
    };
  },
  methods: {
    // 2.
    toastNotify() {
      //   sending a message
      //(`add the name of the emit`, then (whatever we want to pass) ->the list of the argument -> `Successfully deleted!` -> this.message)
      this.$root.$emit(`toastNotify`, this.message);
    },
  },
};
</script>

<style scoped>
</style>