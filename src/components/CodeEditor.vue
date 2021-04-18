<template>
  <div class="code-editor-container">
    <textarea
      class="code-area"
      :value="modelValue"
      @mouseup="emitSelection"
      @input="$emit('update:modelValue', $event.target.value)"
    ></textarea>
  </div>
</template>
<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'CodeEditor',
  props: {
    modelValue: {
      type: String,
      required: false,
      default: '',
    },
  },
  setup() {
    function emitSelection(event: Event) {
      console.log(event);
    }
    return {
      emitSelection,
    };
  },
});
</script>
<style scoped>
.code-area {
  height: 100%;
  width: 100%;
  resize: none;
  margin: 0;
  padding: 1rem;
  -webkit-box-shadow: none;
  -moz-box-shadow: none;
  box-shadow: none;
  border: none;
  overflow: auto;
  outline: none;
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
