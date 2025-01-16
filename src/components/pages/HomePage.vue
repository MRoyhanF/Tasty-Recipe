<script>
import RecipeList from "../recipe/RecipeList.vue";
export default {
  components: {
    RecipeList,
  },
};
</script>

<template>
  <div class="container-md my-5 py-5">
    <div class="recipe__title text-center">
      <h2>All Recipe</h2>
      <p style="font-size: 15px">Lorem ipsum dolor sit amet consectetur adipisicing elit. Eius magni voluptates cumque accusantium labore maiores, itaque saepe rerum eos dicta?</p>
    </div>
    <recipe-list></recipe-list>
  </div>
</template>
