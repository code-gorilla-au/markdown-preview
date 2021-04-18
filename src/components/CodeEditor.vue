<template>
  <div class="code-editor-container">
    <textarea
      class="code-area"
      :value="modelValue"
      @input="$emit('update:modelValue', $event.target.value)"
    ></textarea>
  </div>
</template>
<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Editor',
  props: {
    modelValue: {
      type: String,
      required: false,
      default: '',
    },
  },
  setup() {},
});
</script>
<style scoped>
.code-area {
  height: 100%;
  width: 100%;
  resize: none;
  margin: 0;
  -webkit-box-shadow: none;
  -moz-box-shadow: none;
  box-shadow: none;
  border: none;
  overflow: auto;
  outline: none;
  padding: 1rem;
}
.code-area:focus {
  border: none;
  overflow: auto;
  outline: none;

  -webkit-box-shadow: none;
  -moz-box-shadow: none;
  box-shadow: none;
}
</style>
