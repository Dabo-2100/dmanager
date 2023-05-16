<template>
    <transition name="slide" mode="out-in">
        <div id="SideMenu" v-if="this.$store.state['SideMenuIndex'] == 1">
            <section id="AppInfo">
                <p>dManager</p>
            </section>
            <section id="MenuActions">
                <ul id="Actions">
                    <li v-for="Action in this.Menu_Actions" :key="Action">{{ Action['ArabicName'] }}</li>
                </ul>
            </section>
            <section id="LogOut">
                <p>LogOut</p>
            </section>
        </div>
    </transition>
</template>
  
<script>
// @ is an alias to /src

export default {
    name: 'SideMenu',
    components: {},
    data() {
        return {
            Api_Url: this.$store.state['Api_Url'],
            Menu_Actions: [
                { ArabicName: "الصفحة الرئيسية", Name: "Home", OpenTab: "DashboardView", Icon: "" },
                { ArabicName: "المشتريات", Name: "Purchase", OpenTab: "DashboardView", Icon: "" },
                { ArabicName: "المبيعات", Name: "Sales", OpenTab: "DashboardView", Icon: "" },
                { ArabicName: "المخازن", Name: "Inventory", OpenTab: "DashboardView", Icon: "" },
                { ArabicName: "الحسابات", Name: "Accounting", OpenTab: "DashboardView", Icon: "" },
            ],
        };
    },
    created() { },
    mounted() { },
    computed() { },
    watch: {}
}
</script>
  
<style lang="scss" scoped>
#SideMenu {
    width: 13rem;
    display: flex;
    padding: 3rem 1rem;
    height: 100vh;
    background-color: #2a3042;
    transition: ease all 500ms;
    flex-direction: column;
    flex-wrap: nowrap;
    justify-content: space-between;
    align-items: center;

    #Actions {
        margin: 0;
        padding: 0;

        li {
            list-style: none;
            font-size: 1.2rem;
            color: white;
            padding: 0.5rem 1rem;
        }
    }
}

.slide-enter-active,
.slide-leave-active {
    transition: 300ms;

}

.slide-enter-to {
    position: relative;
    left: 0;
}

.slide-leave {
    position: absolute;
}

.slide-enter {
    left: -100vw;
    position: absolute;
}

.slide-leave-to {
    right: -100vw;
}
</style>
  