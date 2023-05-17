<template>
    <div class="col-12" id="InventoryView">
        <!-- CURD -->
        <div class="col-12 SubNav">
            <button class="btn btn-primary">ادارة المخازن</button>
            <button class="btn btn-primary">ادارة المخزون</button>
            <button class="btn btn-primary">طلبات السحب </button>
            <button class="btn btn-primary">اذونات الاضافة</button>
            <button class="btn btn-primary">طلبات الاضافة</button>
        </div>

        <div class="col-12 Widget" id="ShowAllStores">

        </div>
    </div>
</template>
  
<script>
// @ is an alias to /src

export default {
    name: 'InventoryView',
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
#InventoryView {
    display: flex;
    width: 100%;
    height: 100%;
    background-color: #f6f6fa;
    flex-direction: row;
    flex-wrap: wrap;
    align-content: flex-start;
    justify-content: flex-start;
    align-items: flex-start;

    .SubNav {
        padding: 1rem;
        background-color: bisque;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        align-content: center;
        justify-content: space-evenly;
        align-items: center;
    }

}
</style>
  