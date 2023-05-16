<template>
    <div class="col-12" id="HomeView" @click="this.$store.state['NotificationsMenuIndex'] = 0">
        <SideMenu />
        <div class="Row">
            <MainNav />
            <WorkingArea />
        </div>
    </div>
</template>
  
<script>
import MainNav from '@/components/MainNav.vue';
import SideMenu from "@/components/SideMenu.vue";
import WorkingArea from "@/components/WorkingArea.vue";

// @ is an alias to /src
export default {
    name: 'HomeView',
    components: { MainNav, SideMenu, WorkingArea },
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
#HomeView {
    direction: rtl;
    height: 100vh;
    width: 100%;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    align-content: flex-start;
    justify-content: flex-start;
    align-items: flex-start;

    .Row {
        height: 100vh;
        flex-grow: 1;
        background-color: green;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        align-content: flex-start;
        justify-content: flex-start;
        align-items: flex-start;
    }
}
</style>
  