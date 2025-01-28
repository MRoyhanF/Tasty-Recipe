<template>
    <div class="col-12 col-sm-8">
        <RecipeDescription/>
        <RecipeIngredients/>
        <RecipeDirections/>
    </div>
</template>

<script setup>
import { onMounted } from "vue";
import RecipeDescription from "./RecipeDescription.vue";
import RecipeIngredients from "./RecipeIngredients.vue";
import RecipeDirections from "./RecipeDirections.vue";

onMounted(async () => {
    try {
        await store.dispatch(
            "recipe/getRecipeDetail",
            route.params.id
        );
    } catch (error) {
        console.log(error);
    }
});

</script>
