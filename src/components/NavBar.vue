<template>
  <div id="nav-bar">
    <div id="container">
      <div id="left">
        <DropDownMenu class="drop-down-menu"/>
      </div>
      <div id="right"></div>
      <div id="center"><a class="site-title">Pizza 42</a></div>
    </div>
  </div>
</template>

<script>

import DropDownMenu from '@/components/DropDownMenu.vue'

export default {
  name: 'NavBar',
  data() {
    return {
     
    }
  },
  components:{
    DropDownMenu
  }
}
</script>

<style scoped>

#nav-bar {
  margin: -8px;
  height: 45px;
  background-color: black;
}

.site-title {
  vertical-align: text-bottom;
  color: aliceblue;
  font-size: 24px;
}

#container{width:100%;}
#left{float:left;width:100px;}
#right{float:right;width:100px;}
#center{
  margin:0 auto;
  width:100px;
  text-align: center;
  padding-top: 7px;}

.drop-down-menu {
  padding-left: 10px;
  padding-top: 10px;
  transform: translate(0%, 0%);
}

</style>
