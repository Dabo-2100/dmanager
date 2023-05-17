<template>
    <div class="col-12" id="SalesView">
        <h1 class="col-12">This is Sales View</h1>
    </div>
</template>
  
<script>
// @ is an alias to /src

export default {
    name: 'SalesView',
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
#SalesView {
    display: flex;
    width: 100%;
    height: 100%;
    background-color: #f6f6fa
}
</style>
  