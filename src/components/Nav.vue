<template>
  <nav
    :style="{
      backgroundColor: mode.nav,
      borderBottom: `1px solid ${mode.text}`,
    }"
  >
    <p>Reactive code</p>
    <button
      :style="{ backgroundColor: mode.button, color: mode.text }"
      @click="modeChange()"
    >
      {{ mode.name }}
    </button>
  </nav>
</template>

<script>
export default {
  name: "Nav",
  computed: {
    mode() {
      return this.$store.state.mode;
    },
  },
  methods: {
    modeChange() {
      this.$store.commit("modeChange");
    },
  },
};
</script>

<style scoped>
nav {
  padding: 0.7vh;
  display: flex;
  justify-content: space-between;
}
button {
  border: none;
  padding-left: 30px;
  padding-right: 30px;
  border-radius: 10px;
  font-weight: bolder;
  font-size: 2vh;
  transition: 0.1s ease;
}
nav p {
  font-weight: bolder;
  font-size: 4vh;
  user-select: none;
}
nav p:hover {
  cursor: pointer;
}
</style>
