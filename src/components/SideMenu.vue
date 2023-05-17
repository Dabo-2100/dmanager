<template>
    <transition name="slide" mode="out-in">
        <div id="SideMenu" v-if="this.$store.state['SideMenuIndex'] == 1">
            <section id="AppInfo">
                <p>dManager</p>
            </section>
            <section id="MenuActions">
                <ul id="Actions">
                    <li v-for="Action in this.Menu_Actions" :key="Action"
                        @click="this.$store.state['CurrentView'] = Action['OpenTab']">{{ Action['ArabicName'] }}</li>
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
                { ArabicName: "المشتريات", Name: "Purchase", OpenTab: "PurchaseView", Icon: "" },
                { ArabicName: "المبيعات", Name: "Sales", OpenTab: "SalesView", Icon: "" },
                { ArabicName: "المخازن", Name: "Inventory", OpenTab: "InventoryView", Icon: "" },
                { ArabicName: "الحسابات", Name: "Accounting", OpenTab: "FinanceView", Icon: "" },
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
            cursor: pointer;
            list-style: none;
            font-size: 1.2rem;
            color: white;
            padding: 0.5rem 1rem;
            transition: all ease 300ms;
        }

        li:hover {
            color: rgba(187, 187, 187, 0.843);

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
  