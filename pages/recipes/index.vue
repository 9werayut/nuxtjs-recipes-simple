<template>
  <section class="recipes">
    <Recipe
      v-for="recipe in recipes"
      :key="recipe.id"
      :thumnail="recipe.thumnail"
      :title="recipe.title"
      :previewText="recipe.previewText"
      :id="recipe.id"
    />
  </section>
</template>

<script>
import Recipe from "@/components/Recipe";
export default {
  components: {
    Recipe
  },
  asyncData() {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipes: [
            {
              id: "1",
              title: "The Pizza",
              previewText: "This is Awesome pizza",
              thumnail:
                "https://upload.wikimedia.org/wikipedia/commons/a/a3/Eq_it-na_pizza-margherita_sep2005_sml.jpg"
            },
            {
              id: "2",
              title: "The Hamberger",
              previewText: "This is Awesome hamberger",
              thumnail:
                "https://whatsupdockth.com/wp-content/uploads/2019/09/beef-hamburger.jpg"
            }
          ]
        });
      }, 1500);
    });
  }
};
</script>

<style scoped>
.recipes {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  align-items: center;
}
</style>