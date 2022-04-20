<template>
    <section class="team-image">
<!--        <img src="images/team-image.png" alt="">-->
        <div class="image"></div>
    </section>
</template>

<script>
export default {
    name: "TeamImage"
}
</script>

<style scoped>
.team-image {
    width: 100%;
    height: 400px;
}
.image {
    height: 100%;
    background-image: url("../../images/team-image.png");
    background-attachment: fixed;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
}
</style>
