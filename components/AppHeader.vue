<template>
    <div class="header">
        <app-logo/>
        <app-search />
    </div>
</template>
<script>
    import AppLogo from '~/components/AppLogo.vue'
    import AppSearch from '~/components/AppSearch.vue'

    export default {
        components: {
            AppLogo,
            AppSearch
        }
    }
</script>
<style>
    .header {
        margin-top: 50px;
        overflow: hidden;
    }
</style>