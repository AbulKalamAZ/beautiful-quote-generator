<template>
    <div class="header">
        <h3>Quotes Added: {{ numberOfQuotes }} / {{ maxNumberOfQuotes}}</h3>
        <hr>
        <div class="quotes-bar">
            <div 
            class="inner-quotes-bar"
            style="background-color: #3a7f9b; height: 100%; border-radius: 5px; transition: all 450ms"
            :style="{width: numberOfQuotes / maxNumberOfQuotes * 100 + '%'}"
            ></div>
        </div>
    </div>
</template>

<script>
export default {
  name: "Header",
  props: ["numberOfQuotes", "maxNumberOfQuotes"],
  methods: {}
};
</script>

<style scoped>
.header {
  background-color: #e9ecef;
  width: 100%;
  padding: 2rem;

  border-radius: 0.3rem;
}
.quotes-bar {
  width: 100%;
  height: 30px;
  background-color: #8e9395;
  border-radius: 5px;
}
</style>
