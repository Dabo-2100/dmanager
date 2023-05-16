<template>
    <div class="col-12" id="DashboardView">
        <h1 class="col-12">This is Dashboard View</h1>
    </div>
</template>
  
<script>
// @ is an alias to /src

export default {
    name: 'DashboardView',
    components: {},
    data() {
        return {
            Api_Url: this.$store.state['Api_Url'],
        };
    },
    created() { },
    mounted() { },
    computed() { },
    watch: {}
}
</script>
  
<style lang="scss" scoped>
#DashboardView {
    display: flex;
    width: 100%;
    height: 100%;
    background-color: #f6f6fa
}
</style>
  