<script>
import User from "./components/User.vue";
import Message from "./components/Message.vue";

export default {
  name: "App",
  components: {
    User,
    Message,
  },
  data() {
    return {
      messages: [], 
    };
  },
  methods: {
    handleSend(message) {
      this.messages.push(message); 
    },
  },
};
</script>

<template>
  <div class="container">
    <User position="left" @send="handleSend" />
    <Message :messages="messages" />
    <User position="right" @send="handleSend" />
  </div>
</template>

<style scoped>
.container {
  display: flex;
  justify-content: space-between;
  align-items: flex-start; 
  width: 100%; 
  max-width: 1280px;
  margin: auto;
  padding: 10px;
  gap: 15px;
}
</style>