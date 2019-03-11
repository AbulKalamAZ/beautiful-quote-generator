<template>
    <div class="quote">
        <div class="title">
            <slot name="title"></slot>
        </div>
        <div class="author">
            <slot name="author">-author's unknown</slot>
        </div>
    </div>
</template>

<script>
export default {
  name: "Quote"
};
</script>

<style scoped>
.quote {
  width: 100%;
  border: 1px solid #cccccc;
  margin: 30px auto;
  padding: 30px;
  box-shadow: 7px 7px 20px #2e2e2e;
}
.title {
  text-transform: capitalize;
  font-weight: 300;
  color: #2e2e2e;
  word-spacing: 2px;
}
.author {
  font-style: italic;
  padding-left: 5px;
}
</style>
