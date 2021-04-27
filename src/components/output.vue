<template>
  <div v-html="raw"></div>
</template>

<script>
export default {
  name: "Output",
  computed: {
    raw() {
      return this.$store.state.raw;
    },
  },
};
</script>

<style scoped>
div {
  width: 50%;
  height: 92vh;
  overflow: scroll;
  padding: 2px;
  color: black;
}
</style>
