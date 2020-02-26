<template>
  <div class="login-page">
    <div class="bg" v-if="!$auth.loading">
    <div id="container">
      <img v-show="$auth.isAuthenticated" src="../assets/pizza.gif" width="100%">
      <div id="left"></div>
      <div id="right"></div>
      <div id="center">      
      <div 
        class="login_btn noselect" 
        v-show="!$auth.isAuthenticated" @click="login"
        @mouseover="attachAqua = !attachAqua"
        @mouseleave="attachAqua = !attachAqua"
        @mouseup="attachAquamarine = !attachAquamarine, attachAqua = !attachAqua"
        @mousedown="attachAquamarine = !attachAquamarine, attachAqua = !attachAqua"
        :class="{aqua: attachAqua, aquamarine: attachAquamarine}">
        login
      </div>
      </div>
    </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data () {
    return {
        attachAqua: false,
        attachAquamarine: false
    }
  },
  methods: {
    // Log the user in
    login() {
      this.$auth.loginWithRedirect();
    },
    // Log the user out
    logout() {
      this.$auth.logout({
        returnTo: window.location.origin
      });
    }
  }
}
</script>

<style scoped>

.bg {
  background-color:  #cabb68;
  width: 100%;
  height: 500px;
  margin-top: 8px;
}

.login_btn {
  border-radius: 20px;
  width: 110px;
  height: 45px;
  background-color: gray;
  text-align: center;
  font-weight: bolder;
  font-size: 24px;
  color: white;
  padding-top: 6px;
}

.aquamarine {
  background-color: #7FFFD4;
  color: gray;
}

.aqua {
  background-color: #00FFFF;
  color: black;
}

.noselect {
  -webkit-touch-callout: none; /* iOS Safari */
  -webkit-user-select: none; /* Safari */
  -khtml-user-select: none; /* Konqueror HTML */
  -moz-user-select: none; /* Old versions of Firefox */
  -ms-user-select: none; /* Internet Explorer/Edge */
  user-select: none; /* Non-prefixed version, currently */
}

#container{width:100%;}
#left{float:left;width:100px;}
#right{float:right;width:100px;}
#center{
  margin:0 auto;
  width:100px;
  text-align: center;
  padding-top: 150px;}

</style>
