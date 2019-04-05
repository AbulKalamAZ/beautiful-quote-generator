<template>
  <div class="container">
    <app-header 
    :numberOfQuotes="quotes.length" 
    :maxNumberOfQuotes="maxNumberOfQuotes"
    >
    </app-header>
    <app-new-quotes 
    @quoteAdded="quoteAdded($event)"
    ></app-new-quotes>
    <app-show-quotes
    v-if="isVisible"
    @quoteDeleted="quoteDeleted($event)"
    :quotes="quotes"></app-show-quotes>
  </div>
</template>

<script>
import Header from "./components/Header";
import NewQuotes from "./components/NewQuotes";
import ShowQuotes from "./components/ShowQuotes";

export default {
  name: "App",
  components: {
    appHeader: Header,
    appNewQuotes: NewQuotes,
    appShowQuotes: ShowQuotes
  },
  data() {
    return {
      quotes: [],
      maxNumberOfQuotes: 5,
      isVisible: false
    };
  },
  methods: {
    quoteAdded(data) {
      if (this.quotes.length < this.maxNumberOfQuotes) {
        this.quotes.push(data);
        this.isVisible = true;
      } else {
        alert("You can not add more quotes!!");
      }
    },
    quoteDeleted(data) {
      this.quotes.splice(data, 1);
      if (this.quotes.length == 0) {
        this.isVisible = false;
      }
    }
  }
};
</script>

<style>
</style>

