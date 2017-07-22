<template>
   <section>
        <app-navbar></app-navbar>
        <div class="container">
            <router-view></router-view>
        </div>
        
   </section>
</template>

<script>
    import Navbar from './components/nav/Navbar.vue'
    export default {
      name: 'app',
      data () {
        return {
            
        }
      },
        components:{
            appNavbar: Navbar
        }
    }
</script>

<style>

</style>
