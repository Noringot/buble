<template >
    <Header />
    <main class="main" ><slot /></main>
</template>

<script>
import Header from "@/Components/Header";

export default {
    name: "BaseLayout",
    components: {
        Header,
    }
}
</script>

<style scoped>

</style>
