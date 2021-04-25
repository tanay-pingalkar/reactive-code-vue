<template>
  <div :style="{ color: color }">
    <Nav />
    <div class="flex">
      <Input />
      <Output />
    </div>
  </div>
</template>

<script>
import Input from "./components/Input";
import Output from "./components/output";
import Vuex from "vuex";
import Vue from "vue";
import Nav from "./components/Nav";

Vue.use(Vuex);
const store = new Vuex.Store({
  state: {
    raw: "",
    mode: {
      name: "night",
      nav: "rgb(0, 0, 51)",
      editor: "rgb(0, 0, 26)",
      button: "rgb(0, 0, 128)",
      text: "white",
    },
  },
  mutations: {
    change(state, str) {
      state.raw = str;
    },
    modeChange(state) {
      if (state.mode.name === "night") {
        state.mode = {
          name: "day",
          editor: "lightgray",
          nav: "white",
          button: "yellow",
          text: "black",
        };
      } else {
        state.mode = {
          name: "night",
          nav: "rgb(0, 0, 51)",
          editor: "rgb(0, 0, 26)",
          button: "rgb(0, 0, 128)",
          text: "white",
        };
      }
    },
  },
});
export default {
  name: "App",
  components: {
    Input,
    Output,
    Nav,
  },
  store: store,
  computed: {
    color() {
      return this.$store.state.mode.text;
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300&display=swap");
* {
  font-family: "Poppins", sans-serif;
  padding: 0;
  margin: 0;
}

.flex {
  display: flex;
  width: 100%;
  height: 100%;
}
</style>
