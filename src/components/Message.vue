<template>
  <div class="container">
    <div
      v-for="(message, index) in messages"
      :key="index"
      class="messageUser"
      :class="{'align-left': message.aligne === 'left', 'align-right': message.aligne === 'right'}"
    >
      <p>{{ message.name }}</p>
      <p class="pmessage" :style="{ backgroundColor: message.color }">{{ message.text }}</p>
    </div>
  </div>
</template>


<script>
export default {
  name: 'Message',
    props:{
        messages: Array,

    },
};
</script>

<style scoped>
.container {
  height: 550px;
  width: 25%;
  margin: 5px;
  border: 2px solid #b8bab9;
  background-color: #d7dbd8;
  overflow-y: auto;
  padding-top: 15px;
  display: flex;
  flex-direction: column;
  gap: 5px;
}

.messageUser {
  display: flex;
  flex-direction: column;
  gap: 5px;
  max-width: 70%;
}

.align-left {
  align-self: flex-start; 
}

.align-right {
  align-self: flex-end; 
}

.pmessage {
  width: max-content;
  padding: 10px;
  border-radius: 25px;
}

p {
  margin: 2px 0;
  padding-left: 2px;
}
</style>