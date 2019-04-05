<template>
    <div class="container">
        <abbr title="Click To delete">
          <div v-for="(quote, index) in quotes" :key="index" class="quote-body" @click="quoteDeleted(index)">
          <p>{{ quote }}</p>
        </div>
        </abbr>
    </div>
</template>

<script>
export default {
  name: "ShowQuotes",
  props: {
    quotes: Array
  },
  data() {
    return {
      isVisible: false
    };
  },
  methods: {
    quoteDeleted(data) {
      this.$emit("quoteDeleted", data);
    }
  }
};
</script>

<style scoped>
.container {
  background: #e9ecef;
  height: auto;
  padding: 20px;
}
.quote-body {
  width: 100%;
  padding: 10px;
  margin: 0 0 10px 0;
  background: #fff;
  border-left: 5px solid burlywood;
  cursor: pointer;
  font-family: "Patrick Hand", cursive;
  font-weight: 500;
  font-size: 1.5rem;
  border-radius: 5px;
}
abbr[title] {
  text-decoration: none !important;
}
p {
  margin-top: 0;
  margin-bottom: 0;
}
</style>
