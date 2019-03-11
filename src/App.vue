<template>
  <div class="container">
    <button @click="con('appQuote')">Quote</button>
    <button @click="con('appAuthor')">Author</button>
    <button @click="con('appNew')">New</button>
    <hr>
    <component v-bind:is="selectedComponent"></component>
  </div>
</template>

<script>
import Quote from "./components/Quote";
import Author from "./components/Author";
import New from "./components/New";

export default {
  components: {
    app: "Quote",
    appAuthor: "Author",
    appNew: "New"
  },
  data() {
    return {
      selectedComponent: "appQuote"
    };
  },
  methods: {
    con(data) {
      this.selectedComponent = data;
    }
  }
};
</script>

<style>
</style>

