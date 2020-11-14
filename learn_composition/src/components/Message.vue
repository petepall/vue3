<template>
  <label>
    <input v-model="message.test" type="text" />
  </label>
  <label>
    <input v-model="message.msgTxt" type="text" />
  </label>
  <input v-model="message.date" type="text" />
</template>

<script>
import { computed } from 'vue';

export default {
  props: {
    modelValue: {
      type: Object,
      default: () => {}
    },
  },

  emits: ['update:modelValue'],

  setup(props, { emit }) {
    const message = computed({
      get: () => props.modelValue,
      set: (value) => emit('update:modelValue', value),
    });

    return {
      message,
    };
  },
};
</script>

<style>
</style>
