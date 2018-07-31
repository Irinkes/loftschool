<template>
    <div class="menu">
        <ul>
            <li><a href="">Каталог продукции</a></li>
            <li>Все бренды</li>
            <li>Подарки на 14 февраля</li>
            <li>Подарки на 23 февраля</li>
            <li>Подарки на 8 марта</li>
        </ul>
    </div>
</template>
<script>
    // import AppLogo from '~/components/AppLogo.vue'
    // import AppSearch from '~/components/AppSearch.vue'
    //
    // export default {
    //     components: {
    //         AppLogo,
    //         AppSearch
    //     }
    // }
</script>
<style>
    .menu {
        margin-top: 50px;
        overflow: hidden;
    }
    .menu ul li {
        list-style: none;
        float: left;
        padding: 10px;
    }
    .menu ul li:first-child {
        padding-left: 0;
    }
</style>