<template>
  <section class="single-recipe">
    <h1>Title {{ recipe.title }}</h1>
    <div>
      <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title">
    </div>
    <p>{{ recipe.descriptionText }}</p>
  </section>
</template>

<script>
import Recipe from '@/components/Recipe'
export default {
  components: {
    Recipe
  },
  asyncData(context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe: [
            {
              id: "1",
              title: "Title A",
              previewText: "Description A",
              descriptionText: "Long Description A",
              thumbnail: "https://res.cloudinary.com/grohealth/image/upload/v1583764330/DCUK/Content/iStock-680111050.jpg"
            },
            {
              id: "2",
              title: "Title B",
              previewText: "Description B",
              descriptionText: "Long Description B",
              thumbnail: "https://ik.imagekit.io/grgdihc3l/crm/simpleview/image/upload/w_1440,h_900,c_fit/crm/miamifl/Food_1440x9000_df5550c2-5056-a36a-0b8705afe2fb9d3b.jpg"
            }
          ].find(el => el.id === context.params.id)
        })
      }, 0)
    })
  }
}
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