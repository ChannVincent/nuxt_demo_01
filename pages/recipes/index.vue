<template>
  <section class="recipes">
    
    <Recipe 
      v-for="recipe in recipes"
      :key="recipe.id"
      :thumbnail="recipe.thumbnail"
      :title="recipe.title"
      :previewText="recipe.previewText"
      :id="recipe.id"/>
 
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
          recipes: [
            {
              id: "1",
              title: "Title A",
              previewText: "Description A",
              thumbnail: "https://res.cloudinary.com/grohealth/image/upload/v1583764330/DCUK/Content/iStock-680111050.jpg"
            },
            {
              id: "2",
              title: "Title B",
              previewText: "Description B",
              thumbnail: "https://ik.imagekit.io/grgdihc3l/crm/simpleview/image/upload/w_1440,h_900,c_fit/crm/miamifl/Food_1440x9000_df5550c2-5056-a36a-0b8705afe2fb9d3b.jpg"
            }
          ]
        })
      }, 1500)
    })
  }
}

</script>

<style scoped>
.recipes {
  display: flex;
  flex-flow: row;
  justify-content: center;
  align-items: center;
}
</style>