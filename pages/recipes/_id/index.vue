<template>
  <section class="single-recipe">
    <h1>{{ recipe.title }}</h1>
    <div>
      <img class="recipe-image" :src="recipe.thumnail" :alt="recipe.title" />
    </div>
    <p>{{ recipe.description }}</p>
  </section>
</template>

<script>
export default {
  asyncData(context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe: [
            {
              id: "1",
              title: "The Pizza",
              previewText: "This is Awesome pizza",
              description: "This is realy a delicies meal!!",
              thumnail:
                "https://upload.wikimedia.org/wikipedia/commons/a/a3/Eq_it-na_pizza-margherita_sep2005_sml.jpg"
            },
            {
              id: "2",
              title: "The Hamberger",
              previewText: "This is Awesome hamberger",
              description: "This is realy a delicies meal!!",
              thumnail:
                "https://whatsupdockth.com/wp-content/uploads/2019/09/beef-hamburger.jpg"
            }
          ].find(el => el.id === context.params.id)
        });
      }, 1500);
    });
  }
};
</script>

<style scoped>
.single-recipe {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 30px;
}
.recipe-image {
  width: 100%;
}
</style>