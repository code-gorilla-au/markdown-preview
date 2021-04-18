<template>
  <h1>Markdown Preview</h1>
  <input v-model.lazy="code" />
  <p v-html="preview"></p>
</template>

<script lang="ts">
import { computed, defineComponent, ref } from 'vue';
import marked from 'marked';

export default defineComponent({
  name: 'App',
  components: {},
  setup() {
    const code = ref('');
    const preview = computed(() => {
      return marked(code.value);
    });
    return {
      code,
      preview,
    };
  },
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
