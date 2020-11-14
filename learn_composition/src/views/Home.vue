<template>
  <h1>{{ message.test }} and {{ message.msgTxt }}</h1>
  <h2>Current date is: {{ message.date }}</h2>
  <!-- <h1>{{ message }}</h1> -->
  <Message v-model="message" />
</template>

<script>
import Message from '@/components/Message.vue';

import { reactive } from 'vue';
// import { ref } from 'vue';

export default {
  name: 'Home',
  components: { Message },

  setup() {
    const message = reactive({
      test: '123',
      msgTxt: 'Test of object',
      date: Date.now()
    });
    // const message = ref('123');

    return {
      message,
    };
  },
};
</script>
