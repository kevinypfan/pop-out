<template>
    <nav class="navbar navbar-toggleable-md navbar-light bg-faded">
        <button class="navbar-toggler navbar-toggler-right" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation" @click="menu = !menu" v-if="!menu">
        <span class="navbar-toggler-icon"></span>
        </button>
        <div class="container">
            <router-link to="/">
                <a class="navbar-brand" href="#">Navbar</a>
            </router-link>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav">
                    <router-link to="/user" tag="li" activeClass="active">
                        <a class="nav-link">User</a>
                    </router-link>
                </ul>
            </div>
        </div>
        <transition name="fade">
            <app-menu v-if="menu" :menu="menu" @closeMenu="closeMenu"></app-menu>
        </transition>
    </nav>
</template>
<script>
    import Menu from './Menu.vue'
    export default{
        data(){
            return {
                menu: false
            }
        },
        components:{
            appMenu: Menu
        },
        methods:{
            closeMenu(evt){
                this.menu = evt
            }
        }
    }
</script>
<style scoped>
.fade-enter-active, .fade-leave-active {
  transition: opacity .8s
}
.fade-enter, .fade-leave-to /* .fade-leave-active in below version 2.1.8 */ {
  opacity: 0
}
</style>