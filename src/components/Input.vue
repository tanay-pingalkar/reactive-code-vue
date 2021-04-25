<template>
  <textarea
    @input="set"
    :style="{ backgroundColor: bg.editor, color: bg.text }"
  ></textarea>
</template>

<script>
export default {
  name: "Input",
  methods: {
    set(event) {
      this.$store.commit("change", event.target.value);
    },
  },
  computed: {
    bg() {
      return this.$store.state.mode;
    },
  },
};
</script>

<style scoped>
textarea {
  width: 50%;
  height: 91vh;
  padding: 5px;
  border: none;
  outline: none;
}
</style>
