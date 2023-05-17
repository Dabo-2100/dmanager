<template>
    <div id="WorkingArea" class="col-12" :style="'height :calc(100vh - ' + this.$store.state['CurrentNavHieght'] + 'px);'">
        <component :is="this.$store.state['CurrentView']"></component>
    </div>
</template>
  
<script>
import DashboardView from "@/views/DashboardView.vue";
import PurchaseView from "@/views/PurchaseView.vue";
import SalesView from "@/views/SalesView.vue";
import InventoryView from "@/views/InventoryView.vue";
import FinanceView from "@/views/FinanceView.vue";
// @ is an alias to /src

export default {
    name: 'WorkingArea',
    components: { DashboardView, SalesView, InventoryView, PurchaseView, FinanceView },
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
#WorkingArea {
    display: flex;
    width: 100%;
    overflow-y: auto;
}
</style>
  