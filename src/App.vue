<template>
  <h1 class="title">Markdown Preview</h1>
  <div class="markdown-preview-grid">
    <Editor class="grid-item" v-model="code" />
    <div class="preview-area grid-item" v-html="preview"></div>
  </div>
</template>

<script lang="ts">
import { computed, defineComponent, ref } from 'vue';
import marked from 'marked';

import Editor from '@/components/CodeEditor.vue';

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

<style scope>
.markdown-preview-grid {
  width: min(100%, 900px);
  display: flex;
  justify-content: space-between;
  height: 90%;
}
.grid-item {
  width: 46%;
  height: 90%;
}
.preview-area {
  background-color: var(--colour-light-shade-default);
  padding: 1rem;
  margin: 0;
}
</style>
