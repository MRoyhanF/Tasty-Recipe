<script>
    import NavigationBar from "./NavigationBar.vue";
    export default {
        components: {
            NavigationBar,
        },
    };
</script>

<template>
    <header
        class="shadow-sm bg-white container-fluid bg-white py-3 border-bottom fixed-top"
    >
    <div class="container-md d-flex justify-content-between align-items-center">
        <router-link to="/">
            <img src="@/assets/images/Logo.png" alt="">
        </router-link>
        <navigation-bar></navigation-bar>
    </div>

    </header>
</template>