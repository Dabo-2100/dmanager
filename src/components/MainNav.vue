<template>
    <nav class="col-12" id="MainNav">
        <section id="NavActions">
            <font-awesome-icon id="SideMenuIcon" icon="fa-solid fa-bars" @click="ChangeSideMenuStyle()" />
            <div id="SearchBar">
                <font-awesome-icon icon="fa-solid fa-magnifying-glass" id="SearchIcon" />
                <input type="search" placeholder="بحث عن عميل" />
            </div>
        </section>
        <section id="UserActions">
            <div id="Notifications" @click="this.OpentMenu(); $event.stopPropagation()">
                <font-awesome-icon id="NotificationsIcon" icon="fa-regular fa-bell" />
                <span id="NotificationsCount">4</span>
                <div id="NotificationsMenu" :hidden="this.$store.state['NotificationsMenuIndex'] == 1 ? false : true"
                    :style="this.$store.state['NotificationsMenuIndex'] == 0 ? `top:3.5rem;` : ''">
                    <div class="col-12">This is Notification 1</div>
                    <div class="col-12">This is Notification 2</div>
                    <div class="col-12">This is Notification 3</div>
                </div>
            </div>

        </section>
    </nav>
</template>
  
<script>
// @ is an alias to /src

export default {
    name: 'MainNav',
    components: {},
    data() {
        return {
            Api_Url: this.$store.state['Api_Url'],
        };
    },
    created() { },
    mounted() {
        this.$store.state['CurrentNavHieght'] = document.getElementById('MainNav').clientHeight;
    },
    methods: {
        ChangeSideMenuStyle() {
            if (this.$store.state['SideMenuIndex'] == 0) {
                this.$store.state['SideMenuIndex'] = 1;
            }
            else if (this.$store.state['SideMenuIndex'] == 1) {
                this.$store.state['SideMenuIndex'] = 0;
            }
        },
        OpentMenu() {
            this.$store.state['NotificationsMenuIndex'] = 1;
            setTimeout(() => {
                $("#NotificationsMenu").css('top', '2.5rem');
                // $("#NotificationsMenu").css('transform', 'translate(0px, -1rem)');
            }, 50);
        }
    },
    computed() { },
    watch: {}
}
</script>
  
<style lang="scss" scoped>
#MainNav {
    display: flex;
    width: 100%;
    padding: 1rem 2%;
    background-color: white;
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: space-between;
    align-items: center;
    box-shadow: 0px 1px 1px #929292;
    z-index: 1;

    #NavActions {
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        align-content: center;
        justify-content: flex-start;
        align-items: center;

        #SideMenuIcon {
            height: 1.2rem;
            width: 1.2rem;
            cursor: pointer;
        }

        #SearchBar {
            display: flex;
            background: #f3f3f9;
            padding: 0.5rem;
            border-radius: 2rem;
            margin: 0 0.5rem;
            position: relative;
            flex-direction: row;
            flex-wrap: wrap;
            align-content: center;
            justify-content: center;
            align-items: center;
            cursor: pointer;

            #SearchIcon {
                height: 1.2rem;
                width: 1.2rem;
                position: absolute;
                right: 1rem;
                cursor: pointer;
            }

            input {
                color: black;
                border: 0;
                background-color: transparent;
                font-size: 1rem;
                padding: 0.25rem 2rem;
                outline: 0;
                cursor: pointer;
            }
        }

    }

    #UserActions {
        display: flex;

        #Notifications {
            display: flex;
            background: #f3f3f9;
            padding: 0.5rem;
            border-radius: 50%;
            margin: 0 0.5rem;
            position: relative;
            flex-direction: row;
            flex-wrap: wrap;
            align-content: center;
            justify-content: center;
            align-items: center;
            cursor: pointer;

            #NotificationsIcon {
                height: 1.5rem;
                width: 1.5rem;
            }

            #NotificationsCount {
                position: absolute;
                border-radius: 50%;
                padding: 0.2rem 0.4rem;
                background-color: #621919;
                color: white;
                top: -0.5rem;
                left: -0.25rem;
                font-size: 0.6rem;
            }

            #NotificationsMenu {
                transition: all ease 200ms;
                position: absolute;
                background-color: #f3f4f9;
                color: black;
                top: 3.5rem;
                left: 0;
                padding: 1rem;
                box-shadow: 1px 1px 1px black;
                display: flex;
                flex-direction: row;
                flex-wrap: wrap;
                align-content: flex-start;
                justify-content: flex-start;
                align-items: flex-start;
                width: 15rem;
                border-radius: 0.25rem;
            }
        }
    }
}
</style>
  