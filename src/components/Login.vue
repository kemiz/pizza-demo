<template>
  <div class="login-page">
    <div class="bg" v-if="!$auth.loading">
      <h1 class="title">Pizza 42 Delivery</h1>
      <img src="../assets/pizza.gif" width="50%">
        <div 
          class="login_btn noselect" 
          v-if="!$auth.isAuthenticated" @click="login"
          @mouseover="attachAqua = !attachAqua"
          @mouseleave="attachAqua = !attachAqua"
          @mouseup="attachAquamarine = !attachAquamarine, attachAqua = !attachAqua"
          @mousedown="attachAquamarine = !attachAquamarine, attachAqua = !attachAqua"
          :class="{aqua: attachAqua, aquamarine: attachAquamarine}">
          login
        </div>
        <div 
          class="login_btn noselect" 
          v-if="$auth.isAuthenticated" @click="logout"
          @mouseover="attachAqua = !attachAqua"
          @mouseleave="attachAqua = !attachAqua"
          @mouseup="attachAquamarine = !attachAquamarine, attachAqua = !attachAqua"
          @mousedown="attachAquamarine = !attachAquamarine, attachAqua = !attachAqua"
          :class="{aqua: attachAqua, aquamarine: attachAquamarine}">
          logout
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

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#login-page {
  text-align: center;
  margin-top: 20px;
}


.title {
  color: grey;
  font-size: 34px;
  font-weight: lighter;
  text-align: center;
}

.main {  
  padding-left: 180%;
}

.bg {
  background-color:  #cabb68;
  position: absolute;
  width: 80%;
  height: 400px;
  left: 0px;
  right: 0px;
  margin: auto;
}

.login_btn {
  border-radius: 20px;
  width: 100px;
  height: 25px;
  background-color: gray;
  text-align: center;
  font-weight: bolder;
  font-size: 24px;
  color: white;
  padding: 20px;
  position: absolute;
  top:0px;
  bottom: 0px;
  left: 0px;
  right: 0px;
  text-align: center;
  color: #2c3e50;
  margin: auto;
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
</style>
