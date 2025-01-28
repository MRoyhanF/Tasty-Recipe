<template>
    <main>
        <div class="container-md my-5 py-5" >
            <div class="row my-4">
                <div class="col-12 col-sm-2" ></div>
                <!-- <recipe-detai></recipe-detai> -->
                <RecipeDetail />    
                <div class="col-12 col-sm-2" ></div>
            </div>
        </div>
    </main>
</template>

<script setup>
    import RecipeDetail from "../detail/RecipeDetail.vue";
    import { onMounted } from "vue";
    import { useRoute } from "vue-router";
    import { useStore } from "vuex";
    import RecipeDescription from "../detail/RecipeDescription.vue";

    const store = useStore();
    const route = useRoute();

    onMounted(async () => {
        try {
            await store.dispatch(
                "recipe/getRecipeDetail", route.params.id
            );
        } catch (error) {
            console.log(error);
        }
    });
</script>