<template>
    <header class="header">
        <div class="container">
            <div class="header__wrapper flex justify-between">
                <div class="header__year">2021*</div>
                <div class="header__column flex">
                    <div class="header__lang">
                        <span class="lang-active">EN</span>
                        <span class="slash">/</span>
                        <span>RU</span>
                    </div>
                    <div class="header__year">2022</div>
                </div>
            </div>
        </div>
    </header>
</template>

<script>
export default {
    name: "Header"
}
</script>

<style scoped>

.header {
    font-family: 'Open Sans';
    color: #303435;
    padding: 26px 0;
}
.header__year {
    font-size: 42px;
    font-weight: 800;
}
.header__lang {
    font-size: 20px;
}
.slash,
.lang-active {
    color: #FFF;
}

</style>
