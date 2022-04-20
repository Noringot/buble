<template>
    <BaseLayout >
        <Hero />
        <Blot />
        <About />
        <TeamImage />
        <Slider />
        <Scroll />
    </BaseLayout>
</template>

<script>
import BaseLayout from "@/Layouts/BaseLayout";
import Hero from "@/Components/Hero";
import About from "@/Components/About";
import TeamImage from "@/Components/TeamImage";
import Blot from "@/Components/Blot";
import Slider from "@/Components/Slider";
import Scroll from "@/Components/ProgessScroll";

export default {
    name: "Index",
    components: {
        BaseLayout,
        Hero,
        About,
        TeamImage,
        Blot,
        Slider,
        Scroll,
    },
}
</script>

<style scoped>


</style>
