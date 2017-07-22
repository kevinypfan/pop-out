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
        <app-menu v-if="menu" :menu="menu" @closeMenu="closeMenu"></app-menu>
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
<style>

</style>