<template>
  <div>
    <!--1. define on click on this button  -->
    <button @click="toastNotify">DELETE</button>
  </div>
</template>

<script>
export default {
  name: "DeleteButton",
  data() {
    return {
      message: `Successfully deleted!`,
    };
  },
  //   2.Method
  methods: {
    toastNotify() {
      //3. making a global emit
      //   sending a message
      //(`add the name of the emit`, then (whatever we want to pass) ->the list of the argument -> `Successfully deleted!` -> this.message)
      this.$root.$emit(`toastNotify`, this.message);
    },
  },
};
</script>

<style scoped>
</style>