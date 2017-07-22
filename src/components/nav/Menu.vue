<template>
    <div class="mobile-menu">
        <div class="mask">
            <div class="menu-title" @click="closeMenu">
            </div>
            <ul class="menu-list">
                <li class="menu-item"><a href="">Home</a></li>
                <li class="menu-item"><a href="">User</a></li>
                <li class="menu-item"><a href="">List</a></li>
                <li class="menu-item"><a href="">list</a></li>
            </ul>
        </div>
    </div>
</template>
<script>
    export default{
        props: ['menu'],
        methods:{
            closeMenu(){
                this.$emit('closeMenu',false)
            }
        }
    }
</script>
<style>
.menu-title {
  position: absolute;
  top: 0px;
  right: 0px;
  height: 50px;
  width: 50px;
  cursor: pointer;
}
.menu-title:hover:after, .menu-title:hover:before {
  background-color: rgba(255, 255, 255, 0.4);
}
.menu-title:after, .menu-title:before {
  content: "";
  display: block;
  position: absolute;
  height: 3px;
  width: 50%;
  background-color: #fff;
}
.menu-title:after {
  top: 50%;
  left: 50%;
  -webkit-transform: translate(-50%, -50%) rotate(45deg);
          transform: translate(-50%, -50%) rotate(45deg);
}
.menu-title:before {
  top: 50%;
  left: 50%;
  -webkit-transform: translate(-50%, -50%) rotate(-45deg);
          transform: translate(-50%, -50%) rotate(-45deg);
}

.mask {
  position: absolute;
  background-color: rgba(6, 49, 86, 0.9);
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  text-align: center;
}
.mask .menu-list {
  padding: 0;
  margin: 0;
  list-style: none;
  position: absolute;
  top: 50%;
  left: 50%;
  -webkit-transform: translate(-50%, -50%);
          transform: translate(-50%, -50%);
}
.mask .menu-list .menu-item {
  padding: 10px 150px;
  border-bottom: #0e4975 1px solid;
}
.mask .menu-list .menu-item a {
  color: #fff;
  font-size: 24px;
}

</style>