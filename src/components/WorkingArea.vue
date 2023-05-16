<template>
    <div id="WorkingArea" class="col-12" :style="'height :calc(100vh - ' + this.$store.state['CurrentNavHieght'] + 'px);'">
        <component :is="'DashboardView'"></component>
    </div>
</template>
  
<script>
import DashboardView from "@/views/DashboardView.vue";
// @ is an alias to /src

export default {
    name: 'WorkingArea',
    components: { DashboardView },
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
  