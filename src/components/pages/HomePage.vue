<script setup>
import RecipeList from "../recipe/RecipeList.vue";
import {onMounted, ref} from 'vue';
import {useStore} from 'vuex';

const store = useStore();
const recipeListStatus = ref(false);
const recipeList = ref([]);

onMounted(async () => {
  try {
    await store.dispatch("recipe/getRecipeData");

    recipeList.value = store.state.recipe.recipes;
    recipeListStatus.value = recipeList.value.length > 0;
  } catch (error) {
    console.log(error);
  }
});

</script>

<template>
  <div class="container-md my-5 py-5">
    <div class="recipe__title text-center">
      <h2>All Recipe</h2>
      <p style="font-size: 15px">Find and share everyday cooking inspiration on All Recipe. Discover recipes, cooks, videos, and how-tos based on the food you love and the friends you follow.</p>
    </div>

    <!-- Pengecekan apakah recipeList kosong -->
    <div v-if="recipeListStatus" class="text-center mt-5">
      <recipe-list :recipes="recipeList"></recipe-list>
    </div>

    <!-- Looping melalui recipeList jika tidak kosong -->
    <div v-else class="text-center mt-5 fw-bold fs-3">
      <p>No recipes available at the moment. Please check back later!</p>
    </div>
  </div>
</template>
