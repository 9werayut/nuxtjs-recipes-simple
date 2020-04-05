<template>
  <nuxt-link :to="'/recipes/' + id">
    <article class="recipe">
      <div class="thumnail" :style="{ backgroundImage: `url('${ thumnail}')`}"></div>
      <h1>{{ title }}</h1>
      <p>{{ previewText }}</p>
    </article>
  </nuxt-link>
</template>

<script>
export default {
  props: ["thumnail", "title", "previewText", "id"]
};
</script>

<style scope>
a {
  text-decoration: none;
  color: black;
}
.recipe {
  box-sizing: border-box;
  width: 280px;
  padding: 8px;
  border: 1px solid #ccc;
  box-shadow: 0 2px 2px #eee;
  margin: 10px;
}

.thumnail {
  background-position: center;
  background-size: cover;
  width: 100%;
  height: 200px;
}
</style>