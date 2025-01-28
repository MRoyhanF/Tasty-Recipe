<template>
    <div class="col-12 col-sm-8">
        <recipe-description></recipe-description>
    </div>
</template>

<script setup>
import { onMounted } from "vue";
import RecipeDescription from "./RecipeDescription.vue";

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
