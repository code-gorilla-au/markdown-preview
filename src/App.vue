<template>
  <h1 class="text-4xl">Markdown Preview</h1>
  <div class="container">
    <Editor v-model="code" />
    <p class="preview-area border-2" v-html="preview"></p>
  </div>
</template>

<script lang="ts">
import { computed, defineComponent, ref } from 'vue';
import marked from 'marked';

export default defineComponent({
  name: 'App',
  components: { Editor },
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

<style></style>
