<template>
    <div id="container">
        <textarea 
            v-model="newQuote"
            name="new-quote" 
            id="new-quote" 
            placeholder="What's on your mind ??" 
            cols="120" 
            rows="5">
            </textarea>
        <div class="row" style="width: 80%; margin: 10px auto; display: flex; flex-direction: row; justify-content: flex-end">
            <button class="btn" @click="addQuotes">Add Quote</button>
        </div>
    </div>
</template>

<script>
export default {
  name: "NewQuotes",
  props: {},
  data() {
    return {
      newQuote: ""
    };
  },
  methods: {
    addQuotes() {
      this.$emit("quoteAdded", this.newQuote);
      this.newQuote = "";
    }
  }
};
</script>

<style scoped>
#container {
  background-color: #e9ecef;
  margin: 2rem 0;
  padding: 2rem 0;
  border-radius: 0.3rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
#new-quote {
  width: 80%;
  height: auto;
  padding: 0.5rem;
  margin: 0 auto;
  letter-spacing: 0.1rem;
}
#new-quote:focus {
  outline-color: #3a7f9b;
}
.btn {
  width: 25%;
  height: 10%;
  padding: 0.25rem;
  border: 2px solid #3a7f9b;
  color: #2e2e2e;
  transition: all 450ms;
}
.btn:hover {
  background-color: #3a7f9b;
  color: #fff;
}
.btn:focus {
  outline: 0;
  box-shadow: none;
}
</style>
