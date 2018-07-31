<template>
    <section class="wrapper">
        <app-header />
        <app-topmenu />
        <app-breadcrumbs />
        <div>
            <h1>Корзина</h1>
            <div class="">
                <div>
                    <span>Выделено <span class="bold">45</span></span>
                </div>
                <div class="deleteSelectedBtn">Удалить отмеченные</div>
            </div>
            <table class="cart">                
                <tbody>
                    <tr v-for="item in allItems" :key="item.id">
                        <td>{{item.id}}</td>
                        <td>{{item.img}}</td>
                        <td>{{item.description}}</td>
                        <td>{{item.price}}</td>
                        <td>+</td>
                        <td><input type="text" /></td>
                        <td>=</td>
                        <td>total price</td>
                    </tr>
                </tbody>
            </table>
            <div>
                test json
            </div>
        </div>
    </section>
</template>

<script>
    import AppLogo from '~/components/AppLogo.vue'
    import AppHeader from '~/components/AppHeader.vue'
    import AppTopmenu from '~/components/AppTopmenu.vue'
    import AppBreadcrumbs from '~/components/AppBreadcrumbs.vue'

    const axios = require('axios');

    export default {
        components: {
            AppLogo,
            AppHeader,
            AppTopmenu,
            AppBreadcrumbs
        },
        data: () => ({
            items: null
        }),
        mounted() {
            axios
                .get('http://www.json-generator.com/api/json/get/bTyrMoBGYy?indent=2')
                .then(response => {
                    if (response.status === 200) {
                        this.items = response.data;
                    } else {
                        throw new Error("Error");
                    }
                }).catch(error=>{
                    console.log(error);
                });
        },
        computed: {
            allItems: function() {
                return this.items;
            }
        }
    }
</script>

<style>
    @import "~/css/main.scss";

    .wrapper {
        width: 1000px;
        margin: 0 auto;
    }
    .cart {
        width: 100%;
    }
    .cart th{
        background: #ccc;
    }
    .deleteSelectedBtn {
        float: right;
        margin-right: 10px;
    }
</style>

