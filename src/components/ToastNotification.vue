<template>
  <!-- #10. -->
  <!-- (the reason for us adding a if statement is to the border only pops when the array pops) -->
  <!-- v-if -> if the msgOueue has a length, only then display the length -->
  <div v-if="msgQueue.length" class="basediv">
    <!-- we want this div to print multiple messages so we need v-for loop -->
    <div v-for="(msg, index) in msgQueue" :key="index">
      <h1>{{ msg }}</h1>
      <button @click="clearMessage(index)">Dismiss</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "ToastNotification",
  // 1.  adding an array for where the message can print
  data() {
    return {
      msgQueue: [],
    };
  },
  // Functions
  methods: {
    //2. a handler that does what we want it do -> we're receiving this msg from postButton
    // we're pushing the recived msg in the msgQueue array
    handleNotification(message) {
      this.msgQueue.push(message);
    },
    // splice function takes 2 argument. 1.The index-> the element you want to delete and 2.The #-> of items you want to delete
    clearMessage(index) {
      this.msgQueue.splice(index, 1);
    },
  },
  //   4.Listening for the event in mounted
  mounted() {
    // the event and then the call back (a function that passes the argument)
    this.$root.$on(`toastNotify`, this.handleNotification);
  },
};
</script>

<style scoped>
.basediv {
  border: dotted 2px black;
  width: 20vw;
  /* fixed because it'll always be there even if you scroll down or up */
  position: fixed;
  right: 5px;
  top: 5px;
}
</style>