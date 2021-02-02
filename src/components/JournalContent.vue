<template>
  <div class="journal-content" v-html="markdownHtml(content)" />
</template>

<script>
import MarkdonwIt from "markdown-it";
const md = new MarkdonwIt();
export default {
  props: {
    content: String,
  },
  methods: {
    markdownHtml(markdown) {
      return md.render(markdown);
    },
  },
};
</script>

<style>
p {
  line-height: 1.5;
  font-size: 1.15rem;
}
h2 {
  font-size: 2rem;
}
h3 {
  font-size: 1.5rem;
}
h4,
h5,
h6 {
  font-size: 1.15rem;
}
</style>
